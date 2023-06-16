# Challenge 10 - Authenticating with marketplace APIs

[< Previous Challenge](./Challenge-09.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-11.md)

## Introduction

The SaaS Emulator doesn't require authentication when calling the emulated APIs, however the real SaaS Fulfillment APIs do!

Authentication is handled using an Azure Active Directory bearer token (JWT) in the Authentication header of requests to the APIs. And in order to obtain this token, there needs to be some configuration.

## Description

In this challenge we will configure a second App Registration that will be used to obtain an "App token" and call the emulated marketplace APIs securely. Unlike the previous App Registration, this one should be "single-tenant" as it will only ever be called by your own backend code and the token will always be used to access the marketplace APIs as your own tenant.

**Configuration and Code Tracks**

- Create a second Azure App Registration in Azure Active Directory. 
- Configure the Emulator to use the Client ID and Secret for the purposes of authentication, in the same `.env` file as the other coded configuration settings.

**Code Track**

- Obtain an App token from Azure Active Directory
- Add this to _all_ requests being made to the emulator

## Success Criteria

To complete this challenge successfully, you should be able to:
- Verify that "Requires Auth" has been enabled on the emulator by checking the UI
- Make a purchase and activate the subscription, ensuring that the calls to the emulator succeed

## Learning Resources

- [Obtain an access token for the Marketplace SaaS APIs](https://learn.microsoft.com/en-us/partner-center/marketplace/partner-center-portal/pc-saas-registration#how-to-get-the-publishers-authorization-token)
