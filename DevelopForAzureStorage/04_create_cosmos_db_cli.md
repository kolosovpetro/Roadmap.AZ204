# Create Cosmos DB using CLI

- Create resource group
    - `az group create --name "azure-cosmos-demo-rg" --location "westus"`
- Create cosmos db account
    - `az cosmosdb create --name "cosmosdbpkolosov" --resource-group "azure-cosmos-demo-rg"`
- Create database
    - `az cosmosdb sql database create --account-name "cosmosdbpkolosov" --resource-group "azure-cosmos-demo-rg" --name "MoviesDatabase"`
- Create container (table)
    - `az cosmosdb sql container create -g "azure-cosmos-demo-rg" -a "cosmosdbpkolosov" -d "MoviesDatabase" -n "Movies" --partition-key-path "/id"`
- Drop resource group
    - `az group delete --name "azure-cosmos-demo-rg"`