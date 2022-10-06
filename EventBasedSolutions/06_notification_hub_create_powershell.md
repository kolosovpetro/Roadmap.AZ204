# Create Notification hub using PowerShell

- Set appropriate values for these variables
    - `$resourceGroupName = "rg-hub-$(Get-Random 1000)"`
    - `$nhubnamespace = "hubns$(Get-Random 1000)"`
    - `$location = "East US"`

- Create a resource group.
    - `New-AzResourceGroup -Name $resourceGroupName -Location $location`

- Create a namespace for the resource group
    - `New-AzNotificationHubsNamespace -ResourceGroup $resourceGroupName -Namespace $nhubnamespace -Location $location`

- Create an input JSON file that you use with the New-AzNotificationHub command
    - `$text = '{"name": "MyNotificationHub",  "Location": "East US",  "Properties": { }}'`
    - `$text | Out-File "NotificationHubConfig.json"`

- Create a notification hub
    - `New-AzNotificationHub -ResourceGroup $resourceGroupName -Namespace $nhubnamespace -InputFile "./NotificationHubConfig.json"`

- Delete resource group
    - `Remove-AzResourceGroup -ResourceGroupName $resourceGroupName`