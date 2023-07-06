# Challenge 01 - Emulate!

[< Previous Challenge](./Challenge-00.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-02.md)

## Pre-requisites

You must have **installed the emulator**

## Introduction

Now we have the emulator working, we can exercise it a little to get a feel for the APIs and understand the emulator features.

With emulating the marketplace SaaS Fulfillment APIs, the Emulator also offers configuration to mimic the real world, simple implementations of a landing page and webhook, and custom offer creation. 

We will implement our own landing page and webhook as we work through later challenges. For now, it will be useful to explore an end-to-end purchase scenario using the built-in Emulator features.

When you browse to the emulator, you will be presented with the Emulator homepage and a menu showing the pages available:
- Marketplace (homepage)
  - Here you can configure and generate "synthetic" purchase tokens similar those used by the marketplace
  - The format of marketplace tokens is undocumented - we can consider them to be opaque
  - The only thing to keep in mind is that while they interact with your assets in the same way the individual tokens are not interchangeable between the Emulator and Commercial Marketplace
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

In this challenge we will run through the purchase workflow using the emulator, as an experience of the customer and then ISV perspective:
- Create a custom offer - a lighter version of what is required in the Partner Center experience
- Make a *purchase* of the custom offer - as a customer would in Marketplace, taking them to the landing page to accept the purchase
- As the ISV, activate the subscription
- Make changes to the plans, unsubscribe, etc, this uses APIs and webhook to simulate the marketplace actions

**Configuration and Code Tracks**

- Make sure the Emulator is running - it should be available on `http://localhost:3978`
- While the commercial team typically creates Offers and Plans (in Partner Center) using the custom plan feature of the Emulator gives and understanding of the basic dimensions of offers
- Following this activity you should have an understanding of the lifecycle of an offer - and functionality of the Emulator
- It is worth noting that the Emulator allows testing of certain APIs not available through Partner Center Preview Offers, for example, Suspend and Reinstate

## Success Criteria

To complete this challenge successfully, you should be able to:

- Describe the functions of the different sections of the Emulator
- Created a custom Offer and Plan
- Have purchased your custom offer and a second of the opposite type (per offer <> flat rate) in doing so:
  - Generated and decoded a purchase token using any Base64 decoder utility
  - Activated a subscription 
- Used the Subscriptions page to observe actions for offer and plan states
  - Observed the responses and delays

## Learning Resources

- [States of a SaaS subscription](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-life-cycle#states-of-a-saas-subscription)
- [Implementing a webhook on the SaaS service](https://learn.microsoft.com/azure/marketplace/partner-center-portal/pc-saas-fulfillment-webhook)

## Tips

- Give subscriptions meaningful names so you can track the status on the "Subscriptions" page
- When you click buttons on the "Subscriptions" page, this simulates actions in the marketplace that generate webhook calls.
Some of these calls need to be handled and some are just "FYI".
- We will implement a webhook handler later, for now the emulator's built-in handler is working for us. For more
information see "Implementing a webhook on the SaaS service" in the Learning Resources section
