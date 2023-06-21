# Challenge 02 - Emulate!

[< Previous Challenge](./Challenge-01.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-03.md)

## Pre-requisites

You must have **installed the emulator**

## Introduction

Now we have the emulator working, we can exercise it a little to get a feel for the APIs and understand the emulator features.

With emulating the marketplace SaaS Fulfillment APIs, the emulator also offers configuration to mimic the real world, simple implementations of a landing page and webhook, and custom offer creation. 

We will implement our own landing page and webhook as we work through
later challenges. For now, it will be useful to explore an end-to-end purchase scenario using the built-in emulator features.

When you browse to the emulator, you will be presented with the Emulator homepage and a menu showing the pages available:

- Marketplace (homepage)
  - Here you can configure and generate "synthetic" purchase tokens similar those used by the marketplace
  - The format of marketplace tokens is undocumented - we can consider them to be opaque
  - The only thing to keep in mind is that while they interact with your assets in the same way the individual tokens are not interchangeable between emulator and marketplace
- Subscriptions
  - Displays details of the current subscriptions (purchases) and their status
  - Displays the actions that have been taken on the subscription and the responses from the webhook
  - On this page you can also simulate marketplace actions (eg the user may request a plan change via the portal)
- Landing Page
  - This is the default, built-in landing page implementation
  - This page will automatically decode the token from the token query string parameter in the URL
- Offers
  - Create and configure custom offers - a simplified version of what you get in Partner Center
  - Note, the full plan options are not available but are sufficient to track real world scenarios
- Config
  - Here, various aspects of the emulator can be configured
  - When we have built our own landing page, we would configure the emulator to use it here

## Description

In this challenge we will create an offer, configure and generate a purchase token, simulate a "configure my subscription" request from
the marketplace and activate the subscription. Finally we will try to change to a new plan and unsubscribe from the offer.

**Configuration and Code Tracks**

- Make sure the emulator is running - it should be available on `http://localhost:3978`
- While the partner commercial team typically creates Offers and Plans (in Partner Center) using the custom plan feature of the emulator gives and understanding of the basic dimenions of offers
- Following this activity you should have an understanding of the lifecycle of an offer - and functionality of the Emulator
- It is worth noting that the Emulator allows testing of certain APIs not avilable through Partner Center Preview Offers, for example, Suspend and Reinstate

## Success Criteria

To complete this challenge successfully, you should be able to:

- Be able to describle the functions of the different sections of the Emulator
- Custom Offer and Plan
- Have purchased of at least your custom offer and a second of another type (per offer/flat rate) in doing so:
  - Generated and decoded a purchase token using any Base64 decoder utility
  - Confirmed the Base64 result matches the original JSON token
  - Activated a subscription 
- Used the Subscriptions page to observe actions for offer and plan states
  - Observed the responses and delays

## Learning Resources

- [Decode from Base64 with GCHQ's CyberChef](https://gchq.github.io/CyberChef/)
- [States of a SaaS subscription](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-life-cycle#states-of-a-saas-subscription)
- [Implementing a webhook on the SaaS service](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-webhook)

## Tips

- Make a note of the `id` on the "Marketplace Token" page before posting to the landing page so you can track the
status on the "Subscriptions" page
- When you click buttons on the "Subscriptions" page, this simulates actions in the marketplace that generate webhook calls.
Some of these calls need to be handled and some are just "FYI".
- We will implement a webhook handler later, for now the emulator's built-in handler is working for us. For more
information see "Implementing a webhook on the SaaS service" in the Learning Resources section
