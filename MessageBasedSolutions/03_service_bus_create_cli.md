# Create service bus using CLI

- Create resource group
    - `az group create --name "service-bus-topics-rg" --location "westus"`
- Create service bus namespace
    - `az servicebus namespace create --name "pkolosovsbnamespace" --resource-group "service-bus-topics-rg"`
- Create service bus queue
    - `az servicebus queue create --name "pkolsovqueue" --namespace-name "pkolosovsbnamespace" --resource-group "service-bus-topics-rg"`
- Create service bus topics
    - `az servicebus topic create --namespace-name "pkolosovsbnamespace" --name "topic_one" --resource-group "service-bus-topics-rg"`
    - `az servicebus topic create --namespace-name "pkolosovsbnamespace" --name "topic_two" --resource-group "service-bus-topics-rg"`
- Create service bus topic subscriptions
    - `az servicebus topic subscription create --resource-group "service-bus-topics-rg" --namespace-name "pkolosovsbnamespace" --name "topic_one_subscription" --topic-name "topic_one"`
    - `az servicebus topic subscription create --resource-group "service-bus-topics-rg" --namespace-name "pkolosovsbnamespace" --name "topic_two_subscription" --topic-name "topic_two"`