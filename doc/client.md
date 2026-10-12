
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpConfiguration | [`HttpConfiguration`](../doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| oAuth2SandboxCredentials | [`OAuth2SandboxCredentials`](auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| oAuth2ProductionCredentials | [`OAuth2ProductionCredentials`](auth/oauth-2-client-credentials-grant-1.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |

The API client can be initialized as follows:

```go
package main

import (
    "splititwebapiv3"
    "splititwebapiv3/models"
)

func main() {
    client := splititwebapiv3.NewClient(
    splititwebapiv3.CreateConfiguration(
            splititwebapiv3.WithHttpConfiguration(
                splititwebapiv3.CreateHttpConfiguration(
                    splititwebapiv3.WithTimeout(0),
                ),
            ),
            splititwebapiv3.WithEnvironment(splititwebapiv3.PRODUCTION),
            splititwebapiv3.WithOAuth2SandboxCredentials(
                splititwebapiv3.NewOAuth2SandboxCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2SandboxEnum{
        models.OAuthScopeOAuth2SandboxEnum_APIV3,
    }),
            ),
            splititwebapiv3.WithOAuth2ProductionCredentials(
                splititwebapiv3.NewOAuth2ProductionCredentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2ProductionEnum{
        models.OAuthScopeOAuth2ProductionEnum_APIV3,
    }),
            ),
        ),
    )
}
```

## splitit-web-api-v3 Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| InstallmentPlanController() | Gets InstallmentPlanController |
| OAuthAuthorizationController() | Gets OAuthAuthorizationController |

