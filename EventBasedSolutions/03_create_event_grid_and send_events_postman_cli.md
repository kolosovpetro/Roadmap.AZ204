# Create event grid using CLI and send events from Postman

App service source code: https://github.com/Azure-Samples/azure-event-grid-viewer

- Create resource group
    - `$rgname="rg-event-grid"`
    - `az group create --name $rgname --location "westus"`
- Register event grid provider
    - `az provider register --namespace Microsoft.EventGrid`
- Check event grid provider registration status
    - `az provider show --namespace Microsoft.EventGrid --query "registrationState"`
- Create custom event grid topic
    - `$topicname="pkolosovtopic"`
    - `az eventgrid topic create --name $topicname --location "westus2" -g $rgname`
- Create message endpoint
    - `$sitename="appservice$(Get-Random)"`
    - `$templateUri="https://raw.githubusercontent.com/Azure-Samples/azure-event-grid-viewer/master/azuredeploy.json"`
    - `az deployment group create -g $rgname --template-uri $templateUri --parameters siteName=$sitename hostingPlanName=viewerhost`
- Subscribe to event grid topic endpoint
    - `$endpoint="https://$sitename.azurewebsites.net/api/updates"`
    - `$subId="fc972a47-036d-42a1-a9f7-83c1f6aaed12"`
    - `$sourceId="/subscriptions/$subId/resourceGroups/$rgname/providers/Microsoft.EventGrid/topics/$topicname"`
    - `az eventgrid event-subscription create --source-resource-id $sourceId --name "demoViewerSub" --endpoint $endpoint`
- Send event to custom topic
    - `$endpoint=$(az eventgrid topic show --name $topicname -g $rgname --query "endpoint" --output tsv)`
    - `$key=$(az eventgrid topic key list --name $topicname -g $rgname --query "key1" --output tsv)`
    - `$event="hello world"`
    - `curl -X POST -H "aeg-sas-key: $key" -d "$event" $endpoint`
- Delete resource group
    - `az group delete --name $rgname`

## Postman request

![postman_request](./event_grid/01_event_grid_postman.PNG)

## App service

![app_service](./event_grid/02_event_grid_receiver.PNG)