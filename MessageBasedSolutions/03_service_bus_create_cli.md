# Create service bus using CLI

- Create resource group
    - `$rgName="rg-servicebus-cli"`
    - `$location="westus"`
    - `az group create -n $rgName -l $location`

- Create service bus namespace
    - `$nsName="pkolosovsbnamespace"`
    - `az servicebus namespace create -g $rgName -n $nsName`

- Create service bus queue
    - `$sbQueueName="pkolsovqueue"`
    - `az servicebus queue create -g $rgName -n $sbQueueName --namespace-name $nsName`

- Create service bus topics
    - `$topicName="topic_one"`
    - `az servicebus topic create -g $rgName -n $topicName --namespace-name $nsName`

- Create service bus topic subscriptions
    - `$subName="topic_one_subscription"`
    - `az servicebus topic subscription create -g $rgName -n $subName --namespace-name $nsName --topic-name $topicName`

- Delete resource group
    - `az group delete -n $rgName --yes`