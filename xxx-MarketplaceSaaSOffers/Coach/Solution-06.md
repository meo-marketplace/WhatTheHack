# Challenge 06 - Listening on a webhook - Coach's Guide 

[< Previous Solution](./Solution-05.md) - **[Home](./README.md)** - [Next Solution >](./Solution-07.md)

## Notes & Guidance

This is the only section you need to include.

The challenge updates the file: `src/service/webhook-api.ts`

The suggested code is listed below:

    // -- START REMOVE FOR CODE PATH -- //

    switch(action.toLowerCase() as WebhookAction) {
        case "changeplan":
        case "changequantity":
            res.sendStatus(200).send();
            await saveEntitlement(tenantId, req.body.subscription.name, planId, true);
            return;

        case "reinstate":
            await saveEntitlement(tenantId, req.body.subscription.name, planId, true);
            break;
        case "renew":
            break;
        case "suspend":
            await saveEntitlement(tenantId, req.body.subscription.name, planId, false);
            break;
        case "unsubscribe":
            await removeEntitlement(tenantId);
            break;
    }

    // -- END REMOVE FOR CODE PATH -- //
