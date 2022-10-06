# Create KeyVault using Powershell

- Create resource group
    - `New-AzResourceGroup -Name "keyvault-training-rg" -Location "centralus"`
- Create key vault
    - `New-AzKeyVault -Name "pkolosovkeyvault" -ResourceGroupName "keyvault-training-rg" -Location "northeurope"`
- Delete resource group
    - `Remove-AzResourceGroup -Name "keyvault-training-rg"`