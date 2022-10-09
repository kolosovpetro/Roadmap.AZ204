# Create and deploy Azure Functions

Install Azure Functions Core Tools
locally: [Download Azure Functions Core Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local)

- Create resource group
    - `$rgName="rg-function-cli"`
    - `$location="centralus"`
    - `az group create -n $rgName -l $location`

- Create storage account
    - `$storName="storagepkolosov"`
    - `az storage account create -g $rgName -n $storName -l $location --sku "Standard_ZRS" --kind "StorageV2"`

- Create function app at Azure
    - `$funcName="funcpkolosov"`
    - `az functionapp create -g $rgName -n $funcName --runtime "dotnet" --functions-version "4" --runtime-version "6" --os-type "Linux" --storage-account $storName --consumption-plan-location $location`

- Create function project source code
    - `func init --worker-runtime dotnet --force`

- Create function with template
    - `func new --template "HTTP trigger" --name "Echo"`

- Build and start function
    - `func start --build`

- Deploy function
    - `func azure functionapp publish $funcName`

- Delete resource group
    - `az group delete -n $rgName --yes`