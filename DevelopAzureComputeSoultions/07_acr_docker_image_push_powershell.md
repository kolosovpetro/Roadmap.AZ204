# Push docker image to ACR via Powershell

- Create resource group
    - `$rgName="rg-acr-practice"`
    - `$location="WestUs"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

- Create Azure Container Registry (ACR)
    - `$acrName="pkolosovregistry"`
    - `$registry = New-AzContainerRegistry -ResourceGroupName $rgName -Name $acrName -EnableAdminUser -Sku "Basic"`

- Build docker image
    - `$acrUrl="$acrName.azurecr.io"`
    - `$repo="acr-practice-repository"`
    - `$tag="latest"`
    - `docker build -t "$acrUrl/${repo}:$tag" .`

- Login to ACR
    - `Connect-AzContainerRegistry -Name $registry.Name`

- Push image to ACR repository
    - `docker image push -a "$acrUrl/${repo}"`

- Remove resource group
    - `Remove-AzResourceGroup -Name $rgName`