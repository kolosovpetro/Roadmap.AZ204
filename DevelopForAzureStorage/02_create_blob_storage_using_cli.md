# Create blob storage using CLI

- Create resource group
    - `az group create --name "storage-training-rg" --location "centralus"`
- Create storage account
    - `az storage account create --name "storagepkolosov" --resource-group "storage-training-rg" --location "centralus" --sku "Standard_ZRS" --kind "StorageV2"`
- Create storage container
    - `az storage container create --name "containerpkolosov" --account-name "storagepkolosov" --public-access "off"`