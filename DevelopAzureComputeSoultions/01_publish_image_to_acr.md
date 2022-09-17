# Publish image to ACR

- Create resource group:
    - `az group create --name "rg-acr-practice" --location "westus"`
- Create Azure Container Registry (ACR):
    - `az acr create --resource-group "rg-acr-practice" --name "pkolosovregistry" --sku "Basic"`
- Build docker image:
    - `docker build -t "pkolosovregistry.azurecr.io/acr-practice-repository:latest"`
- Create password using service principal:
    - `$ACR_REGISTRY_ID=$(az acr show --name "pkolosovregistry" --query "id" --output tsv)`
    - `$PASSWORD=$(az ad sp create-for-rbac --name "testsp" --scopes $ACR_REGISTRY_ID --role acrpush --query "password" --output tsv)`
- Define username using service principal:
    - `$USER_NAME=$(az ad sp list --display-name "testsp" --query "[].appId" --output tsv)`
- Login to ACR:
    - `docker login "pkolosovregistry.azurecr.io" --username $USER_NAME --password $PASSWORD`
- Push image to ACR repository:
    - `docker image push -a "pkolosovregistry.azurecr.io/acr-practice-repository"`