# Easy Data - Mono Repo with Front-End and Back-End

This repository is a monorepo containing multiple sub-projects, including the Mirror Reco application, which has both frontend and backend components.

## Table of Contents
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
- [Frontend Setup](#frontend-setup)
  - [Install Yarn](#install-yarn)
  - [Install Dependencies](#install-dependencies)
  - [Configure Environment Variables](#configure-environment-variables)
  - [Run the Frontend](#run-the-frontend)
- [Backend Setup](#backend-setup)
  - [Open Project in Visual Studio](#open-project-in-visual-studio)
  - [Configure Environment Variables](#configure-environment-variables-1)
  - [Run the Backend](#run-the-backend)
- [Conclusion](#conclusion)

### Getting Started

This guide will help you set up and run the Easy Data project locally.

**Prerequisites:**

* Node.js and npm (or yarn)
* Visual Studio (for back-end)

---

### Frontend Setup

#### - Install Yarn:

Follow the official instructions for your operating system: https://classic.yarnpkg.com/lang/en/docs/cli/install/

#### - Install Dependencies:

Navigate to the `web-vite` directory.
Run the following command to install dependencies:

```bash
yarn install
```

### Configure Environment Variables:
Create a file named .env.development in the web-vite folder.
Add the following environment variables to the file (replace with your actual values):

``` env
VITE_PUBLIC_MSAL_CLIENT_ID=""
VITE_PUBLIC_AZURE_AD_TENANT_ID=""
VITE_PUBLIC_MSAL_REDIRECT_URL=""
VITE_PUBLIC_STORAGE_ACCOUNT_NAME=""
VITE_PUBLIC_STORAGE_CONTAINER_NAME=""
VITE_PUBLIC_STORAGE_TENANT_TABLE_NAME=""
VITE_PUBLIC_STORAGE_JOB_STATUS_TABLE_NAME=""
VITE_PUBLIC_START_PROCESSING_QUEUE_NAME=""
VITE_PUBLIC_SERVICEBUS_QUEUE_NAME=""
VITE_PUBLIC_SAS_TOKEN=""
VITE_PUBLIC_SIGNALR_KEY=""
VITE_PUBLIC_SIGNALR_ENDPOINT=""
VITE_PUBLIC_SIGNALR_HUBNAME=""
VITE_PUBLIC_SERVICEBUS=""
VITE_FUNCTION_API_URL=""
```

### Run the Frontend:
Open a terminal in the web-vite directory.
Run the following command to start the development server:

``` bash
yarn dev
```
---

### Backend Setup
#### Open Project in Visual Studio:
Navigate to the services/CompactAccounting.EasyData.Services directory.
Open the file named CompactAccounting.EasyData.Services.sln with Visual Studio.

#### Configure Environment Variables:
Create a file named local.settings.json inside the EasyData.Functions folder (located within services/CompactAccounting.EasyData.Services/EasyData.Functions).
Paste the following code into the local.settings.json file, replacing the placeholders with your actual values:

``` json
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "",
    "FUNCTIONS_WORKER_RUNTIME": "",
    "StorageConnectionString": "",
    "storageAccountName": "",
    "blobContainerName": "",
    "formRecognizerKey": "",
    "jobStatusTableName": "",
    "startQueueName": "",
    "ServiceBusQueueName": "",
    "managedIdentityClientID": "",
    "ServiceBusConnectionString": "",
    "SignalRConnectionString": "",
    "SendGridAPIKey": "",
    "GrpcChannelUri": "",
    "APPINSIGHTS_INSTRUMENTATIONKEY": ""
  },
  "Host": {
    "LocalHttpPort": 7500,
    "CORS": "*",
    "CORSCredentials": false
  }
}
```
This configuration allows the backend to connect to required services and APIs for local development.

#### Run the Back-End:
After setting up your local.settings.json, simply run the solution file (CompactAccounting.EasyData.Services.sln) in Visual Studio to start the backend service.

---

### Conclusion
You are now ready to work on the Easy Data project!
