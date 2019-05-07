# ![LOGO](logo.png) Authentiq Connect **flow**ground Connector

## Description

A generated **flow**ground connector for the Authentiq Connect API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/authentiq.io/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:37:03+03:00

## API Description

Authentiq Connect OAuth 2.0 and OpenID Connect API reference.
Learn about [Authentiq ID](https://www.authentiq.com/) or check out the [Authentiq Connect](https://developers.authentiq.com) developer documentation.


## Authorization

Supported authorization schemes:
- API Key- OAuth2
- OAuth2
- OAuth2
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Authenticate a user

> Start a session with Authentiq Connect to authenticate a user.<br/>
> <br/>
> ```<br/>
> GET https://connect.authentiq.io/authorize?client_id=<your-client-id>&response_type=code+id_token&scope=openid+email&redirect_uri=<your-redirect-uri>&state=0123456789<br/>
> ```<br/>
> <br/>
> This endpoint also supports the POST method.

*Tags:* `Authentication`

#### Input Parameters
* `client_id` - _required_ - A client ID obtained from the [Dashboard](https://dashboard.authentiq.com/).

* `response_type` - _required_ - The OIDC response type to use for this authentication flow. Valid choices are `code`, `id_token`, `token`, `token id_token`, `code id_token` `code token` and `code token id_token`, but a client can be configured with a more restricted set.

* `scope` - _required_ - The space-separated identity claims to request from the end-user. Always include `openid` as a scope for compatibility with OIDC.

* `redirect_uri` - _required_ - The location to redirect to after (un)successful authentication. See OIDC for the parameters passed in the query string (`response_mode=query`) or as fragments (`response_mode=fragment`). Unless the client is in test-mode this must be one of the registered redirect URLs.

* `state` - _required_ - An opaque string that will be passed back to the redirect URL and therefore can be used to communicate client side state and prevent CSRF attacks.

* `response_mode` - _optional_ - Whether to append parameters to the redirect URL in the query string (`query`) or as fragments (`fragment`). This option usually has a sensible default for each of the response types.

* `nonce` - _optional_ - An nonce provided by the client (and opaque to Authentiq Connect) that will be included in any ID Token generated for this session. Clients should use the nonce to mitigate replay attacks.

* `display` - _optional_ - The authentication display mode, which can be one of `page`, `popup` or `modal`. Defaults to `page`.

* `prompt` - _optional_ - Space-delimited, case sensitive list of ASCII string values that specifies whether the Authorization Server prompts the End-User for reauthentication and consent. The supported values are: `none`, `login`, `consent`. If `consent` the end-user is asked to (re)confirm what claims they share. Use `none` to check for an active session.

* `max_age` - _optional_ - Specifies the allowable elapsed time in seconds since the last time the end-user was actively authenticated.

* `ui_locales` - _optional_ - Specifies the preferred language to use on the authorization page, as a space-separated list of BCP47 language tags. Ignored at the moment.


### List clients

> Retrieve a list of clients.

*Tags:* `Client Management`

### Register a client

> Register a new client with this Authentiq Connect provider.<br/>
> <br/>
> This endpoint is compatible with [OIDC's Client Registration](http://openid.net/specs/openid-connect-registration-1_0.html) extension.

*Tags:* `Client Management`

### Delete a client

> Delete a previously registered client.

*Tags:* `Client Management`

#### Input Parameters
* `client_id` - _required_ - Client identifier

### View a client

> Retrieve the configuration of a previously registered client.

*Tags:* `Client Management`

#### Input Parameters
* `client_id` - _required_ - Client identifier

### Update a client

> Update the configuration of a previously registered client.

*Tags:* `Client Management`

#### Input Parameters
* `client_id` - _required_ - Client identifier

### Obtain an ID Token

> Exchange en authorization code for an ID Token or Access Token.<br/>
> <br/>
> This endpoint supports both `client_secret_basic` (default) and `client_secret_basic` authentication methods, as specified by the client's `token_endpoint_auth_method`.

*Tags:* `Authentication`

#### Input Parameters
* `Authorization` - _optional_ - HTTP Basic authorization header.


### Retrieve a user profile

> Use this endpoint to retrieve a user's profile in case you are unable to parse an ID Token or you've not already obtained enough details from the ID Token via the Token Endpoint.

*Tags:* `Authentication`

### Include a session iframe

> An OpenID Connect Session Management iframe to facilitate e.g. single sign-on or remote logouts.<br/>
> <br/>
> The iframe implements the OIDC postMessage-based [change notification protocol](http://openid.net/specs/openid-connect-session-1_0.html#ChangeNotification) via which a client can receive notifications about session state changes.

*Tags:* `Session Management`

#### Input Parameters
* `client_id` - _required_ - Client identifier

## License

**flow**ground :- Telekom iPaaS / authentiq-io-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
