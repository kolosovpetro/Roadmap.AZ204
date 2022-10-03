# Create Event Hub using Powershell

- Create resource group
    - `New-AzResourceGroup –Name "rg-eventhub-training" –Location "centralus"`
- Register namespace
    - `$namespace="eventhubns$(Get-Random)"`
    - `New-AzEventHubNamespace -ResourceGroupName "rg-eventhub-training" -NamespaceName $namespace -Location "centralus" -SkuName "Standard"`
- Create event hub
    - `New-AzEventHub -ResourceGroupName "rg-eventhub-training" -NamespaceName $namespace -EventHubName "hubpkolosov" -MessageRetentionInDays 3 -PartitionCount 4`
- Delete resource group
    - `Remove-AzResourceGroup -Name "rg-eventhub-training"`