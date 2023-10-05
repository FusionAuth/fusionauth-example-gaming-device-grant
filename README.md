FusionAuth Device Authorization Grant workflow example
====
The foundation of this codebase is rooted in the FusionAuth primary Device Authorization Grant flow illustration, which can be conveniently located within the GitHub repository linked here: [GitHub Repository Link]. 
 (https://github.com/FusionAuth/fusionauth-example-device-grant)
 Our codebase draws its architectural inspiration and core principles from the exemplary implementation provided in the aforementioned repository. This foundational integration showcases the seamless orchestration of the Device Authorization Grant flow, a pivotal component in our authentication framework.

For those seeking deeper insights into the technical underpinnings and intricate details, we highly recommend exploring the original example, as it offers a comprehensive and illuminating exploration of this robust authentication paradigm.

[Read the full article](https://fusionauth.io/learn/expert-advice/gaming-entertainment/oauth-device-grant-gaming) walking you through the Device Authorization grant and how it can help your users log in to your game.

This is for demo puposes
====
A basic HTML/JavaScript app demonstrating the Device Authorization Request and Device Access Token Request of the [OAuth2 Device Authorization Grant](https://tools.ietf.org/html/rfc8628) specification.

Use in conjunction with an installation of FusionAuth to demo the entire Device Grant workflow.

Usage
----

1. [Download and install FusionAuth](https://fusionauth.io/download)
1. [Create an Application](https://fusionauth.io/docs/v1/tech/tutorials/create-an-application)
    1. Enable Device Grant on the OAuth tab under "Enabled grants"
    1. Enter a Device Verification URL. 
      - This URL should be as short (and sweet) as possible.
      - This URL will be either landing page to your application that can perform a `302` redirect to the FusionAuth device page with the required request parameters or a URL configured in a proxy to perform the same redirect.
      - For example, `https://acme.com/activate` which would be able to redirect to `https://login.acme.com/oauth2/device?client_id={client_id}&tenantId={tenantId}` where `https://login.acme.com` is the URL of your FusionAuth service.
    1. Click save (blue icon at the top right).
1. Update the [FusionAuth CORS policy](https://fusionauth.io/docs/v1/tech/reference/cors)
    1. Add `http://localhost:8000` to "Allowed origins"
    1. Check "POST" as an "Allowed methods"
    1. Click save. 
1. Edit the `main.js` file in this project
    1. Change `baseFusionAuthURL` to your base FusionAuth URL
    1. Change `clientId` to that of the newly created Application in the previous step
1. Run this example
    1. Run `python3 -m http.server` to start a simple HTTP server for the `index.html` file.
    1. Open `localhost:8000` in your browser
    1. Click the "Click to Start" button
    1. Browse to the URL provided and enter the code or scan the QR code with your phone.
    
----

Created by Lucien Chemaly
 
