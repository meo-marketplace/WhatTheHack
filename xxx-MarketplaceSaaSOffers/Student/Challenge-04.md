# Challenge 04 - Activate!

[< Previous Challenge](./Challenge-03.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-05.md)

## Pre-requisites

You must have completed **Challenge 03 - Decoding purchase tokens**

## Introduction

Now that we've resolved (decoded) the purchase token on our landing page, the next step is to activate the subscription.
As seen in the Emulator challenge you would typically present some key properties from the decoded purchase to the customer on the landing and ask them to
complete any additional details required for onboarding to your solution.

When the customer submits the form, they are finalising the "purchase". You, as the ISV, then complete whatever steps
are necessary to onboard them as a new customer. This can be an automated provisioning process or a set of manual steps.
Once completed, you call the marketplace activate API to indicate that the customer has been onboarded, their service
is available and billing should commence.

## Description
In this challenge we will activate a subscription, take note of where the actions are taken and where the changes happen, now that the Landing Page has been "removed" from the Emulator this is your asset updating what will be the Azure Marketplace in the live scenario.
 
**Configuration Track**
- Create a new purchase
- Use a meaningful subscription name, something relevant to this challenge, e.g. preface with "C4-"
- Resolve as before - note the subscription state in the Emulator
- Activate in the Sample App - note the subscription state change

**Code Track**
In this challenge you will implement a server-side method to call the marketplace `activate` API. We will keep things
simple; we wont collect any additional customer details and we wont concern ourselves (at this stage) about taking
"whatever steps are necessary to onboard them as a new customer". We will assume that's been handled elsewhere.

The client-side function is already implemented for you as `activateButtonClick()` in `landing.html`. This calls
`api/activate` which is the API we need to implement. Routing has been configured to route POST requests to `api/activate`
to the TypeScript function `activateSubscription()` defined in `src/service/api.ts`, under `// Challenge 04 - Activate!`.

In this challenge we will only be concerned with the function `activateSubscription()` in `src/service/api.ts`. The function
currently has an empty implementation.

Your task it to update the `activateSubscription()` implementation to call the marketplace `activate` API and return the
result to the caller handling any errors along the way.

The emulator should be available on `http://localhost:3978`

- Validate the request (check the necessary parameters)
- Call the marketplace `activate` API
- Check the result and return an appropriate status code
- If the call is successful, return the response status and body (which will be displayed on the landing page)

## Success Criteria

To complete this challenge successfully, you should be able to:
- With the landing page set to the Sample App (from a previous challenge) confirm the new subscription status is set to "Subscribed" in the Emulator subscriptions list

## Learning Resources

- [Marketplace activate API](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-subscription-api#post-httpsmarketplaceapimicrosoftcomapisaassubscriptionssubscriptionidactivateapi-versionapiversion)
- [README for the marketplace emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator/blob/main/README.md)
- [Configuring the emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator/blob/main/docs/config.md)
- [Intro to TypeScript](https://www.typescriptlang.org/docs/)
- [The Express request object](http://expressjs.com/en/4x/api.html#req)

## Tips
