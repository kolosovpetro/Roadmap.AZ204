# Create blob storage using Powershell

- Create resource group
    - `$rgName="rg-stograge-pwsh"`
    - `$location="centralus"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

- Create storage account
    - `$storName="storagepkolosov"`
    - `New-AzStorageAccount -ResourceGroupName $rgName -Name $storName -Location $location -SkuName "Standard_ZRS" -Kind "StorageV2"`

- Define storage account context
    - `$ctx = New-AzStorageContext -StorageAccountName $storName -UseConnectedAccount`

- Create storage container
    - `$contName="containerpkolosov"`
    - `New-AzStorageContainer -Name $contName -Context $ctx`

- Delete resource group
    - `Remove-AzResourceGroup -Name $rgName`