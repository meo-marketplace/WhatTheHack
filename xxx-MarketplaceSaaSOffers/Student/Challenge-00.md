# Challenge 00 - Prerequisites - Ready, Set, GO!

**[Home](../README.md)** - [Next Challenge >](./Challenge-01.md)

## Introduction

Thank you for participating in the Marketplace SaaS Offers What The Hack. Before you can hack, you will need to set up some prerequisites.

**Note:** Other than the Sample App .zip file, all of the prerequisites are common to both configuration and code tracks.  
There are a number of ways to deploy and run the Emulator, please keep to the methods provided for ease of troubleshooting, should you need support from the coach.

## Prerequisites

You will need the following to complete this hack:

- [Azure Subscription](../../000-HowToHack/WTH-Common-Prerequisites.md#azure-subscription) - a trial or free subscription is all you need to run this hack 
- [Visual Studio Code](../../000-HowToHack/WTH-Common-Prerequisites.md#visual-studio-code)
  - [VS Code REST Client Extension](#vs-code-rest-client-extension)
- [Git](../../000-HowToHack/WTH-Common-Prerequisites.md#git)
- [Node js](#node-js)
- [Microsoft Commercial Marketplace API Emulator](#microsoft-commercial-marketplace-api-emulator)
- [Install the sample app](#sample-app) from the .zip file provide for the track you want to do


### VS Code REST Client Extension
You will need VS Code installed and open to install the REST Client extension. You have two options to install the extension:
- In VS Code, on the left bar, select the Extensions icon (Ctrl+Shift+X) and search for REST Client (from Huachao Mao). Select the extension and click Install.
**or**
- [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) in the Visual Studio Marketplace

### Node js
Both the Emulator and the Sample App require Node js to run.

To check if you have this installed use the CMD prompt / BASH and type `node --version` to get the installed version, if you get nothing it needs installing (post install the package it is worth checking re-running the version check).

To install Node js use the following link and follow the instructions for your OS.
[Node js](https://nodejs.org/en) 


### Microsoft Commercial Marketplace API Emulator
You need Git to install and Node to run the Emulator, get those now if you have not already. 

[Microsoft Commercial Marketplace API Emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator) GitHub repo

- if you are familiar with Git, clone the repo
- if you are new to Git follow the instructions below:
  - Create a folder on your local machine to hold the emulator
  - Open VS Code
  - Open the folder you created
  - Open the Terminal in VS Code, to do this use the menu Terminal > New Terminal
  - In the Terminal type the following commands
    - `git init`
    - `git clone https://github.com/meo-marketplace/wth-sample-app.git`


The above will give you the base install of the Emulator you will need to install the dependencies to run it. In the Terminal type the following commands:

- `cd Commercial-Marketplace-SaaS-API-Emulator`
- `npm build`

You should now see the Node modules folder in the directory (in the left panel of VS Code), you are now ready to run the emulator.

For this hack we will be running the Emulator (and Sample App) from the VS Code debugger. To start the Debugger either:
- Press F5
- Use the top menu Run > Start Debugging
- Click the 'Run and Debug' icon on the left bar and select the green arrow

You should see the Emulator home page at `http://localhost:3978`

### Sample App
The coach will provide a .zip file for the track you are on - **code** or **configuration**, identified by the file name.

- Unzip the file to a folder on your local machine (we suggest the location as the Emulator **folder** - which should only see the Commercial Marketplace SaaS API Emulator folder, if you are seeing a lot of files and folders, move up a level)
- In VS Code click File > New Window
- In the Explorer pane on the left open the folder you unzipped the Sample App to
- Open the Terminal in VS Code, to do this use the top menu Terminal > New Terminal or use the shortcut `Ctrl + '`
- Type the following command to complete the install
  - `npm build`

You should now see the Node modules folder in the Explorer pane, you are now ready to run the Sample App.

For this hack we will be running the Sample App (and Emulator) from the VS Code debugger. To start the Debugger either:
- Press F5
- Use the menu Run > Start Debugging
- Click the 'Run and Debug' icon on the left bar and select the green arrow

You should see the Sample App home page at `http://localhost:3000`


### Success Criteria

- Open VS Code
- In VS Code confirm the version of Node you have installed
- Confirm the REST Client extension is installed
- Login to Azure, at portal.azure.com 
- Verify that the Azure Marketplace API Emulator home page is available at `http://localhost:3978`
- Verify the Sample app is available on `http://localhost:3000`

