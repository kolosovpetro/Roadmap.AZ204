# Deploy code to app service

### 1. Create web app

- Create resource group `az group create --name "rg-app-service" --location "centralus"`
- Create app service
  plan: `az appservice plan create --name "appserviceplan" --resource-group "rg-app-service" --sku "F1"`
    - Available values for
      sku: `B1, B2, B3, D1, F1, FREE, I1, I1v2, I2, I2v2, I3, I3v2, P1V2, P1V3, P2V2, P2V3, P3V2, P3V3, S1, S2, S3, SHARED, WS1, WS2, WS3`
- Check available app service runtimes: `az webapp list-runtimes`
- Create app
  service: `az webapp create --resource-group "rg-app-service" --name "apipkolosov" --plan "appserviceplan" --runtime '"DOTNETCORE|3.1"'`

### 2. Build project and create zip archive

- Publish: `dotnet publish --configuration Release --output .\bin\publish`
- Create zip via powershell: `Compress-Archive .\bin\publish\* .\app.zip -Force`

### 3. Deploy

- Deploy via
  CLI: `az webapp deployment source config-zip --resource-group "rg-app-service" --src "app.zip" --name "apipkolosov"`