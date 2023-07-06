# Challenge 05 - Tracking entitlement (licensing) - Coach's Guide 

[< Previous Solution](./Solution-04.md) - **[Home](./README.md)** - [Next Solution >](./Solution-06.md)

## Notes & Guidance

There is no code to write in this challenge just walking through the API calls in **VS Code**. 

The suggested code is listed below:

    // -- START REMOVE FOR CODE PATH -- //

    const subscriptionUrl = new URL(
      `api/saas/subscriptions/${subscription}?publisherId=${config.publisherId}&api-version=2018-08-31`,
      config.baseUrl
    );

    const subscriptionResponse = await fetch(subscriptionUrl, {
      method: 'GET',
      headers: {
        'Content-Type': 'application/json',
        ...headers
      }
    });

    if (!subscriptionResponse.ok) {
      return res.status(400).send(text);
    }
    
    const subscriptionObject = await subscriptionResponse.json() as Subscription;
    
    await saveEntitlement(subscriptionObject.beneficiary.tenantId, subscriptionObject.name, planId, true);

    return res.status(200).send(`${activateResponse.status} ${text}`);
    
    // -- END REMOVE FOR CODE PATH -- //

**Troubleshooting:**
