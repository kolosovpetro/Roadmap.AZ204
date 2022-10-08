# Create Queue storage using Powershell

- Create resource group
    - `$rgName="rg-queue-pwsh"`
    - `$location="centralus"`
    - `New-AzResourceGroup -ResourceGroupName $rgName -Location $location`

- Create storage account
    - `$storName = "storagepkolosov"`
    - `$storageAccount = New-AzStorageAccount -ResourceGroupName $rgName -Name $storName -Location $location -SkuName "Standard_LRS"`

- Define storage account context
    - `$ctx = $storageAccount.Context`

- Create a queue storage
    - `$queueName = "pklosovqueue"`
    - `$queue = New-AzStorageQueue –Name $queueName -Context $ctx`

- Remove resource group
    - `Remove-AzResourceGroup -Name $rgName`