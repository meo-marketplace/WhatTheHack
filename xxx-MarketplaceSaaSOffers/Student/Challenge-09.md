# Challenge 09 - Landing page Single Sign On

[< Previous Challenge](./Challenge-08.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-10.md)

## Introduction

In the vast majority of cases, a SaaS solution will need to know some information about the current user in order to ensure they are allowed to use the application.

*Note: This hack will not extend into configured Single-Sign-On into your own solution and will focus only on meeting the requirements of the landing page and checking that a particular tenant has access to the solution*

## Description

There are two scenarios covered in this challenge. The first is to satisfy the requirement of checking the beneficiary is present when activating the subscription (i.e. the correct user has signed into the landing page) and the second is to sign in a user and check whether they are allows to use the application.

**Configuration and Code Tracks**

- Define an Azure Active Directory App Registration
- Ensure that this is multi-tenant
- Configure the return URL for a Single Page Application as `{your base uri}/saas.html` and `{your base uri}/landing.html` replacing `{your base uri}` with the URI your sample app is running on
- Configure the MSAL_CLIENT_ID and MSAL_REDIRECT_BASEURI values appropriately

**Code Track**

- Replace the alert ("Challenge 09 - SSO") with the code to sign in a user with a work account
- Do this in both the `landing.html` and `saas.html` pages

## Success Criteria

To complete this challenge successfully, you should be able to:
- Verify that a user is signed into the landing page _before_ the subscription is activated and an entitlement is assigned
- Verify that the entitlement has been assigned to the correct tenant by checking the values on the `entitlements.html` page of the sample app
- Sign a user into the `saas.html` page to check whether they have an entitlement assigned to them and are allowed to access the solution.

## Learning Resources

- [Azure Active Directory App Registration](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)