# Create Event Hub using CLI

- Create resource group
    - `$rgName="rg-evenhub-cli"`
    - `$location="centralus"`
    - `az group create -n $rgName -l $location`

- Register namespace
    - `$nsName="eventhubns$(Get-Random 1000)"`
    - `az eventhubs namespace create -g $rgName -n $nsName -l $location --sku "Standard"`

- Create event hub
    - `$hubName="hubpkolosov"`
    - `az eventhubs eventhub create -g $rgName -n $hubName --namespace $nsName --message-retention "3" --partition-count "4"`

- Delete resource group
    - `az group delete -n $rgName --yes`