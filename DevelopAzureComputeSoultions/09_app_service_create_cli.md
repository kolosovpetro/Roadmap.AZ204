# Create App Service using CLI

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

- Delete resource group
    - `az group delete -n $rgName --yes`