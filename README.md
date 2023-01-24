---
title: 'Step-by-step: Create a static web app using DevOps'
description: Learn to deploy an Azure Static Web App using DevOps
services: static-web-apps
author: beatrizmartins
ms.author: bemartins
ms.date: 01/24/2023
ms.topic: step-by-step
ms.service: static-web-apps
zone_pivot_groups: devops
---

# Step-by-step: Publish and Angular App with Azure Static Web Apps using DevOps

Azure Static Web Apps publishes a website to a production environment by building apps from an Azure DevOps or GitHub repository. In this step-by-step guide, you will deploy a web application to Azure Static Web apps using DevOps.

## Required

- An Azure subscription
- A DevOps organization

## Create a repository

This article uses a GitHub repository to make it easy for you to get started. The repository features a starter app used to deploy using Azure Static Web Apps.

1. Log in in Azure DevOps: [DevOps](https://dev.azure.com/)
2. Create a **New Project**
3. Add the following **properties** (expand **Advanced**):

    | Properties | Value |
    |--|--|
    | Name | **my-first-web-static-app** |
    | Description | Your choice ||
    | Visibility | Your choice |
    | Version control | **Git**  |
    | Work item process | Your choice |

4. Click on **Create Project**
5. Choose **Repos** as the service type
6. The files tab will be opened automatically. Click on the **Import** button in the Import a repository section
7. Choose your template and copy its URL. In this case we are using an Angular template: [https://github.com/staticwebdev/angular-basic.git](https://github.com/staticwebdev/angular-basic.git)
8. Click on **Import**
9. Once the import is successful, you can check the content files of the repository

## Create a static web app

Now, we need to connect the repository created in DevOps to a static web app created using your Azure Subscription. This is done through the Azure Portal.

1. Log in in the Azure Portal [Azure portal](https://portal.azure.com)
2. Click on **Create a Resource**
3. Search for **Static Web Apps** in the search bar
4. Click on **Create > Static Web App**
5. Add the following properties:

| Properties | Value |
|--|--|
| Subscription | Your Azure subscription |
| Resource Group | Click on **Create new** and enter **static-web-apps-test** |
| Name | **my-first-static-web-app** |
| Plan type | **Free** |
| Azure Functions and staging details | Your choice |
| Source | **DevOps** |
| Organization | Select your organization |
| Repository| Select the repository you created. In this case **my-first-web-static-app** |
| Branch | **main** |
| Build presets | Select the framework on your template. In this case we choose **Angular** |
| App location | Select your location. In this case it is the default value, **"/"** |
| Api location | Empty as there is no API. In case of an API, insert its location here |
| App artifact location | Select your location. In this case **"dist/angular-basic"** |

6. Click on **Review + Create > Create**
7. Once the deployment is complete, click on **Go to Resource** and then on *Browse* to see your static web app.
