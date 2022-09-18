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
- [Quizlet](https://quizlet.com/)

Both of these resources require paid subscription.
Pluralsight is used in order to get information and then perform practice based on demo sections.
Quizlet is used to grind-core new definitions.

Practice could be achieved using both

- [Pluralsight AZ-204 Demos](https://app.pluralsight.com/paths/certificate/developing-solutions-for-microsoft-azure-az-204)
- [Microsoft Labs](https://microsoftlearning.github.io/AZ-204-DevelopingSolutionsforMicrosoftAzure/)

So, study flow is following

- Theory: `Watch course on pluralsight -> Note definitions -> Create quizlet quiz -> Grind defintions`
- Practice: `Watch cource on pluralsight -> Complete demos of the cource -> Upload results to github`
- Practice: `Complete lab on Microsoft Labs resource`

As a short conclusion, I want to mention that I am also relatively newbie on Azure,
so this study approach is as well an experiment for me, we'll see how it works :)

## Topics covered by AZ-204 exam

AZ-204 consists of five basic modules such that

### 1. Develop Azure Compute Solutions (25-30%)

- **Implement IaaS Solutions**
    - Provision Virtual Machines (VMs)
        - [Create Windows VM using CLI](./DevelopAzureComputeSoultions/06_create_windows_vm_using_cli.md)
        - [Create Linux VM using CLI](./DevelopAzureComputeSoultions/07_create_linux_vm_using_cli.md)
        - [Create Windows VM using Az Powershell](./DevelopAzureComputeSoultions/08_create_windows_vm_using_powershell.md)
    - Configure, validate, and deploy ARM templates
        - [Deploy ARM template using CLI](./DevelopAzureComputeSoultions/09_deploy_arm_template_using_CLI.md)
        - [Deploy ARM template using Az Powershell](./DevelopAzureComputeSoultions/10_deploy_arm_template_using_powershell.md)
    - Configure container images for solutions
    - [Publish an image to the Azure Container Registry](./DevelopAzureComputeSoultions/01_publish_image_to_acr.md)
    - [Run containers by using Azure Container Instance](./DevelopAzureComputeSoultions/05_run_containers_using_instances.md)
    - Pluralsight
      course: [Microsoft Azure Developer: Implement IaaS Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-iaas-solutions/table-of-contents)

- **Create Azure App Service Web Apps**
    - [Create an Azure App Service Web App](./DevelopAzureComputeSoultions/02_create_app_service_cli.md)
    - Enable diagnostic logging
    - [Deploy code to a web app](./DevelopAzureComputeSoultions/03_deploy_code_to_app_service.md)
    - Configure web app settings
    - Implement autoscaling rules, including scheduled autoscaling, and scaling by operational or system metrics
    - Pluralsight
      course: [Microsoft Azure Developer: Create Azure App Service Web Apps](https://app.pluralsight.com/library/courses/azure-developer-create-azure-app-service-web-apps/table-of-contents)

- **Implement Azure Functions**
    - [Create and deploy Azure Functions](./DevelopAzureComputeSoultions/04_create_and_deploy_azure_function.md)
    - Implement input and output bindings for a function
    - Implement function triggers by using data operations, timers, and webhooks
    - Implement Azure Durable Functions
    - Implement custom handlers
    - Pluralsight
      course: [Microsoft Azure Developer: Implement Azure Functions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-azure-functions/table-of-contents)

- **Quiz**
    - [Develop Azure Compute Solutions Quiz]()

- **Exam Alert**
    - [Exam Alert: Develop Azure Compute Solutions](https://app.pluralsight.com/library/courses/exam-alert-develop-azure-compute-solutions/table-of-contents)

### 2. Implement Azure Security (20-25%)

- **Implement User Authentication and Authorization**
    - Authenticate and authorize users by using the Microsoft Identity Platform
    - [Authenticate and authorize users and apps by using Azure Active Directory](https://gist.github.com/kolosovpetro/4e2a830b51422bfce8e5bd951f76d71d)
        - [Single and multi tenant authorization using MVC app](https://github.com/kolosovpetro/OpenIDConnect.AZ204)
        - [Get an AAD token and use it to send messages to a Service Bus queue](https://learn.microsoft.com/en-us/rest/api/servicebus/get-azure-active-directory-token)
        - [Role-based authorization using AAD and two web APIs](https://github.com/kolosovpetro/OpenIDConnect.AZ204.API)
        - [Quick and simple role-based AAD authentication & authorization using JWT tokens](https://github.com/kolosovpetro/QuickAndSimpleApiAuth)
    - Create and implement shared access signatures
    - Pluralsight
      course: [Microsoft Azure Developer: Implement User Authentication and Authorization](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-user-authentication-authorization/table-of-contents)

- **Implement Secure Cloud Solutions**
    - Secure app configuration data by using the App Configuration and Azure Key Vault
    - Develop code that uses keys, secrets, and certificates stored in Azure Key Vault
    - Implement solutions that interact with Microsoft Graph
    - Implement Managed Identities for Azure resources
    - Pluralsight
      course: [Microsoft Azure Developer: Implement Secure Cloud Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-secure-cloud-solutions/table-of-contents)

- **Quiz**
    - [Implement Azure Security Quiz]()

- **Exam Alert**
    - [Exam Alert: Implement Azure Security](https://app.pluralsight.com/library/courses/exam-alert-implement-azure-security/table-of-contents)

### 3. Connect to and Consume Azure Services and Third-party Services (15-20%)

- **Implement API Management**
    - Create an API Management instance
    - Configure authentication for APIs
    - Define policies for APIs
    - Pluralsight
      course: [Microsoft Azure Developer: Implement API Management](https://app.pluralsight.com/library/courses/microsoft-azure-developer-implement-api-management/table-of-contents)

- **Develop Event-Based Solutions**
    - [Implement solutions that use Azure Event Grid](https://github.com/kolosovpetro/EventGridDemo.AZ204)
    - Implement solutions that use Azure Event Hub
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Event-based Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-event-based-solutions/table-of-contents)

- **Develop Message-Based Solutions**
    - [Implement solutions that use Azure Service Bus](https://github.com/kolosovpetro/ServiceBusTopics.AZ204)
    - [Implement solutions that use Azure Queue Storage Queues](https://github.com/kolosovpetro/StorageQueue.AZ204)
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Message-based Solutions](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-message-based-solutions/table-of-contents)

- **Quiz**
    - [Connect to and Consume Azure Services and Third-party Services Quiz]()

- **Exam Alert**
    - [Exam Alert: Connect to and Consume Azure Services and Third-Party Services](https://app.pluralsight.com/library/courses/exam-alert-connect-consume-azure-services-third-party-services/table-of-contents)

### 4. Develop for Azure Storage (15-20%)

- **Develop Solutions that use Cosmos DB Storage**
    - Select the appropriate API and SDK for a solution
    - Implement partitioning schemes and partition keys
    - Perform operations on data and Cosmos DB containers
    - Set the appropriate consistency level for operations
    - Manage change feed notifications
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Solutions with Cosmos DB Storage](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-solutions-cosmos-db-storage/table-of-contents)

- **Develop solutions that use Blob storage**
    - [Move items in Blob storage between storage accounts or containers](./DevelopForAzureStorage/01_move_items_between_blob_accounts.md)
    - [Set and retrieve properties and metadata](https://github.com/kolosovpetro/AzureStorageSDKTraining.AZ204)
    - Perform operations on data by using the appropriate SDK
    - Implement storage policies, and data archiving and retention
    - Pluralsight
      course: [Microsoft Azure Developer: Develop Solutions with Blob Storage](https://app.pluralsight.com/library/courses/microsoft-azure-developer-develop-solutions-blob-storage/table-of-contents)

- **Quiz**
    - [Develop for Azure Storage Quiz]()

- **Exam Alert**
    - [Exam Alert: Develop for Azure Storage](https://app.pluralsight.com/library/courses/exam-alert-develop-azure-storage/table-of-contents)

### 5. Monitor, Troubleshoot, and Optimize Azure Solutions (15-20%)

- **Integrate Caching and Content Delivery Within Solutions**
    - Configure cache and expiration policies for Azure Redis cache
    - Implement secure and optimized application cache patterns including data sizing, connections, encryption, and
      expiration
    - Pluralsight
      course: [Microsoft Azure Developer: Integrate Caching and Content Delivery](https://app.pluralsight.com/library/courses/microsoft-azure-developer-integrate-caching-content-delivery/table-of-contents)

- **Instrument Solutions to Support Monitoring and Logging**
    - Configure an app or service to use Application Insights
    - Analyze and troubleshoot solutions by using Azure Monitor
    - Implement Application Insights web tests and alerts
    - Pluralsight
      course: [Microsoft Azure Developer: Instrument Solutions for Monitoring and Logging](https://app.pluralsight.com/library/courses/microsoft-azure-developer-instrument-solutions-monitoring-logging/table-of-contents)

- **Quiz**
    - [Monitor, Troubleshoot, and Optimize Azure Solutions Quiz]()

- **Exam Alert**
    - [Exam Alert: Monitor, Troubleshoot, and Optimize Azure Solutions](https://app.pluralsight.com/library/courses/exam-alert-monitor-troubleshoot-optimize-azure-solutions/table-of-contents)