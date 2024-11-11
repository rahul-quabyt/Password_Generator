# MirrorReco 

This repository is a monorepo containing multiple sub-projects, including the Mirror Reco application, which has both frontend and backend components.

## Table of Contents
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
- [Frontend Setup](#frontend-setup)
  - [Install Bun](#install-bun)
  - [Environment Variables](#environment-variables)
  - [Running the Frontend](#running-the-frontend)
- [Backend Setup](#backend-setup)
  - [Opening in Visual Studio](#opening-in-visual-studio)
  - [Environment Configuration](#environment-configuration)
  - [Running the Backend](#running-the-backend)
- [Conclusion](#conclusion)

---

## Project Structure

This monorepo includes the following sub-projects:
- **mirror-reco**: The Mirror Reco project, containing both frontend and backend code.
  - **frontend**: Frontend code for the Mirror Reco application.
  - **backend**: Backend code for Mirror Reco, located under `CompactAccounting.MirrorReco.Services`.

---

## Getting Started

### Prerequisites

Ensure you have the following prerequisites installed:
- **Node.js**: For managing dependencies and running the project.
- **Bun**: Required to run the frontend application.
- **Visual Studio**: Needed to open and run the backend solution file.

---

## Frontend Setup

The frontend of Mirror Reco is located in the `mirror-reco/frontend` directory. Follow the steps below to configure and run the frontend application.

### Install Bun

To run the frontend application, you need to install [Bun](https://bun.sh/) on your system. You can install it using either npm or a shell script.

#### Using npm

Run the following command to install Bun globally:

```bash
npm install -g bun
```

#### - Using Script
Alternatively, you can install Bun by running the following command in your terminal:

```bash
curl -fsSL https://bun.sh/install | bash
```

After installation, verify it by running:

```bash
bun --version
```
### Environment Variables

Create a `.env.development` file under the `frontend` folder and add the following environment variables:

``` env
VITE_PUBLIC_MSAL_CLIENT_ID=""
VITE_PUBLIC_AZURE_AD_TENANT_ID=""
VITE_PUBLIC_MSAL_REDIRECT_URL=""
VITE_PUBLIC_STORAGE_ACCOUNT_NAME=""
VITE_PUBLIC_STORAGE_CONTAINER_NAME=""
VITE_PUBLIC_STORAGE_TENANT_TABLE_NAME=""
VITE_PUBLIC_SAS_TOKEN=""
VITE_PUBLIC_FUNCTION_URL=""
VITE_FUNCTION_MIRRORRECO_API_URL=""
```
These variables are necessary to configure the frontend to connect with the backend and other services.

### Running the Frontend

To start the frontend, open your terminal and navigate to the frontend directory. Run the following command:

```
bun dev --port 3000
```

This will start the frontend server on http://localhost:3000.

---

### Backend Setup
The backend for Mirror Reco is located in backend/CompactAccounting.MirrorReco.Services. It includes a solution file (.sln) that can be opened in Visual Studio.

### - Opening in Visual Studio
Navigate to backend > CompactAccounting.MirrorReco.Services and open CompactAccounting.MirrorReco.Services.sln with Visual Studio.

### - Environment Configuration
Before running the backend, you need to create a local.settings.json file in the MirrorReco.Functions directory (located at backend > CompactAccounting.MirrorReco.Services > MirrorReco.Functions).

local.settings.json Configuration
Add the following code to your local.settings.json file:

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

### Running the Backend
After setting up your local.settings.json, simply run the solution file (CompactAccounting.MirrorReco.Services.sln) in Visual Studio to start the backend service.

---

### Conclusion
You are now ready to work on the Mirror Reco project!
