# Create queue storage using CLI

- Create resource group
    - `$rgName="rg-queuestorage-cli"`
    - `$location="westus"`
    - `az group create -n $rgName -l $location`

- Create storage account
    - `$storName="pkolosovstorage"`
    - `az storage account create -g $rgName -n $storName`

- Create storage queue
    - `$queueName="pkolosov-storage-queue"`
    - `az storage queue create -n $queueName --account-name $storName`

- Delete resource group
    - `az group delete -n $rgName --yes`