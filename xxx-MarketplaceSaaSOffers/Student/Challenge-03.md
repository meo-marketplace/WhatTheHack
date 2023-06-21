# Challenge 03 - Decoding purchase tokens

[< Previous Challenge](./Challenge-02.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-04.md)

## Pre-requisites

You must have completed **Challenge 02 - Emulate!**

## Introduction

In the Commercial Marketplace when a customer indicates their intention to purchase your solution in the marketplace, they are directed to your landing page passing the query string token that, as seen, contains the basic details about the customer and
their desired purchase. The landing page is also your opportunity to capture any additional information as part of the
onboarding and confirm the customer's purchase.

In Challenge 01, we started work on our own landing page. We extracted the token from the query string and stored it
in a variable. In this challenge the landing page is extended to decode purchase tokens.

This is the point in development, you have a basic landing page, where you direct the Emulator mock purchase to that page, instead of the built in page.

## Description

In this challenge we will extend our landing page by calling the marketplace `resolve` API to decode a purchase token
and display some details from the decoded token in the landing page UI.

**Configuration Track**

You should now be familiar with the marketplace workflow from the emulator. We are going to switch out the Emulator's inbuilt landing page for that in the sample app.
- The URL is set in the Config page, copy the Landing Page URL from your sample app to the config box and Set. 
**Note:** Change just the landing page
- The 'Subscription Name' should begin with 'C4' (if there are multiple subscriptions just use this preface for each)

**Code Track**

Complete the Emulator config as above.

In Challenge-01, you were working in the client-side JavaScript. In practice, most of the work will be done server-side
to avoid cross-domain issues and manage the authentication with the marketplace APIs. In this challenge you will be
implementing an API that will act as a proxy, calling the marketplace `resolve` API on behalf of our client-side JavaScript.

The server component is a Node.js Express application written in TypeScript. You shouldn't have to concern yourself with
the Node / Express aspects (aside from the pre-requisites) but you will be writing some TypeScript.

The client-side function is already implemented for you as `decodeButtonClick()` in `landing.html`. This calls
`api/resolve` which is the API we need to implement. Routing has been configured to route POST requests to `api/resolve`
to the TypeScript function `resolveToken()` defined in `src/service/api.ts`.

In this challenge we will only be concerned with the function `resolveToken()` in `src/service/api.ts`. The function
currently has an empty implementation below the placeholder `// Challenge 03 - Decoding purchase tokens`.

Your task it to update the `resolveToken()` implementation to call the marketplace `resolve` API and return the result
to the caller handling any errors along the way.

The emulator should be available on `http://localhost:3978`

- Validate the request (check there is a token etc)
- Call the marketplace `resolve` API, passing the token in the header
- Check the result and return an appropriate status code
- If the call is successful, return the result as JSON

## Success Criteria

To complete this challenge successfully, you should be able to:

- A purchase token posted from the Emulator to the Sample App landing page
- The token is resolved in the Sample App - observe the token properties in the resolve token section
- Your subscription is listed and is in "Pending" status in the Emulator subscriptions list

## Learning Resources

- [Marketplace resolve API](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-subscription-api#post-httpsmarketplaceapimicrosoftcomapisaassubscriptionsresolveapi-versionapiversion)
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
- You can see the routing configuration to map route `api/resolve` to `resolveToken()` in `index.ts` line 34
