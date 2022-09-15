# Create and deploy Azure Functions

Install Azure Functions Core Tools
locally: [Download Azure Functions Core Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local)

- Create resource group: `az group create --name "rg-function-app" --location "centralus"`
- Create storage account:
  `az storage account create --name "storagepkolosov" --resource-group "rg-function-app" --location "centralus" --sku "Standard_ZRS" --kind "StorageV2"`
- Create function app at Azure:
  `az functionapp create --resource-group "rg-function-app" --name "funcpkolosov" --runtime "dotnet" --runtime-version "3.1" --os-type "Linux" --storage-account "storagepkolosov" --consumption-plan-location "centralus"`
- Create function project source code: `func init --worker-runtime dotnet --force`
- Create function: `func new --template "HTTP trigger" --name "Echo"`
- Build and start function: `func start --build`
- Deploy function: `func azure functionapp publish funcpkolosov`