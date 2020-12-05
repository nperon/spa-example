# spa-example

POC PKCE client for a resource server requiring authentication with an OIDC
following Oauth 2 standard.

Application was tested with success with Keycloak as the OIDC and 
a Jhipster OAuth2 backend as the resource server. The default 
Keycloak settings specific with the Jhipster application were just 
complemented with an additional client called pkce-client.

To configure Keycloak, the following steps need to be taken:
- create a new client called pkce-client within the jhipster realm
- set the value of Access Type to public
- for this new client, toggle Standard Flow Enabled to ON
- toggle the Implicit Flow Enabled and Direct Access Grant Enabled to OFF if it is not the case yet
- set the following url as a Valid Redirect URI : 'http://localhost:8181/authcodeReader.html'
- set a + sign in the first Web Origins input
- in the Advanced Settings section of client pkce-client, set the value of the Proof Key for Code Exchange Code Challenge Method to S256

Valid all of these settings with Save.
