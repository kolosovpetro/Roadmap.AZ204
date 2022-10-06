# Publish docker image to ACR Powershell

- Create resource group:
    - `$rgname="rg-acr-practice"`
    - `$location="WestUs"`
    - `New-AzResourceGroup -Name $rgname -Location $location`
- Create Azure Container Registry (ACR):
    - `$registryname="pkolosovregistry"`
    - `$registry = New-AzContainerRegistry -ResourceGroupName $rgname -Name $registryname -EnableAdminUser -Sku "Basic"`
- Build docker image:
    - `docker build -t "$registryname.azurecr.io/acr-practice-repository:latest" .`
- Login to ACR:
    - `Connect-AzContainerRegistry -Name $registry.Name`
- Push image to ACR repository:
    - `docker image push -a "$registryname.azurecr.io/acr-practice-repository"`
- Remove resource group
    - `Remove-AzResourceGroup -Name $rgname`