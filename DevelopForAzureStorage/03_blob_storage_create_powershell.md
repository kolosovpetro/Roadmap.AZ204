# Create blob storage using Powershell

- Create resource group
    - `New-AzResourceGroup -Name "storage-training-rg" -Location "centralus"`
- Create storage account
    - `New-AzStorageAccount -ResourceGroupName "storage-training-rg" -Name "storagepkolosov" -Location "centralus" -SkuName "Standard_RAGRS" -Kind "StorageV2"`
- Define storage account context
    - `$ctx = New-AzStorageContext -StorageAccountName "storagepkolosov" -UseConnectedAccount`
- Create storage container
    - `New-AzStorageContainer -Name "pkolosovcontainer" -Context $ctx`
- Delete resource group
  - `Remove-AzResourceGroup -Name "storage-training-rg"`