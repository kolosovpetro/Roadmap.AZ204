# Create App Service Using PowerShell

- Login and set subscription
    - `Connect-AzAccount -SubscriptionName "Azure for Students"`
- Create variables
    - `$webappname="mywebapp$(Get-Random)"`
    - `$rgname="rg-web-app-pwsh"`
    - `$location="westus"`
- Create a resource group
    - `New-AzResourceGroup -Name $rgname -Location $location`

- Create app service plan tier
    - `New-AzAppServicePlan -Name $webappname -Location $location -ResourceGroupName $rgname -Tier F1`

- Create a new web app
    - `New-AzWebApp -Name $webappname -Location $location -AppServicePlan $webappname -ResourceGroupName $rgname`

- Delete resource group
    - `Remove-AzResourceGroup -Name $rgname`