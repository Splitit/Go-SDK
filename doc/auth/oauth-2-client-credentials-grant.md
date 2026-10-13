
# OAuth 2 Client Credentials Grant



Documentation for accessing and setting credentials for OAuth2.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| oAuthClientId | `string` | OAuth 2 Client ID | `WithOAuthClientId` | `OAuthClientId()` |
| oAuthClientSecret | `string` | OAuth 2 Client Secret | `WithOAuthClientSecret` | `OAuthClientSecret()` |
| oAuthToken | `OAuthToken` | Object for storing information about the OAuth token | `WithOAuthToken` | `OAuthToken()` |
| oAuthScopes | `[]OAuthScopeOAuth2Enum` | List of scopes that apply to the OAuth token | `WithOAuthScopes` | `OAuthScopes()` |
| OAuthTokenProvider | `func (models.OAuthToken, OAuth2Manager) models.OAuthToken` | Registers a callback function for oAuth Token Provider used for automatic token fetching/refreshing | `WithOAuthTokenProvider` | `OAuthTokenProvider` |
| OAuthOnTokenUpdate | `func (token models.OAuthToken)` | Registers a callback function for token update event | `WithOAuthOnTokenUpdate` | `OAuthOnTokenUpdate` |
| OAuthClockSkew | `int64` | Clock skew time in seconds applied while checking the OAuth Token expiry | `WithOAuthClockSkew` | `OAuthClockSkew` |



**Note:** Required auth credentials can be set using `WithOAuth2Credentials()` by providing a credentials instance with `NewOAuth2Credentials()` in the configuration initialization and accessed using the `OAuth2Credentials()` method in the configuration instance.

## Usage Example

### Client Initialization

You must initialize the client with *OAuth 2.0 Client Credentials Grant* credentials as shown in the following code snippet. This will fetch the OAuth token automatically when any of the endpoints, requiring *OAuth 2.0 Client Credentials Grant* authentication, are called.

```go
package main

import (
    "github.com/Splitit/go-sdk/v2"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    client := github.com/Splitit/go-sdk/v2.NewClient(
    github.com/Splitit/go-sdk/v2.CreateConfiguration(
            github.com/Splitit/go-sdk/v2.WithOAuth2Credentials(
                github.com/Splitit/go-sdk/v2.NewOAuth2Credentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2Enum{
        models.OAuthScopeOAuth2Enum_APIV4,
    }),
            ),
        ),
    )
}
```



Your application can also manually provide an OAuthToken using the setter `WithOAuthToken` in `OAuth2Credentials` object. This function takes in an instance of OAuthToken containing information for authorizing client requests and refreshing the token itself.

You must have initialized the client with scopes for which you need permission to access.

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OAuthScopeOAuth2Enum`](../../doc/models/o-auth-scope-o-auth-2-enum.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `API_V4` | Access to API v4 |

### Adding OAuth Token Update Callback

Whenever the OAuth Token gets updated, the provided callback implementation will be executed. For instance, you may use it to store your access token whenever it gets updated.

```go
package main

import (
    "github.com/Splitit/go-sdk/v2"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    client := github.com/Splitit/go-sdk/v2.NewClient(
    github.com/Splitit/go-sdk/v2.CreateConfiguration(
            github.com/Splitit/go-sdk/v2.WithOAuth2Credentials(
                github.com/Splitit/go-sdk/v2.NewOAuth2Credentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthOnTokenUpdate(func(oAuthToken models.OAuthToken) {
                    // Add the callback handler to perform operations like save to DB or file etc.
                    // It will be triggered whenever the token gets updated
                    saveTokenToDatabase(oAuthToken)
                }).
                WithOAuthScopes([]models.OAuthScopeOAuth2Enum{
        models.OAuthScopeOAuth2Enum_APIV4,
    }),
            ),
        ),
    )
}
```

### Adding Custom OAuth Token Provider

To authorize a client using a stored access token, set up the `OAuthTokenProvider` in `OAuth2Credentials` builder along with the other auth parameters before creating the client:

```go
package main

import (
    "context"
    "github.com/Splitit/go-sdk/v2"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    client := github.com/Splitit/go-sdk/v2.NewClient(
    github.com/Splitit/go-sdk/v2.CreateConfiguration(
            github.com/Splitit/go-sdk/v2.WithOAuth2Credentials(
                github.com/Splitit/go-sdk/v2.NewOAuth2Credentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthTokenProvider(func(lastOAuthToken models.OAuthToken, authManager OAuth2Manager) models.OAuthToken {
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
                WithOAuthScopes([]models.OAuthScopeOAuth2Enum{
        models.OAuthScopeOAuth2Enum_APIV4,
    }),
            ),
        ),
    )
}
```


