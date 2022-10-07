# Create Cosmos DB using CLI

- Create resource group
    - `$rgName="rg-cosmos-cli"`
    - `$location="westus"`
    - `az group create -n $rgName -l $location`

- Create cosmos db account
    - `$cosmosDbAccountName="cosmosdbpkolosov"`
    - `az cosmosdb create -g $rgName -n $cosmosDbAccountName`

- Create database
    - `$dbName="MoviesDatabase"`
    - `az cosmosdb sql database create -g $rgName -n $dbName -a $cosmosDbAccountName`

- Create container (table)
    - `$contName="Movies"`
    - `az cosmosdb sql container create -g $rgName -n $contName -d $dbName -a $cosmosDbAccountName --partition-key-path "/id"`

- Delete resource group
    - `az group delete -n $rgName --yes`