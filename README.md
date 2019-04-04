# ARMDeploymentSample 
Azure Resource Management sample

### Prerequisites

**If your powershell is not able to run scripts you need to run following command:**

`Set-ExecutionPolicy -Scope LocalMachine -ExecutionPolicy Bypass`



**Possible issue is the absence of AzureRM module for powershell:**

`Install-Module -Name AzureRM`


**See error by correlationId:**

`Get-AzureRMLog -CorrelationId xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -DetailedOutput`

---

### Main points:

* *deploy.ps1* - Creates new ResourceGroup in Azure under your subscription.
* *template.json* - ARM template describes what resources have to be deployed. Resources described include: Application Insights, Bot Channels Registration, App Service, App Service plan, Storage account, Function, App Service plan for Function, Key Vault.
* *parameters.json* - All the parameters needed to make template easy to maintain.

**List of parameters in deploy.ps1:**

* *subscriptionId* - Guid of your Azure subscription
* *resourceGroupName* - name for Resource Group to create
* *resourceGroupLocation* - location that will be used for group location and all the resources as well
* *deploymentName* - name of deployment that will be shown in deployment section on Azure portal
* *templateFilePath* - path to ARM template
* *parametersFilePath* - path to parameters file for the template
* *chatbotName* - name of the bot

**List of resources in template.json:**
* microsoft.insights/alertrules
* microsoft.insights/components
* Microsoft.KeyVault/vaults
* Microsoft.Storage/storageAccounts
* Microsoft.Web/serverfarms (for App Service)
* Microsoft.Web/serverfarms (for Function)
* Microsoft.Web/sites (App Service)
* Microsoft.Web/sites (Function)
* Microsoft.Web/sites/config (for App Service)
* Microsoft.Web/sites/hostNameBindings (for App Service)
* Microsoft.Web/sites/config (for Function)
* Microsoft.Web/sites/hostNameBindings (for Function)