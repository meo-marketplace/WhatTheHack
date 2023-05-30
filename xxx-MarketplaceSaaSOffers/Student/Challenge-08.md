# Challenge 08 - Listening on a webhook

[< Previous Challenge](./Challenge-07.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-09.md)

## Introduction

Once a purchase has been made, the customer can manage their subscription through the M365 Admin Portal (if the purchase was made from AppSource) or the Azure Portal (if the purchase was made from the Azure Marketplace).

When a change is made, for example the number of seats on a per-user subscription, your solution is notified by way of a webhook call. This call contains the type of event and information about the change to the subscription.

There are several events that can be raised via the webhook and the majority of them are sent as a notification to your service and will succeed even if you return a failed status code. However, there are a few that require a successful status code to be returned in order for the change to be enacted. These are `change plan`, `change quantity` and `reinstate`.

*Note: The emulator will not retry on a failed request but the real marketplace APIs will retry if a status code of 500+ is returned*

## Description

In this challenge, we will implement and configure the webhook used by the emulator to simulate the various events that can occur after a purchase has been successful.

**Configuration Track**

- Configure the emulator to use the webhook hosted within the sample application. The webhook URL to configure is `/api/webhook`.

**Code Track**

- Implement the body of the `webhookHandler` method in the `webhook-api.ts` file.

## Success Criteria

To complete this challenge successfully, you should be able to:
- Make and activate a purchase
- Modify the properties of the subscription (such as the plan or the number of seats for a per-user subscription) from the emulator user interface
- Make state changes to the subscription (such as Suspend, Unsubscribe or Renew)

## Learning Resources

- [Implement a webhook](https://learn.microsoft.com/en-us/partner-center/marketplace/partner-center-portal/pc-saas-fulfillment-webhook)