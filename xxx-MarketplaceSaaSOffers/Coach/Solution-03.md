# Challenge 03 - Decoding purchase tokens - Coach's Guide 

[< Previous Solution](./Solution-02.md) - **[Home](./README.md)** - [Next Solution >](./Solution-04.md)

## Notes & Guidance

- navigate to the Emulator Config page
- update the **Landing Page URL** to the solution Landing Page URL - this should be `http://localhost:3000/landing.html`
- check on the Emulator **Marketplace Token** page that the **Post to landing page** button directs to the solution Landing Page

**Code Track**
The student should check the Challenge 3 section in `src/client/landing.html`
The code updates are made in file: `src/service/api.ts`

The suggested code is listed below:

    // -- START REMOVE FOR CODE PATH -- //

    const resolveUrl = new URL(
      `api/saas/subscriptions/resolve?publisherId=${config.publisherId}&api-version=2018-08-31`,
      config.baseUrl
    );

    const resolveResponse = await fetch(resolveUrl, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'x-ms-marketplace-token': token,
        ...headers
      },
    });

    if (!resolveResponse.ok) {
      const text = await resolveResponse.text();
      console.log(resolveResponse.status + '-' + text);
      return res.status(400).send(text);
    }

    const resolveResult = await resolveResponse.json();
    console.log(`RESOLVE successful. ${resolveResult}`);

    // -- END REMOVE FOR CODE PATH -- //