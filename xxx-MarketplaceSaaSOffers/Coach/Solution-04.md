# Challenge 04 - Activate! - Coach's Guide 

[< Previous Solution](./Solution-03.md) - **[Home](./README.md)** - [Next Solution >](./Solution-05.md)

## Notes & Guidance

The challenge updates the file: `src/service/api.ts`

The suggested code is listed below:

    // -- START REMOVE FOR CODE PATH -- //

    const activateUrl = new URL(
      `api/saas/subscriptions/${subscription}/activate?publisherId=${config.publisherId}&api-version=2018-08-31`,
      config.baseUrl
    );

    const activateResponse = await fetch(activateUrl, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        ...headers
      },
      body: JSON.stringify({ planId: planId }),
    });

    const text = await activateResponse.text();

    if (!activateResponse.ok) {
      console.log(activateResponse.status + '-' + text);
      return res.status(400).send(text);
    }

    console.log(`ACTIVATE successful. ${text}`);

    // -- END REMOVE FOR CODE PATH -- //
