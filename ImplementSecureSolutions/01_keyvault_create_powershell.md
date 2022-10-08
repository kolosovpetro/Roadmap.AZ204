# Create KeyVault using Powershell

- Create resource group
    - `$rgName="rg-keyvault-pwsh"`
    - `$location="centralus"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

- Create key vault
    - `$kvName="pkolosovkeyvault"`
    - `New-AzKeyVault -ResourceGroupName $rgName -Name $kvName -Location $location`

- Delete resource group
    - `Remove-AzResourceGroup -Name $rgName`