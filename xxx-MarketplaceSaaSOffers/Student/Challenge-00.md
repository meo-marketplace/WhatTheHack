# Challenge 00 - Prerequisites - Ready, Set, GO!

**[Home](../README.md)** - [Next Challenge >](./Challenge-01.md)

**_This is a template for "Challenge Zero" which focuses on getting prerequisites set up for the hack. The italicized text provides hints & examples of what should or should NOT go in each section._**

**_We have included links to some common What The Hack pre-reqs in this template. All common prerequisite links go to the WTH-CommonPrerequisites page where there are more details on what each tool's purpose is._**

**_You should remove any common pre-reqs that are not required for your hack. Then add additional pre-reqs that are required for your hack in the Description section below._**

**_You should remove all italicized & sample text in this template and replace with your content._**

## Introduction

Thank you for participating in the MarketplaceSaaSOffers What The Hack. Before you can hack, you will need to set up some prerequisites.

## Prerequisites

You will need the following to complete this hack:

- [Azure Subscription](../../000-HowToHack/WTH-Common-Prerequisites.md#azure-subscription) - a trial or free subscription is all you need to run this hack 
- [Visual Studio Code](../../000-HowToHack/WTH-Common-Prerequisites.md#visual-studio-code)
  - VS Code REST Client Extension from Huachao Mao - add once VS Code is installed
- [Node js](https://nodejs.org/en) - install the version specific to your system. You can check if you have this installed in the CMD prompt / BASH by typing `node -v`.
- [Microsoft Commercial Marketplace API Emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator)

## Description

This challenge will focus on getting your environment set up and ready to hack. You will need to install the tools listed in the prerequisites section above. You will also need to log in to Azure.

The Microsoft Commercial Marketplace API Emulator is a tool that mimics the behaviour of the SaaS Fulfillment APIs. This makes it easy to make changes and doesn't require access to Partner Center. It is important to understand that final testing must always be carried out against the marketplace APIs themselves, the emulator is a tool to accelerate development.

## Success Criteria

- Open VS Code
- In VS Code confirm the version of Node you have installed
- Confirm the REST Client extension is installed
- Login to Azure, at portal.azure.com 
- Verify that the Azure Marketplace API Emulator home page is available at `http://localhost:3978`

## Tips

- The emulator can be run from VSCode or the command line if you have Node.js installed
(see [Prerequisites](./Challenge-00.md))
- If you have Docker installed, the emulator can be run as a Docker container
- If you use Dev Containers with VS Code, you can also use this
- If you already have Docker installed, this may be the simplest way to get the emulator up and running. Similarly, if
you use Dev Containers in VSCode, this is a good route to follow
- More information is in the Readme linked in the Learning Resources section
- If using Docker, make sure to map the port correctly

