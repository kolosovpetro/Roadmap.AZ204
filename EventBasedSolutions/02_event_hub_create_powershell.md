# Create Event Hub using Powershell

- Create resource group
    - `$rgName="rg-eventhub-pwsh"`
    - `$location="centralus"`
    - `New-AzResourceGroup –Name $rgName –Location $location`

- Register namespace
    - `$nsName="eventhubns$(Get-Random)"`
    - `New-AzEventHubNamespace -ResourceGroupName $rgName -NamespaceName $nsName -Location $location -SkuName "Standard"`

- Create event hub
    - `$hubName="hubpkolosov"`
    - `New-AzEventHub -ResourceGroupName $rgName -EventHubName $hubName -NamespaceName $nsName -MessageRetentionInDays "3" -PartitionCount "4"`

- Delete resource group
    - `Remove-AzResourceGroup -Name $rgName`