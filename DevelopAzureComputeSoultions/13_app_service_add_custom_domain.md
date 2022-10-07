# App Service add custom domain

### 1. Create web app (B1 to have domains + SSL)

- Create resource group
    - `$rgName="rg-app-service-cli"`
    - `$location="centralus"`
    - `az group create -n $rgName -l $location`

- Create app service plan
    - `$planName="appserviceplan"`
    - `az appservice plan create -g $rgName -n $planName --sku "F1"`
    - Available values for sku:
        - `B1, B2, B3, D1, F1, FREE, I1, I1v2, I2, I2v2, I3, I3v2, P1V2, P1V3, P2V2, P2V3, P3V2, P3V3, S1, S2, S3, SHARED, WS1, WS2, WS3`

- Check available app service runtimes
    - `az webapp list-runtimes`

- Create app service
    - `$appName="apipkolosovcli"`
    - `$runtime="dotnet:6"`
    - `az webapp create -g $rgName -n $appName --plan $planName --runtime $runtime`

### 2. Add custom domain

- Azure Portal

![portal_add_domain](./img/custom-domains/01_add_azure_portal.PNG)

![validate_domain_portal](./img/custom-domains/04_domain_name_validation_portal.PNG)

### Configure Cloudflare

![domain_cloudflare](./img/custom-domains/02_cloudflare_config.PNG)

### Domain added successfully

![domain_added](./img/custom-domains/03_custom_domain_added.png)

### Check domain in browser

![check_browser](./img/custom-domains/05_check_in_browser.PNG)