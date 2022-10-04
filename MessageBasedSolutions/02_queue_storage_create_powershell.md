# Create Queue storage using Powershell

- Create resource group
    - `$resourceGroup="rg-queue-pwsh"`
    - `$location="centralus"`
    - `New-AzResourceGroup -ResourceGroupName $resourceGroup -Location $location`
- Create storage account
    - `$storageAccountName = "storagepkolosov"`
    - `$storageAccount = New-AzStorageAccount -ResourceGroupName $resourceGroup -Name $storageAccountName -Location $location -SkuName "Standard_LRS"`
- Extract storage context
    - `$ctx = $storageAccount.Context`
- Create a queue
    - `$queueName = "pklosovqueue"`
    - `$queue = New-AzStorageQueue –Name $queueName -Context $ctx`
- Remove resource group
    - `Remove-AzResourceGroup -Name $resourceGroup`