# Run docker containers using Azure Container Instances

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

- Define password using service principal (requires AD permissions)
    - `$acrRegistryId=$(az acr show -n $acrName --query "id" -o tsv)`
    - `$principalName="testsp"`
    - `$password=$(az ad sp create-for-rbac -n $principalName --scopes $acrRegistryId --role "acrpush" --query "password" -o tsv)`

- Define username using service principal
    - `$username=$(az ad sp list --display-name $principalName --query "[].appId" -o tsv)`

- Login to ACR
    - `docker login $acrUrl -u $username -p $password`

- Push image to ACR repository
    - `docker image push -a "$acrUrl/${repo}"`

- Delete resource group
    - `az group delete -n $rgName --yes`


- Run container on Azure Container Instances, `dns-name-label` should be unique
    - `$contName="aci-practice-app"`
    - `$dnsLabel="aci-practice-app"`
    - `$image="$acrUrl/${repo}:$tag"`
    - `az container create -g $rgName -n $contName --dns-name-label $dnsLabel --ports 80 --image $image --registry-login-server $acrUrl --registry-username $username --registry-password $password`

- Confirm that container is running and test access to the web application
    - `az container show -g $rgName -n $contName`

- Pull the logs from the container
    - `az container logs -g $rgName -n $contName`

- Build container using ACR
    - `az acr build --registry $acrName --image $image .`

- Delete the running container
    - `az container delete -g $rgName -n $contName --yes`

- Delete resource group
    - `az group delete -n $rgName --yes`