# Create Event Hub using CLI

- Create resource group
    - `az group create --name "rg-eventhub-training" --location "centralus"`
- Register namespace
    - `$namespace="eventhubns$(Get-Random)"`
    - `az eventhubs namespace create --resource-group "rg-eventhub-training" --location "centralus" --name $namespace --sku "Standard"`
- Create event hub
    - `az eventhubs eventhub create --name "hubpkolosov" --namespace $namespace --message-retention 3 --partition-count 4 -g "rg-eventhub-training"`
- Delete resource group
    - `az group delete --name "rg-eventhub-training"`