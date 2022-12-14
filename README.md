# Roadmap.AZ204

Main purpose of this project is to provide such a structure that it will
be immediately clear what topics should be refreshed in memory.
Unfortunately, AZ-204 exam is not kinda school exam where you are
free to grind-core static questions and get excellent, it requires a deep
understanding of the topics.
However, there is a strategy that, I hope, leads to the success.
Nothing new, just a study that includes two basic components: **theory and practice**.
Theory is mainly studied using the resources:

- [Pluralsight AZ-204 Preparation](https://app.pluralsight.com/paths/certificate/developing-solutions-for-microsoft-azure-az-204)
- [Udemy AZ-204 Preparation](https://www.udemy.com/course/az-300-microsoft-azure-architect-technologies-lab-practice/)
- [Quizlet](https://quizlet.com/)

All of these resources require paid subscription.
Pluralsight as well as Udemy are used in order to get information and then perform practice based on demo sections.
Quizlet is used to grind-core new definitions or key-information.

Practice could be achieved using both

- [Pluralsight AZ-204 Demos](https://app.pluralsight.com/paths/certificate/developing-solutions-for-microsoft-azure-az-204)
- [Microsoft Labs](https://microsoftlearning.github.io/AZ-204-DevelopingSolutionsforMicrosoftAzure/)

So, study flow is the following

- Theory: `Watch course on Pluralsight or Udemy -> Note definitions -> Create quizlet quiz -> Grind defintions`
- Practice: `Watch cource on pluralsight -> Complete demos of the cource -> Upload results to github`
- Practice: `Complete lab on Microsoft Labs resource`

## Repeat on daily basis

Also, keep especial attention to the following topics and repeat them frequently

- [App service plan features quiz](https://quizlet.com/_c1fn2x?x=1qqt&i=2n5czk)
- [App service plan limits (MSDN)](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits#app-service-limits)
- [Storage replication strategies quiz](https://quizlet.com/_c1fxsz?x=1jqt&i=2n5czk)
- Choosing proper solution between event-based and message-based
- `AzCopy` command
- [Cosmos DB consistency levels quiz](https://quizlet.com/_c1fuf3?x=1jqt&i=2n5czk)
- KeyVault references syntax
- [Cache key eviction quiz](https://quizlet.com/_c20755?x=1qqt&i=2n5czk)
- [Web test types quiz](https://quizlet.com/_c230q0?x=1jqt&i=2n5czk)
- [APIM management policies](https://github.com/kolosovpetro/MonitoringAndLogging.AZ204/tree/master/api-management-policies)
- [Resources creation steps quiz](https://quizlet.com/_c3ilw9?x=1jqt&i=2n5czk)
- [ACR roles quiz](https://quizlet.com/_c3nqw2?x=1jqt&i=2n5czk)
- [Compute solutions CLI quiz](https://quizlet.com/_c44f93?x=1jqt&i=2n5czk)
- [Storage CLI quiz](https://quizlet.com/_c3qqkb?x=1qqt&i=2n5czk)
- [Event solutions CLI quiz](https://quizlet.com/_c3rver?x=1jqt&i=2n5czk)
- [Message solutions CLI quiz](https://quizlet.com/_c44jo9?x=1jqt&i=2n5czk)

As a short conclusion, I want to mention that I am also relatively newbie on Azure,
so this study approach is as well an experiment for me, we'll see how it works :)

PS I have passed AZ-204 exam on 7th November 2022, after around 1.5 month of preparation.

- https://www.credly.com/badges/fbc55a56-53d1-4098-905f-91051da9eab1/public_url

![Az204](./az204.PNG)

## Topics covered by AZ-204 exam

AZ-204 consists of five basic modules such that

### 1. Develop Azure Compute Solutions (25-30%)

- **Implement IaaS Solutions**
    - Provision Virtual Machines (VMs)
        - [VM Windows create CLI](./DevelopAzureComputeSoultions/01_vm_windows_create_cli.md)
        - [VM Linux create CLI](./DevelopAzureComputeSoultions/02_vm_linux_create_cli.md)
        - [VM Windows create Powershell](./DevelopAzureComputeSoultions/03_vm_windows_create_powershell.md)
    - Configure, validate, and deploy ARM templates
        - [ARM template deploy CLI](./DevelopAzureComputeSoultions/04_arm_template_deploy_cli.md)
        - [ARM template deploy Powershell](./DevelopAzureComputeSoultions/05_arm_template_deploy_powershell.md)
    - Configure container images for solutions
    - [ACR docker image push CLI || Deploy container to web app](./DevelopAzureComputeSoultions/06_acr_docker_image_push_cli.md)
    - [ACR docker image push Powershell](./DevelopAzureComputeSoultions/07_acr_docker_image_push_powershell.md)
    - [ACI run docker container](./DevelopAzureComputeSoultions/08_aci_run_docker_container.md)
    - Pluralsight
      course: [Microsoft Azure Developer: Implement IaaS Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-iaas-solutions/table-of-contents)

- **Create Azure App Service Web Apps**
    - [App service create CLI](./DevelopAzureComputeSoultions/09_app_service_create_cli.md)
    - [App service create PowerShell](./DevelopAzureComputeSoultions/10_app_service_create_powershell.md)
    - [Enable diagnostic logging](https://github.com/kolosovpetro/AppServiceLogging.AZ204)
    - [App service ZIP deploy CLI](./DevelopAzureComputeSoultions/11_app_service_zip_deploy_cli.md)
    - [App service ARM template deploy (CLI & Powershell)](https://azure.microsoft.com/en-us/resources/templates/webapp-basic-linux/)
    - Configure web app settings
    - Implement autoscaling rules, including scheduled autoscaling, and scaling by operational or system metrics
    - [App service plan tiers (Medium post)](https://medium.com/@zaab_it/azure-app-service-plan-tiers-f07d5e22297a)
    - [App service limits (MSDN)](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits#app-service-limits)
    - [App service pricing (MSDN)](https://azure.microsoft.com/en-us/pricing/details/app-service/windows/)
    - [App service plan features](https://drive.google.com/file/d/1xOv2HuAv8zbDCymZVCvBAHLc-MWkId_c/view?usp=sharing)
    - [App service plan tiers usage](./DevelopAzureComputeSoultions/12_app_service_plan_tiers_usage.md)
    - [App service docker environment constants](https://drive.google.com/file/d/15xRK_ea3s-tVwcnQHziyoT59KISt1Ct1/view?usp=sharing)
    - [App service add custom domain](./DevelopAzureComputeSoultions/13_app_service_add_custom_domain.md)
    - [App service configure SSL for custom domain](./DevelopAzureComputeSoultions/14_app_service_configure_ssl_for_custom_domain.md)
    - Pluralsight
      course: [Microsoft Azure Developer: Create Azure App Service Web Apps](https://app.pluralsight.com/library/courses/azure-developer-create-azure-app-service-web-apps/table-of-contents)

- **Implement Azure Functions**
    - [Azure Functions create and deploy CLI](./DevelopAzureComputeSoultions/15_azure_functions_create_and_deploy_cli.md)
    - Implement input and output bindings for a function
    - Implement function triggers by using data operations, timers, and webhooks
    - Implement Azure Durable Functions
        - Azure Durable Functions: Chaining
        - Azure Durable Functions: Fan-in / Fan-out
        - Azure Durable Functions: Async HTTP APIs
        - Azure Durable Functions: Monitoring
        - Azure Durable Functions: Human Interaction
        - [!!!DO NOT DO THIS IN ORCHESTRATOR FUNCTION!!!](./DevelopAzureComputeSoultions/16_dont_do_this_in_orchestrator_function.md)
    - Implement custom handlers
    - Pluralsight
      course: [Microsoft Azure Developer: Implement Azure Functions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-azure-functions/table-of-contents)

- **Quiz**
    - [Develop Azure Compute Solutions Quiz](https://smarturl.it/11_COMPUTE_QUIZ)

- **Exam Alert**
    - [Exam Alert: Develop Azure Compute Solutions](https://app.pluralsight.com/library/courses/exam-alert-develop-azure-compute-solutions/table-of-contents)

### 2. Develop for Azure Storage (15-20%)

- **Develop Solutions that use Cosmos DB Storage**
    - Select the appropriate API and SDK for a solution
    - Implement partitioning schemes and partition keys
    - Perform operations on data and Cosmos DB containers
    - Set the appropriate consistency level for operations
    - Manage change feed notifications
    - [NoSQL database differences](https://drive.google.com/file/d/1IqId3TBDe7gN3-aQZU32FXJICEs8Rbwh/view?usp=sharing)
    - [Cosmos DB partition key](https://drive.google.com/file/d/1UhB_Fs4MW_gpjYsZUhJaQs7ozwE9HFl3/view?usp=sharing)
    - [Cosmos DB consistency levels](https://drive.google.com/file/d/1bmCedOjDOXpXOiW5fXQhKGFphdOyHBHn/view?usp=sharing)
    - [Cosmos DB API use cases](https://drive.google.com/file/d/1nck5kb08YtcLw49rcXY98c8xGMv7LySd/view?usp=sharing)
    - [Cosmos DB Server-side concepts](https://drive.google.com/file/d/1kmKm83BW1Z1opXwGL9lme6CBRe0lowRg/view?usp=sharing)
    - [Cosmos DB Throughput](https://drive.google.com/file/d/1dzr5Q5Fx4FoJukBdOYw6uZjhOX0aWu-A/view?usp=sharing)
    - [Cosmos DB create CLI](./DevelopForAzureStorage/04_cosmos_db_create_cli.md)
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Solutions with Cosmos DB Storage](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-solutions-cosmos-db-storage/table-of-contents)

- **Develop solutions that use Blob storage**
    - [Move items in Blob storage between storage accounts or containers](./DevelopForAzureStorage/01_move_items_between_blob_accounts.md)
    - [Set and retrieve properties and metadata](https://github.com/kolosovpetro/AzureStorageSDKTraining.AZ204)
    - Perform operations on data by using the appropriate SDK
    - Implement storage policies, and data archiving and retention
    - [Blob storage replication strategies](https://drive.google.com/file/d/1RIrGUJw7A0_f2ldJWpF2CQX6gQ4aHm0y/view)
    - [Blob storage create CLI](./DevelopForAzureStorage/02_blob_storage_create_cli.md)
    - [Blob storage create Powershell](./DevelopForAzureStorage/03_blob_storage_create_powershell.md)
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Solutions with Blob Storage](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-solutions-blob-storage/table-of-contents)

- **Quiz**
    - [Develop for Azure Blob Storage Quiz](https://smarturl.it/09_BLOB_STORAGE_QUIZ)
    - [Develop for Azure CosmosDB Quiz](https://smarturl.it/10_COSMOSDB_QUIZ)

- **Exam Alert**
    - [Exam Alert: Develop for Azure Storage](https://app.pluralsight.com/library/courses/exam-alert-develop-azure-storage/table-of-contents)

### 3. Implement Azure Security (20-25%)

- **Implement User Authentication and Authorization**
    - Authenticate and authorize users by using the Microsoft Identity Platform
    - [Authenticate and authorize users and apps by using Azure Active Directory](https://gist.github.com/kolosovpetro/4e2a830b51422bfce8e5bd951f76d71d)
        - [Single and multi tenant authorization using MVC app](https://github.com/kolosovpetro/OpenIDConnect.AZ204)
        - [Get an AAD token and use it to send messages to a Service Bus queue](https://learn.microsoft.com/en-us/rest/api/servicebus/get-azure-active-directory-token)
        - [Role-based authorization using AAD and two web APIs](https://github.com/kolosovpetro/OpenIDConnect.AZ204.API)
        - [Quick and simple role-based AAD authentication & authorization using JWT tokens](https://github.com/kolosovpetro/QuickAndSimpleApiAuth)
    - Create and implement shared access signatures
    - [RBAC Documentation](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview)
    - [RBAC slides](https://drive.google.com/file/d/1G_0uSgpZpOZI1LQlZyxkZg8BzuzdXj6Q/view?usp=sharing)
    - [SAS token example](https://drive.google.com/file/d/14LXsFtzHo8s6WsiCTqVXsGZ3GSu5n_yV/view?usp=sharing)
    - [SAS best practices](https://drive.google.com/file/d/1tDB1L_pTpn8Ce7gS4xsGQOrceg0sM62Y/view?usp=sharing)
    - [Stored access policy example](https://drive.google.com/file/d/1v2mPJw0nq9A_DzW3y7WnveOZouYcfZge/view?usp=sharing)
    - [RFC: OAuth 2.0 Authorization Framework](https://www.rfc-editor.org/rfc/rfc6749)
    - [RFC: Proof key of code exchange (PKCE)](https://www.rfc-editor.org/rfc/rfc7636.html)
    - [OAuth 2.0 Flows Diagrams](https://darutk.medium.com/diagrams-and-movies-of-all-the-oauth-2-0-flows-194f3c3ade85)
    - [OAuth general flow](./ImplementSecureSolutions/03_oauth_flow.pdf)
    - [OAuth + PKCE flow](./ImplementSecureSolutions/04_oauth_with_pkce_flow.pdf)
    - Pluralsight
      course: [Microsoft Azure Developer: Implement User Authentication and Authorization](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-user-authentication-authorization/table-of-contents)

- **Implement Secure Cloud Solutions**
    - Secure app configuration data by using the App Configuration and Azure Key Vault
    - Develop code that uses keys, secrets, and certificates stored in Azure Key Vault
    - Implement solutions that interact with Microsoft Graph
    - Implement Managed Identities for Azure resources
    - KeyVault create using CLI
    - [KeyVault create using PowerShell](./ImplementSecureSolutions/01_keyvault_create_powershell.md)
    - [KeyVault create using CLI](./ImplementSecureSolutions/02_keyvault_create_cli.md)
    - [KeyVault references use cases](https://drive.google.com/file/d/16zE4LFvmzpsA0BQ-iXJQSMtuqXHUT_uL/view?usp=sharing)
    - [KeyVault references syntax](https://drive.google.com/file/d/1AxhpHJMGxCjLz_hxMEDlpToxSHREjsjg/view?usp=sharing)
    - [KeyVault soft delete](https://drive.google.com/file/d/1CB8V9aRtJSsSOHpsw9zceA9KEIEXDhjr/view?usp=sharing)
    - [KeyVault enable soft delete and purge protection via PowerShell](https://drive.google.com/file/d/1411eHCA5Qsx2P7ppxTmmPh4KcsFj43xy/view?usp=sharing)
    - Pluralsight
      course: [Microsoft Azure Developer: Implement Secure Cloud Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-secure-cloud-solutions/table-of-contents)

- **Quiz**
    - [Implement Azure Security Quiz](https://smarturl.it/07_SECURITY_QUIZ)

- **Exam Alert**
    - [Exam Alert: Implement Azure Security](https://app.pluralsight.com/library/courses/exam-alert-implement-azure-security/table-of-contents)

### 4. Monitor, Troubleshoot, and Optimize Azure Solutions (15-20%)

- **Integrate Caching and Content Delivery Within Solutions**
    - Configure cache and expiration policies for Azure Redis cache
    - Implement secure and optimized application cache patterns including data sizing, connections, encryption, and
      expiration
    - [CDN content distribution](https://drive.google.com/file/d/1MP-muO-fb8vQAe9aybHPBb4zQ6yYKUkf/view?usp=sharing)
    - [CDN request response life cycle](https://drive.google.com/file/d/1fUnHwVpQu9LPXUMIc-JN4jWg14CMwbU3/view?usp=sharing)
    - [When to use cache](https://drive.google.com/file/d/1zPnuBkYQj0LXMhglzJer-dyKDJfwX9pP/view?usp=sharing)
    - [Cache best practices](https://drive.google.com/file/d/1Isk1NHdKCn2A7pgDgEKxNPM5ebtAbkRN/view?usp=sharing)
    - [Cache aside pattern](https://drive.google.com/file/d/1U__hIdaqv5PyXUz22GliOoNvcVnU93nE/view?usp=sharing)
    - [Cache content pattern](https://drive.google.com/file/d/1I9QkMB6HA0P_CrhZbV4iNCii43S7usHa/view?usp=sharing)
    - [Cache user session pattern](https://drive.google.com/file/d/1BeOsv5jP-tVObxvYCDE6yAiF9RxqknXg/view?usp=sharing)
    - [Azure redis cache use cases](https://drive.google.com/file/d/1xBt6sv6EPvwnyk7K2XLBf_E1m1UMZ-WN/view?usp=sharing)
    - [Cache configuration best practices](https://drive.google.com/file/d/1O1rhj68a5eBm_82eY2WWmacYsYbrGJuZ/view?usp=sharing)
    - Pluralsight
      course: [Microsoft Azure Developer: Integrate Caching and Content Delivery](https://app.pluralsight.com/library/courses/microsoft-azure-developer-integrate-caching-content-delivery/table-of-contents)

- **Instrument Solutions to Support Monitoring and Logging**
    - Configure an app or service to use Application Insights
    - Analyze and troubleshoot solutions by using Azure Monitor
    - Implement Application Insights web tests and alerts
    - [Configure web app logging](https://drive.google.com/file/d/1Am166myZK5FcltT4LCWkrUWVYXXIIruD/view?usp=sharing)
    - [Dealing with transient faults](https://drive.google.com/file/d/1KdkHNft_KZbK2sZUuhqvaJagHD3aWIxE/view?usp=sharing)
    - [Azure monitor structure](https://drive.google.com/file/d/1CTR122_HrQa6gDiir09G4irdIX6ma0OO/view?usp=sharing)
    - [Azure monitor capabilities](https://drive.google.com/file/d/1VLSPH7ZwNw7VUwyV6rAQxHxvXf6kWSk7/view?usp=sharing)
    - [Application insights capabilities](https://drive.google.com/file/d/1OAETkG9TMb1R2Txwb9kuXU974v2pJAJT/view?usp=sharing)
    - [Application insights action groups](https://drive.google.com/file/d/1D3VMF_VonW-Ph8DbynKJ5bzP07VxlhC_/view?usp=sharing)
    - [Transient fault challenges](https://drive.google.com/file/d/1hQbqY7sJYabhc7syfdUrs-yWaEqQfKP6/view?usp=sharing)
    - [Retry policy](https://drive.google.com/file/d/1xl8UlPMYHrLqHLK1uZB5rMlqrlKHUK7l/view?usp=sharing)
    - [Circuit breaker policy](https://drive.google.com/file/d/1t0DvYnsQO0v69NMhJlfINJB78EWIT6Hc/view?usp=sharing)
    - [Azure resource abbreviations](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations)
    - Pluralsight
      course: [Microsoft Azure Developer: Instrument Solutions for Monitoring and Logging](https://app.pluralsight.com/library/courses/microsoft-azure-developer-instrument-solutions-monitoring-logging/table-of-contents)

- **Quiz**
    - [Monitor, Troubleshoot, and Optimize Azure Solutions Quiz](https://smarturl.it/MONITOR_TROUBLE_QUIZ)

- **Exam Alert**
    - [Exam Alert: Monitor, Troubleshoot, and Optimize Azure Solutions](https://app.pluralsight.com/library/courses/exam-alert-monitor-troubleshoot-optimize-azure-solutions/table-of-contents)

### 5. Connect to and Consume Azure Services and Third-party Services (15-20%)

- **Implement API Management**
    - Create an API Management instance
    - Configure authentication for APIs
    - Define policies for APIs
    - [APIM access restrictions](https://drive.google.com/file/d/10urhZlhjKEUwt6sUt6f7_DvoIdsni_yx/view?usp=sharing)
    - [APIM caching](https://drive.google.com/file/d/1mV__RiAsplzYzTGuWnvFqeGbegy47gzQ/view?usp=sharing)
    - [APIM policy example](https://drive.google.com/file/d/1z63z5dMczTA6uGQGtcUTOEAZ4UQwZnlM/view?usp=sharing)
    - [APIM policies diagram](./DevelopApiManagement/01_apim_policies.pdf)
    - Pluralsight
      course: [Microsoft Azure Developer: Implement API Management](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-api-management/table-of-contents)

- **Develop Event-Based Solutions**
    - [Implement solutions that use Azure Event Grid](https://github.com/kolosovpetro/EventGridDemo.AZ204)
    - [Event grid provider registration](https://drive.google.com/file/d/1RMasVMHw-Jqpb7QQ4_zeYevYGJX8AZ1g/view?usp=sharing)
    - [Event grid terminology](https://drive.google.com/file/d/1lKrNdgdeKy1G5nYXJVqEjh4kpn0i_zbL/view?usp=sharing)
    - [Event grid create CLI and send events via Postman](./EventBasedSolutions/03_event_grid_create_and%20send_events_postman_cli.md)
    - [Event grid create Powershell and send events via Postman](./EventBasedSolutions/04_event_grid_create_and_send_events_postman_powershell.md)
    - Implement solutions that use Azure Event Hub
    - [Event hub components](https://drive.google.com/file/d/1ROqLEc6nhFH05qZHwNySE9IDmv0_WiKq/view?usp=sharing)
    - [Event hub create CLI](./EventBasedSolutions/01_event_hub_create_cli.md)
    - [Event hub create Powershell](./EventBasedSolutions/01_event_hub_create_cli.md)
    - [Event hub send events](https://drive.google.com/file/d/1YtYf6BCuYXURLaDEw4kslHfh4eHTzUqz/view?usp=sharing)
    - [Event hub partitions](https://drive.google.com/file/d/1oBlf2RiZMS7LPwc116la0vaHaHtV9stw/view?usp=sharing)
    - [Event hub read events](https://drive.google.com/file/d/1jgBIF1aoBfQVq17ZSZMwmXC8Nesf8kPp/view?usp=sharing)
    - [Event hub summary](https://drive.google.com/file/d/1_CP6z3XqILrM5x9dlYl8qJmhsf_KsBHX/view?usp=sharing)
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Event-based Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-event-based-solutions/table-of-contents)

- **Develop Message-Based Solutions**
    - [Implement solutions that use Azure Service Bus](https://github.com/kolosovpetro/ServiceBusTopics.AZ204)
    - [Implement solutions that use Azure Queue Storage Queues](https://github.com/kolosovpetro/StorageQueue.AZ204)
    - [Queue storage architecture](https://drive.google.com/file/d/1HRew1KVT7r9LNXWX6skR5NKEno9G847C/view?usp=sharing)
    - [Queue storage interaction using CLI](https://drive.google.com/file/d/1GKErhpy5hXojBCt7ovClPsWApa4Y4Nu8/view?usp=sharing)
    - [Queue storage use cases](https://drive.google.com/file/d/1o1_SrvxOTzx3f8b2SkZIcoD2nK8iqrq_/view?usp=sharing)
    - [Queue storage create CLI](./MessageBasedSolutions/01_queue_storage_create_cli.md)
    - [Queue storage create Powershell](./MessageBasedSolutions/02_queue_storage_create_powershell.md)
    - [Service bus create CLI](./MessageBasedSolutions/03_service_bus_create_cli.md)
    - [Service bus create Powershell](https://learn.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-powershell)
    - [Service bus architecture](https://drive.google.com/file/d/1jd8JldlkssbO4SmP1Pr1tvhz8dkkxNFz/view?usp=sharing)
    - [Service bus interaction using CLI](https://drive.google.com/file/d/1SFOf9ZrGs7V8hl2Bd5nod6IGnySytgT4/view?usp=sharing)
    - [Service bus use cases](https://drive.google.com/file/d/151aPKhACGEt1ZCnsu75u0BK--ku0dsFj/view?usp=sharing)
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Message-based Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-message-based-solutions/table-of-contents)

- **Notification hubs**
    - [Notification hubs create CLI](./EventBasedSolutions/05_notification_hub_create_cli.md)
    - [Notification hubs create Powershell](./EventBasedSolutions/06_notification_hub_create_powershell.md)
    - [Notification hubs features](https://drive.google.com/file/d/1oNwjXGtXV47wfIBvdLaPOfl1rHl2wPW_/view?usp=sharing)
    - [Notification hubs and namespaces](https://drive.google.com/file/d/1HiWFV5J-qmrnUfYm0mtDTceLb16Xz3Hv/view?usp=sharing)
    - [Notification hubs send notification](https://drive.google.com/file/d/1HpSqZaJAQ5n31lXK0Z3blqsIpKbEKzsW/view?usp=sharing)
    - [Notification hubs register app and send pushes](https://drive.google.com/file/d/1RmSy5rz1F6dFDx5iT11H5pMZThDmSxEP/view?usp=sharing)

- **FAQ**
    - [Event vs Message](https://drive.google.com/file/d/1dN4Shk4730lH3ozyTD2rZIm-IaSyKEzc/view?usp=sharing)
    - [Select Event based solution](https://drive.google.com/file/d/1-RftB3huRtfs94SCYkgCutvG_nV-6ZoM/view?usp=sharing)

- **Quiz**
    - [Event and Messaging Quiz](https://smarturl.it/EVENT_MESSAGING_QUIZ)
    - [APIM Quiz](https://smarturl.it/08_APIM_QUIZ)

- **Exam Alert**
    - [Exam Alert: Connect to and Consume Azure Services and Third-Party Services](https://app.pluralsight.com/library/courses/exam-alert-connect-consume-azure-services-third-party-services/table-of-contents)