# Create queue storage using CLI

- Create resource group
    - `az group create --name "storage-queue-demo-rg" --location "westus"`
- Create storage account
    - `az storage account create --name "pkolosovstorage" --resource-group "storage-queue-demo-rg"`
- Create storage queue
    - `az storage queue create --name "pkolosov-storage-queue" --account-name "pkolosovstorage"`