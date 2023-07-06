# Challenge 10 - Optional - Exploring the APIs

[< Previous Challenge](./Challenge-09.md) - **[Home](../README.md)**

## Pre-requisites 

Complete Challenge 4 to have a working understanding of implementing an API.

## Introduction

So far you have the curated experience calling the APIs through the Emulator UI and built out an API call to activate a subscription, from which you should have an understanding of the parameters required to call the APIs directly. The next stage is to review the API requests and responses across the subscription workflow, the next level of depth, to know what you are building for your own integrations. 

## Description
In this challenge we will use the REST APIs in the Emulator project to run through the workflow.

**Configuration Track**
This challenge is optional but recommended, to get a sense of the workflow, the exchange between the Landing Page and the Emulator. The challenge looks and feels like a code track but is adding values on a VS Code page.

**Code Track**
Open the cloned Emulator project in VS Code.

For this challenge you will need the **VS Code 'REST client' extension**. To check that it is installed select Extensions from the vertical toolbar on the left or Ctrl+Shift+X. 
You should see the REST Client listed in the **INSTALLED** Extensions. 
If the extension is not present refer to **Challenge 0**.

You will need the following in place to complete the challenge: 
- at least one active per user subscription in the Emulator
- a Marketplace Purchase token from the Emulator; when you generate the token select to Copy to Clipboard.
- the file `rest_calls/subscription-apis.http` open in VS Code.

Work through the following: 
- Use a Token in the Emulator to resolve and activate using the **REST APIs in VS Code**
- Using VS Code update the quantity and plan for an existing Subscription
- Exercise all Subscription APIs in the VS Code 

## Success Criteria

To complete this challenge successfully, you should be able to:
- Resolve a Marketplace Purchase token using the REST APIs
- Activate a subscription using the APIs only
- Exercise APIs against an existing Subscription created in the Emulator
- Validate the JSON returned from API calls
- Explain the different between Purchaser and Beneficiary - included in the Resolve Response

## Learning Resources

- [SaaS fulfillment Subscription APIs v2 in Microsoft commercial marketplace](https://learn.microsoft.com/en-gb/partner-center/marketplace/partner-center-portal/pc-saas-fulfillment-subscription-api)


## Tips
- Confirm all settings in the .http file - some values will vary from standard configuration to your environment
- Pay attention to variables in API request strings - served via environment variables and request body
