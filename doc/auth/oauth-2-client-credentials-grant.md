
# OAuth 2 Client Credentials Grant



Documentation for accessing and setting credentials for OAuth2-sandbox.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| oAuthClientId | `string` | OAuth 2 Client ID | `WithOAuthClientId` | `OAuthClientId()` |
| oAuthClientSecret | `string` | OAuth 2 Client Secret | `WithOAuthClientSecret` | `OAuthClientSecret()` |
| oAuthToken | `OAuthToken` | Object for storing information about the OAuth token | `WithOAuthToken` | `OAuthToken()` |
| oAuthScopes | `[]OAuthScopeOAuth2SandboxEnum` | List of scopes that apply to the OAuth token | `WithOAuthScopes` | `OAuthScopes()` |
| OAuthTokenProvider | `func (models.OAuthToken, OAuth2SandboxManager) models.OAuthToken` | Registers a callback function for oAuth Token Provider used for automatic token fetching/refreshing | `WithOAuthTokenProvider` | `OAuthTokenProvider` |
| OAuthOnTokenUpdate | `func (token models.OAuthToken)` | Registers a callback function for token update event | `WithOAuthOnTokenUpdate` | `OAuthOnTokenUpdate` |
| OAuthClockSkew | `int64` | Clock skew time in seconds applied while checking the OAuth Token expiry | `WithOAuthClockSkew` | `OAuthClockSkew` |



**Note:** Required auth credentials can be set using `WithOAuth2SandboxCredentials()` by providing a credentials instance with `NewOAuth2SandboxCredentials()` in the configuration initialization and accessed using the `OAuth2SandboxCredentials()` method in the configuration instance.

## Usage Example

### Client Initialization

You must initialize the client with *OAuth 2.0 Client Credentials Grant* credentials as shown in the following code snippet. This will fetch the OAuth token automatically when any of the endpoints, requiring *OAuth 2.0 Client Credentials Grant* authentication, are called.

```go
package main

import (
    "splititwebapiv3"
    "splititwebapiv3/models"
)

func main() {
    client := splititwebapiv3.NewClient(
    splititwebapiv3.CreateConfiguration(
            splititwebapiv3.WithOAuth2SandboxCredentials(
                splititwebapiv3.NewOAuth2SandboxCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2SandboxEnum{
        models.OAuthScopeOAuth2SandboxEnum_APIV3,
    }),
            ),
        ),
    )
}
```



Your application can also manually provide an OAuthToken using the setter `WithOAuthToken` in `OAuth2SandboxCredentials` object. This function takes in an instance of OAuthToken containing information for authorizing client requests and refreshing the token itself.

You must have initialized the client with scopes for which you need permission to access.

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OAuthScopeOAuth2SandboxEnum`](../../doc/models/o-auth-scope-o-auth-2-sandbox-enum.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `API_V3` | Access to WebAPI version 3 |

### Adding OAuth Token Update Callback

Whenever the OAuth Token gets updated, the provided callback implementation will be executed. For instance, you may use it to store your access token whenever it gets updated.

```go
package main

import (
    "splititwebapiv3"
    "splititwebapiv3/models"
)

func main() {
    client := splititwebapiv3.NewClient(
    splititwebapiv3.CreateConfiguration(
            splititwebapiv3.WithOAuth2SandboxCredentials(
                splititwebapiv3.NewOAuth2SandboxCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthOnTokenUpdate(func(oAuthToken models.OAuthToken) {
                    // Add the callback handler to perform operations like save to DB or file etc.
                    // It will be triggered whenever the token gets updated
                    saveTokenToDatabase(oAuthToken)
                }).
                WithOAuthScopes([]models.OAuthScopeOAuth2SandboxEnum{
        models.OAuthScopeOAuth2SandboxEnum_APIV3,
    }),
            ),
        ),
    )
}
```

### Adding Custom OAuth Token Provider

To authorize a client using a stored access token, set up the `OAuthTokenProvider` in `OAuth2SandboxCredentials` builder along with the other auth parameters before creating the client:

```go
package main

import (
    "context"
    "splititwebapiv3"
    "splititwebapiv3/models"
)

func main() {
    client := splititwebapiv3.NewClient(
    splititwebapiv3.CreateConfiguration(
            splititwebapiv3.WithOAuth2SandboxCredentials(
                splititwebapiv3.NewOAuth2SandboxCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthTokenProvider(func(lastOAuthToken models.OAuthToken, authManager OAuth2SandboxManager) models.OAuthToken {
                    // Add the callback function handler to provide a new OAuth token
                    // It will be triggered whenever the lastOAuthToken is undefined or expired
                    oAuthToken := loadTokenFromDatabase()
                    if oAuthToken.AccessToken == "" {
                        if token, err := authManager.FetchToken(context.TODO()); err == nil {
                            return token
                        }
                    }
                    return oAuthToken
                }).
                WithOAuthScopes([]models.OAuthScopeOAuth2SandboxEnum{
        models.OAuthScopeOAuth2SandboxEnum_APIV3,
    }),
            ),
        ),
    )
}
```


