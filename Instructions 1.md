# Getting started

## Prerequisites

To be able to follow this tutorial, you will need access to the following things:
- Azure portal
  - Use your own Azure account, or:
  - [Redeem your Azure pass](https://www.microsoftazurepass.com/)
  - [Get a free Azure account](https://azure.microsoft.com/en-us/free/search/?&ef_id=CjwKCAiArJjvBRACEiwA-Wiqq17wZL3A9eAofpFqFkucr_1RgjC_HPmPhawnW7tP0nmQmjyk7MCcaRoCp3UQAvD_BwE:G:s&OCID=AID2000098_SEM_MNHj2pvg&MarinID=MNHj2pvg_368942021164_azure%20free%20account_e_c__78993973800_kwd-300666823650&lnkd=Google_Azure_Brand&dclid=CLT7hr_AmeYCFclh0wody70Hgw)
- PowerApps

## Some notes before continuing

- Make sure all the resources you create exist within the same resource group in Azure. This will make it easier to delete all resources at the end of the tutorial.
- This tutorial consists of instructions and labs. Instructions will guide you to create resources or use tools from Azure by using the GUI. Labs include the script you need to perform other tasks through code in between. Both are needed to follow the tutorial.  


## Step 1 - Bing Search

Create a **single-service** resource for Bing Search v7 in the Azure portal. 
- Get instructions on how to do it [here](https://docs.microsoft.com/en-us/azure/cognitive-services/cognitive-services-apis-create-account?tabs=singleservice%2Cwindows).
- After your resource has been deployed, make sure to save the following information for further use in a notepad file:
  - Key1
  - Endpoint
  
## Step 2 - Azure Notebook

To continue with the labs, you need to get access to Jupyter notebooks and upload the necessary files.
- Navigate to [Azure Notebooks](https://notebooks.azure.com/).
- Sign in with the credentials which have access to Azure.
- Create a new project
- Upload the lab files from this repository: either through the URL or from your computer after you have downloaded and saved them locally.

You are now ready to continue with the Lab 1 in Azure Notebooks.
