# Create KeyVault using CLI

- Create resource group
    - `$rgName="rg-kv-cli"`
    - `$location="EastUS"`
    - `az group create -n $rgName -l $location`

- Create key vault
    - `$kvName="vaultpkolosov$(Get-Random)"`
    - `az keyvault create -g $rgName -n $kvName -l $location`

- Delete resource group
    - `az group delete -n $rgName --yes`