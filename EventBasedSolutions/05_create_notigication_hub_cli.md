# Create Notification hub using CLI

- Create resource group
    - `$rgname="rg-nh-$(Get-Random 1000)"`
    - `az group create --name $rgname --location "westus2"`
- Create notification hub namespace
    - `$hubnamespace="hubnamespace$(Get-Random 1000)"`
    - `az notification-hub namespace check-availability --name $hubnamespace`
    - `az notification-hub namespace create --resource-group $rgname --name $hubnamespace --location "westus2" --sku "Free"`
    - `az notification-hub namespace list --resource-group $rgname`
- Create notification hub
    - `$hubname="testhub-$(Get-Random 1000)"`
    - `az notification-hub create --resource-group $rgname --namespace-name $hubnamespace --name $hubname --location "westus2"`
    - `az notification-hub list --resource-group $rgname --namespace-name $hubnamespace --output table`

# Work with access policies

- List all policies
    - `az notification-hub authorization-rule list --resource-group $rgname --namespace-name $hubnamespace --notification-hub-name $hubname --output table`
- Create authorization rule
    - `$rulename="spnhub1key"`
    - `az notification-hub authorization-rule create --resource-group $rgname --namespace-name $hubnamespace --notification-hub-name $hubname --name $rulename --rights Listen Manage Send`
- Get access keys
    - `az notification-hub authorization-rule list-keys --resource-group $rgname --namespace-name $hubnamespace --notification-hub-name $hubname --name DefaultListenSharedAccessSignature --output table`
    - `az notification-hub authorization-rule list-keys --resource-group $rgname --namespace-name $hubnamespace --notification-hub-name $hubname --name $rulename --output table`
- Delete resource group
    - `az group delete --name $rgname`