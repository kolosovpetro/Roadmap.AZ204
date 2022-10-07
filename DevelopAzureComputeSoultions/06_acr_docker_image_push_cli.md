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