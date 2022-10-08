# Push docker image to ACR via CLI

- Create resource group:
    - `$rgName="rg-acr-practice"`
    - `$location="westus"`
    - `az group create -n $rgName -l $location`

- Create Azure Container Registry (ACR)
    - `$acrName="pkolosovregistry"`
    - `az acr create -g $rgName -n $acrName --sku "Basic"`

- Build docker image
    - `$acrUrl="$acrName.azurecr.io"`
    - `$repo="acr-practice-repository"`
    - `$tag="latest"`
    - `docker build -t "$acrUrl/${repo}:$tag" .`

- Run container locally to test
    - `docker run -d -p 9000:80 --name "locally-test-container" "$acrUrl/${repo}:$tag"`
    - http://localhost:9000/swagger/index.html

- Define password using service principal (requires AD permissions)
    - `$acrRegistryId=$(az acr show -n $acrName --query "id" -o tsv)`
    - `$principalName="testsp"`
    - `$password=$(az ad sp create-for-rbac -n $principalName --scopes $acrRegistryId --role "acrpush" --query "password" -o tsv)`

- Define username using service principal
    - `$username=$(az ad sp list --display-name $principalName --query "[].appId" -o tsv)`

- Login to ACR with credentials
    - `docker login $acrUrl -u $username -p $password`
    - OR: `az acr login -n $acrName`

- Push image to ACR repository
    - `docker image push -a "$acrUrl/${repo}"`
    - OR: `docker push "$acrUrl/${repo}:newdeploy"`

- Delete resource group
    - `az group delete -n $rgName --yes`

# Deploy container to app service

- Create an App Service plan
    - `$planName="acr-container-plan-f1"`
    - `az appservice plan create -g $rgName -n $planName --sku "F1" --is-linux`

- Create app service
    - `$appName="app-container-deploy"`
    - `$image="$acrUrl/${repo}:$tag"`
    - `az webapp create -g $rgName -n $appName --plan $planName --deployment-container-image-name $image`

- Configure app service port
    - `az webapp config appsettings set -g $rgName -n $appName --settings WEBSITES_PORT=80`

- Enable the system-assigned managed identity for the web app
    - `$identityId=$(az webapp identity assign -g $rgName -n $appName --query "principalId" -o tsv)`

- Retrieve your subscription ID
    - `$subId=$(az account show --query "id" -o tsv)`

- Grant the managed identity permission to access the container registry
    - `$scope="/subscriptions/$subId/resourceGroups/$rgName/providers/Microsoft.ContainerRegistry/registries/$acrName"`
    - `az role assignment create --assignee $identityId --scope $scope --role "AcrPull"`

- Configure your app to use the managed identity to pull from Azure Container Registry
    - `$id="/subscriptions/$subId/resourceGroups/$rgName/providers/Microsoft.Web/sites/$appName/config/web"`
    - `az resource update --ids $id --set properties.acrUseManagedIdentityCreds=True`

- Deploy image to app service
    - `az webapp config container set -g $rgName -n $appName --docker-custom-image-name $image --docker-registry-server-url "https://$acrUrl"`

- Turn on container logging
    - `az webapp log config -g $rgName -n $appName --docker-container-logging filesystem`

- Enable the log stream
    - `az webapp log tail -g $rgName -n $appName`

# Configure continuous deployment

- Enable CI/CD in App Service
    - `$cicdUrl=$(az webapp deployment container config -g $rgName -n $appName --enable-cd "true" --query "CI_CD_URL" -o tsv)`

- Create a webhook in your container registry using the CI_CD_URL you got from the last step
    - `$hookName="appserviceCD"`
    - `az acr webhook create -n $hookName --registry $acrName --uri $cicdUrl --actions push --scope "${repo}:$tag"`

- Test if your webhook is configured properly, ping the webhook and see if you get a 200 OK response
    - `$eventId=$(az acr webhook ping -n $hookName --registry $acrName --query "id" -o tsv)`
    - `az acr webhook list-events -n $hookName --registry $acrName --query "[?id=='$eventId'].eventResponseMessage"`

