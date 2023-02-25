# Challenge 05 - Activate!

[< Previous Challenge](./Challenge-04.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-06.md)

## Pre-requisites

You must have completed **Challenge 04 - Decoding purchase tokens**

## Introduction

Now that we've resolved (decoded) the purchase token on our landing page, the next step is to activate the subscription.
Typically, you might present some key properties from the decoded purchase to the customer on the landing and ask them to
complete any additional details required for onboarding to your solution.

When the customer submits the form, they are finalising the "purchase". You, as the ISV, then complete whatever steps
are necessary to onboard them as a new customer. This can be an automated provisioning process or a set of manual steps.
Once completed, you call the marketplace activate API to indicate that the customer has been onboarded, their service
is available and billing should commence.

## Description

In this challenge you will implement a server-side method to call the marketplace `activate` API. We will keep things
simple; we wont collect any additional customer details and we wont concern ourselves (at this stage) about taking
"whatever steps are necessary to onboard them as a new customer". We will assume that's been handled elsewhere.

The client-side function is already implemented for you as `activateButtonClick()` in `landing.html`. This calls
`api/activate` which is the API we need to implement. Routing has been configured to route POST requests to `api/activate`
to the TypeScript function `activateSubscription()` defined in `src/service/api.ts`.

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

- Make sure the emulator is running & start your application
- Make sure the Landing Page URL is set to point to your application landing page
- Navigate to your landing page and click "Activate Purchase"
  - Confirm that your app does not crash, a suitable message is displayed and the error is logged to the console
- Switch to the emulator, generate a token and click "Post to landing page"
  - Confirm that you are directed to your landing page
- On your landing page
  - Click "Get token from query string"
  - Click "Resolve token"
- Switch to the emulator "Subscriptions" page
  - Confirm that your subscription is listed and is in "Pending" status
- Click "Activate Purchase" on your landing page
  - Confirm the subscription staus changes to "Subscribed" (may require refresh)

## Learning Resources

- [Marketplace activate API](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-subscription-api#post-httpsmarketplaceapimicrosoftcomapisaassubscriptionssubscriptionidactivateapi-versionapiversion)
- [README for the marketplace emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator/blob/main/README.md)
- [Configuring the emulator](https://github.com/microsoft/Commercial-Marketplace-SaaS-API-Emulator/blob/main/docs/config.md)
- [Intro to TypeScript](https://www.typescriptlang.org/docs/)
- [The Express request object](http://expressjs.com/en/4x/api.html#req)

## Tips

- **publisherId** - to call the marketplace APIs, the marketplace needs to know the identity of the caller. Ordinarily
this would be extracted from the AAD bearer token. With the emulator, we don't require AAD so we need some other
way of providing an identity. We do this by adding a query string parameter `publisherId` on the request. For more
details, see the emulator README.
- In the application, a `publisherId` is available on the `Config` type, available at `req.app.locals.config`
- `Config` also contains a `baseUrl` you can use. This is set to `http:\\localhost:3978` unless you are running in a
Dev Container in VS Code. In this case localhost cannot be used and a shared Docker network is required. This should
be set for you automatically.
