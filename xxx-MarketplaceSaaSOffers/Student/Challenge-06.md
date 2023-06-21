# Challenge 06 - Tracking entitlement (licensing)

[< Previous Challenge](./Challenge-05.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-07.md)

## Introduction

Once a purchase has been made, you will likely need to persist some information about the purchase and beneficiary so that when they use the application you can
be sure they have the appropriate entitlement.

There are many ways of ensuring that a user is allowed to use the application, this might be managed by your SaaS solution as a first-party implementation, or you might integrate with a third-party licensing service. Either way, you will want to allocate an entitlement to the user or tenant once a purchase has been made.

An example of how to handle this could be:

* *Tenant-wide* - Typically associated with flat-rate offers, this would allow _anyone_ from the purchaser tenant to access the application
* *Manual assignment* - This approach allows the customer to allocate entitlements to individual users. The benefit of this approach is that it allows a customer to reallocate licenses/entitlements as they see fit
* *Auto-assignment* - To reduce the administration overhead, some applications assign the number of per-user licenses purchased to a pool against the tenant, then the licenses are auto-assigned on a first-come-first-served basis. This is often in addition to manual assignment as the customer will likely need to reassign licenses as their use and requirement changes.
* *Concurrent user access* - Some per-user license models allow the number of licenses purchased to be used by _anyone_ in the customer tenant concurrently but would be limited by the number of available licenses.

This list isn't exhaustive, and occasionally these can used in conjunction with one another to ensure the best user experience.

## Description

This challenge will focus on the tenant-wide model. The goal will be to assign a license to the tenant once a purchase has been made.

**Configuration Track**

*There is no additional configuration required to complete challenge 06.* 
You should still work through the items in the Success Criteria section to ensure you are ready for the next challenge.

The check will involve:
- Make a purchase of a flat-rate offer, setting the beneficiary details in the purchase tile of the Marketplace section of the Emulator
- Activate the subscription (of that purchase)

**Code Track**

- Adding to the code written for Challenge 04, when a subscription is activated by way of calling the `/api/activate`, assign an entitlement to the tenant in `api.ts`, below `// Challenge 06 - Tracking entitlement`.

*Note: An assignment can be made by calling the `saveEntitlement(tenantId, planId, active)` method exported from the `entitlement-api.ts` file.*

Check using the steps detailed in the Configuration Track section above.

## Success Criteria

To complete this challenge successfully, you should be able to:
- Verify the entitlement has been assigned by navigating to `/entitlements.html`