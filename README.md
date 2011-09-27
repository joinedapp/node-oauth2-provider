# OAuth 2 Provider for node.js

Supports both server-side (code) and client-side (token) OAuth flows.

## Quick Start

Install via npm:

    npm install oauth2-provider

You can add it to your Connect or Express application as another middleware.
Be sure to enable the `bodyParser` and `query` middleware.

The OAuth2Provider instance providers two middleware:

* `oauth()`: OAuth flow entry and access token generation
* `login()`: Access control for protected resources

The most importand event emitted by OAuth2Provider is `access_token`, which
lets you set up the request as if it were authenticated. For example, to
support both cookie-authenticated and OAuth access to protected URLs, you
could populate `req.session.user` so that individual URLs don't need to
care about which type of authentication was used.

See examples/simple.js for how to use it.
