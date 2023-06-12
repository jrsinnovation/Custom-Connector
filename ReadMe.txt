## HVI Inspection Specific Vehicle
## Name of connector 
Particular Vehicle Inspection Data
HVI, is an inspection information capture technology. HVI customer can bring inspection and maintenance process data to Microsoft apps.
HVI collects fleet breakdown information in Realtime and via the custom connector, such information can be retrieved.
All inspection information is available for any fleet vehicle or construction equipment. 

## Description( Information about Hvi NEED TO CHECK)
HVI, is an inspection information capture technology. HVI customer can bring inspection and maintenance process data to Microsoft apps. 
HVI collects fleet breakdown information in Realtime and via the custom connector, such information can be retrieved.
All inspection information is available for any fleet vehicle or construction equipment. 

## Prerequisites
You will need the following to proceed:
* A Microsoft Power Apps or Power Automate plan with custom connector feature.
* HVI Subscription Account
* Authentication API KEY(Which is basically HVI Account password).

## How to get an Hvi Account?
-Visit the HVI Official website https://heavyvehicleinspection.com/
-Sign up free for HVI account. Click on Web portal login button on the top-right corner.
-You can login with Gmail or manually type the credentials.
-You are all set with a new Hvi Account.


## Supported Operations
The connector supports the following operations:
* `Particular Vehicle Inspection Data`: Get all the Inspection data of a particular vehicle in a time Frame that is provided.

 
## Parameters
* `sv`: Default value is 1.0.
* `Email ID`: User HVI email that is unique for every user.
* `API KEY`: It is provided by the HVI support Team at the time of account creation that is used to uniquely identify the users.
* `Vehicle Number`: Vehicle number for which inspection data is needed.
* `Start Date`: Starting Date from which user want the inspection detail of the Vehicle.
* `End Date`: Ending Date from within which user want the inspection detail of the vehicle. 












SAMPLE FROM WHICH WE NEED TO PREPARE THE FILE

## Azure Key Vault [Sample] Connector
Azure Key Vault provides a powerful and very extensive REST API.  Using this API, you can manage your keys, certificates, and secrets in an Azure Key Vault account.  Very often, you may want to leverage those secrets in your application, or in your process automation.



## Prerequisites
You will need the following to proceed:
* A Microsoft Power Apps or Power Automate plan with custom connector feature
* An Azure subscription
* The Power platform CLI tools

## Building the connector 
Since Key Vault APIs are secured by Azure Active Directory (AD), we first need to set up a few thing in Azure AD so that our connectors can securely access the Key Vault.  After that is completed, you can create and test the sample connector.

### Set up an Azure AD application for your custom connector
We first need to register our connector as an application in Azure AD.  This will allow the connector to identify itself to Azure AD so that it can ask for permissions to access Key Vault data on behalf of the end user.  You can read more about this [here](https://docs.microsoft.com/en-us/azure/active-directory/develop/authentication-scenarios) and follow the steps below:

1. Create an Azure AD application
This Azure AD application will be used to identify the connector to Azure Key Vault.  This can be done using [Azure Portal] (https://portal.azure.com), by following the steps [here](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).  Once created, note down the value of Application (Client) ID.  You will need this later.

2. Configure (Update) your Azure AD application to access the Azure Key Vault API
This step will ensure that your application can successfully retrieve an access token to invoke Azure Key Vault on behalf of your users.  To do this, follow the steps [here](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis).
    - For redirect URI, use “https://global.consent.azure-apim.net/redirect”
    - For the credentials, use a client secret (and not certificates).  Remember to note the secret down, you will need this later and it is shown only once.
    - For API permissions, make sure “Azure Key Vault” and “user_impersonation” are added.
   
At this point, we now have a valid Azure AD application that can be used to get permissions from end users and access Azure Key Vault.  The next step for us is to create a custom connector.

### Deploying the sample
Run the following commands and follow the prompts:

```paconn
paconn create --api-def apiDefinition.swagger.json --api-prop apiProperties.json --secret <client_secret>
```

## Supported Operations
The connector supports the following operations:
* `List keys`: List keys in the specified vault
* `Get key`: Gets the public part of a stored key
* `Create key`: Creates a new key
* `Decrypt data`: Decrypts a single block of encrypted data
* `Encrypt data`: Encrypts an arbitrary sequence of bytes using an encryption key
* `List secrets`: List secrets in a specified key vault
* `Get secret`: Get a specified secret from a given key vault
* `Create or update secret value`: Sets a secret in a specified key vault
* `List secret versions`: List all versions of the specified secret
* `Get secret version`: Get the value of a specified secret version from a given key vault



