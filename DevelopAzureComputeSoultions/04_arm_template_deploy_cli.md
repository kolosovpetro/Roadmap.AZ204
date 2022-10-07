# Deploy ARM template using CLI

### Get ARM template via Azure Portal

- Start resource creation, then stop on last stage, do not deploy it
- Download template zip using `Download a template for automation`

![Download_template](./img/09_create_template_portal.png)

- Review and download the template

![Review_template](./img/10_download_template.png)

### Deploy ARM via CLI

- Create resource group
    - `$rgName="rg-ubuntu-vm-arm"`
    - `$location="westus"`
    - `az group create -n $rgName -l $location`
- Deploy template
    - `$templatePath = "./arm_templates/exported-portal-rg-ubuntu-vm/template.json"`
    - `$parametersPath = "./arm_templates/exported-portal-rg-ubuntu-vm/parameters.json"`
    - `az deployment group create -g $rgName --template-file $templatePath --parameters $parametersPath`

### Delete resource group

- `az group delete -n $rgName --yes`