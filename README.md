# 10.-Build-a-JS-SDK-for-the-web-an-authenticated-Node.js-backend-that-lets-users-login-buy-credits
Need a JS SDK built for the frontend that exposes a global function called getAccessToken().

Problem Description
Need a JS SDK built for the frontend that exposes a global function called getAccessToken().

When called, it should return a promise that does the following:

Checks if user is logged in.
If not, give options to login with "Google" and "Github" in a top-right popup.

Checks if user has available credit.
If not, lead user to purchase credits.

-> Topup in same popup.
-> Add payment method in new tab.

Is quota up for current domain?
Use slider in same popup to select quota.

If all checks pass, calls the backend using the authentication headers/tokens of Google/Github.

The backend should check if the user has enough credit and quota for the domain.

If all checks pass, the backend should return a randomly generated access token (The access token can be anything random, not going to be used at this stage).

Here's a flowchart for the above. https://i.imgur.com/tx7Iwsk.png.

These are essentially three components:

SDK
Backend
Small web app for adding payment methods (Important that this isn't in the SDK popup as the keystrokes can be hijacked by the site.)
Acceptance Criteria
Both the SDK and backend must be built with Typescript.
The SDK should be easily publishable to NPM. You can use this guide to bootstrap this.
The SDK needs to be plug-and-play. No dependencies.
Using Stripe (I'm not aware of the specifics here), find a way to let users purchase credits and remember their payment method for the next time they want to top-up.
