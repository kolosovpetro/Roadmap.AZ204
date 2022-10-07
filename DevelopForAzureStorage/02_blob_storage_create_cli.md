# Create blob storage using CLI

- Create resource group
    - `$rgName="rg-storage-training"`
    - `$location="centralus"`
    - `az group create -n $rgName -l $location`

- Create storage account
    - `$storName="storagepkolosov"`
    - `az storage account create -g $rgName -n $storName -l $location --sku "Standard_ZRS" --kind "StorageV2"`

- Create storage container
    - `$contName="containerpkolosov"`
    - `az storage container create -n $contName --account-name $storName --public-access "off"`

- Delete resource group
    - `az group delete -n $rgName --yes`