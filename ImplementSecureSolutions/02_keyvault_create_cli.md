# Create KeyVault using CLI

- Create resource group
    - `az group create --name "rg-keyvault-training" --location "EastUS"`
- Create key vault
    - `az keyvault create --name "vaultpkolosov$(Get-Random)" --resource-group "rg-keyvault-training" --location "EastUS"`
- Delete resource group
    - `az group delete --name "rg-keyvault-training"`