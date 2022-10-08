# Create Notification hub using CLI

- Create resource group
    - `$rgName="rg-nh-cli`
    - `$location="westus2"`
    - `az group create -n $rgName -l $location`

- Create notification hub namespace
    - `$nsName="hubnamespacecli`
    - `az notification-hub namespace check-availability -n $nsName`
    - `az notification-hub namespace create -g $rgName -n $nsName -l $location --sku "Free"`
    - `az notification-hub namespace list -g $rgName`

- Create notification hub
    - `$hubName="testhub-cli"`
    - `az notification-hub create -g $rgName -n $hubName -l $location --namespace-name $nsName`
    - `az notification-hub list -g $rgName --namespace-name $nsName -o table`

# Work with access policies

- List all policies
    - `az notification-hub authorization-rule list -g $rgName --namespace-name $nsName --notification-hub-name $hubName -o table`
- Create authorization rule
    - `$ruleName="spnhub1key"`
    - `az notification-hub authorization-rule create -g $rgName -n $ruleName --namespace-name $nsName --notification-hub-name $hubName --rights Listen Manage Send`
- Get access keys
    - `az notification-hub authorization-rule list-keys -g $rgName -n "DefaultListenSharedAccessSignature" --namespace-name $nsName --notification-hub-name $hubName -o table`
    - `az notification-hub authorization-rule list-keys -g $rgName -n $ruleName --namespace-name $nsName --notification-hub-name $hubName -o table`
- Delete resource group
    - `az group delete -n $rgName --yes`