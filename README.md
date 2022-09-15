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
    - Configure, validate, and deploy ARM templates
    - Configure container images for solutions
    - [Publish an image to the Azure Container Registry](./DevelopAzureComputeSoultions/01_publish_image_to_acr.md)
    - Run containers by using Azure Container Instance
- **Create Azure App Service Web Apps**
    - Create an Azure App Service Web App
    - Enable diagnostic logging
    - Deploy code to a web app
    - Configure web app settings
    - Implement autoscaling rules, including scheduled autoscaling, and scaling by operational or system metrics
- **Implement Azure Functions**
    - Create and deploy Azure Functions
    - Implement input and output bindings for a function
    - Implement function triggers by using data operations, timers, and webhooks
    - Implement Azure Durable Functions
    - Implement custom handlers

### 2. Implement Azure Security (20-25%)

- **Implement User Authentication and Authorization**
    - Authenticate and authorize users by using the Microsoft Identity Platform
    - Authenticate and authorize users and apps by using Azure Active Directory
    - Create and implement shared access signatures
- **Implement Secure Cloud Solutions**
    - Secure app configuration data by using the App Configuration and Azure Key Vault
    - Develop code that uses keys, secrets, and certificates stored in Azure Key Vault
    - Implement solutions that interact with Microsoft Graph
    - Implement Managed Identities for Azure resources

### 3. Connect to and Consume Azure Services and Third-party Services (15-20%)

- **Implement API Management**
    - Create an API Management instance
    - Configure authentication for APIs
    - Define policies for APIs
- **Develop Event-Based Solutions**
    - Implement solutions that use Azure Event Grid
    - Implement solutions that use Azure Event Hub
- **Develop Message-Based Solutions**
    - Implement solutions that use Azure Service Bus
    - Implement solutions that use Azure Queue Storage Queues

### 4. Develop for Azure Storage (15-20%)

- **Develop Solutions that use Cosmos DB Storage**
    - Select the appropriate API and SDK for a solution
    - Implement partitioning schemes and partition keys
    - Perform operations on data and Cosmos DB containers
    - Set the appropriate consistency level for operations
    - Manage change feed notifications
- **Develop solutions that use Blob storage**
    - Move items in Blob storage between storage accounts or containers
    - Set and retrieve properties and metadata
    - Perform operations on data by using the appropriate SDK
    - Implement storage policies, and data archiving and retention

### 5. Monitor, Troubleshoot, and Optimize Azure Solutions (15-20%)

- **Integrate Caching and Content Delivery Within Solutions**
    - Configure cache and expiration policies for Azure Redis cache
    - Implement secure and optimized application cache patterns including data sizing, connections, encryption, and
      expiration
- **Instrument Solutions to Support Monitoring and Logging**
    - Configure an app or service to use Application Insights
    - Analyze and troubleshoot solutions by using Azure Monitor
    - Implement Application Insights web tests and alerts
