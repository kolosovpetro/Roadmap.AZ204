# Create Notification hub using PowerShell

- Create a resource group
    - `$rgName="rg-hub-pwsh"`
    - `$location="East US"`
    - `New-AzResourceGroup -Name $rgName -Location $location`

- Create a namespace for the resource group
    - `$nsName="eventhubnspwsh"`
    - `New-AzNotificationHubsNamespace -ResourceGroup $rgName -Namespace $nsName -Location $location`

- Create an input JSON file that you use with the New-AzNotificationHub command
    - `$text = '{"name": "MyNotificationHub",  "Location": "East US",  "Properties": { }}'`
    - `$text | Out-File "NotificationHubConfig.json"`

- Create a notification hub
    - `$inputFilePath="./NotificationHubConfig.json"`
    - `New-AzNotificationHub -ResourceGroup $rgName -Namespace $nsName -InputFile $inputFilePath`

- Delete resource group
    - `Remove-AzResourceGroup -ResourceGroupName $rgName`