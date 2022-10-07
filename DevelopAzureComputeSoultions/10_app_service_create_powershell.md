# Create App Service using PowerShell

- Create resource group
    - `$rgName="rg-web-app-pwsh"`
    - `$location="westus"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

- Create app service plan tier
    - `$planName="pwshplan"`
    - `New-AzAppServicePlan -ResourceGroupName $rgName -Name $planName -Location $location -Tier "F1"`

- Create a new web app
    - `$appName="appservice-pwsh"`
    - `New-AzWebApp -ResourceGroupName $rgName -Name $appName -Location $location -AppServicePlan $planName`

- Delete resource group
    - `Remove-AzResourceGroup -Name $rgname`