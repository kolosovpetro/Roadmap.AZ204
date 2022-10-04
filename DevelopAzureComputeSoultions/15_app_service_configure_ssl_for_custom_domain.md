# Configure SSL for custom domain

It is assumed that you have already configured your custom domain for web app under specified app service plan.
It not -- proceed to [App service add custom domain](./14_app_service_add_custom_domain.md)

### Go to SSL/TSL settings, bindings blade in Azure Portal

![azure_bindings](./img/custom-domains/06_ssl_binding_azure_portal.PNG)

### Click `Create App Service Managed Certificate`

![app_managed_cert_portal](./img/custom-domains/07_create_app_managed_cert_portal.PNG)

### Go back to Custom domains blade, add binding

![back_custom_domains](./img/custom-domains/08_back_to_custom_domains.PNG)

![add_binding](./img/custom-domains/09_add_binding_recently_created_cert.PNG)

### Check certificate

![check_cert](./img/custom-domains/10_check_certificate.PNG)