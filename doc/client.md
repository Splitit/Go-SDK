
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.SANDBOX`** |
| httpConfiguration | [`HttpConfiguration`](../doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| oAuth2Credentials | [`OAuth2Credentials`](auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| apiKeyCredentials | [`ApiKeyCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```go
package main

import (
    "github.com/Splitit/go-sdk/v2"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    client := github.com/Splitit/go-sdk/v2.NewClient(
    github.com/Splitit/go-sdk/v2.CreateConfiguration(
            github.com/Splitit/go-sdk/v2.WithHttpConfiguration(
                github.com/Splitit/go-sdk/v2.CreateHttpConfiguration(
                    github.com/Splitit/go-sdk/v2.WithTimeout(0),
                ),
            ),
            github.com/Splitit/go-sdk/v2.WithEnvironment(github.com/Splitit/go-sdk/v2.SANDBOX),
            github.com/Splitit/go-sdk/v2.WithOAuth2Credentials(
                github.com/Splitit/go-sdk/v2.NewOAuth2Credentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2Enum{
        models.OAuthScopeOAuth2Enum_APIV4,
    }),
            ),
            github.com/Splitit/go-sdk/v2.WithApiKeyCredentials(
                github.com/Splitit/go-sdk/v2.NewApiKeyCredentials("X-Splitit-Api-Key"),
            ),
        ),
    )
}
```

## splitit-web-api-v4 Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| InstallmentPlanController() | Gets InstallmentPlanController |
| OAuthAuthorizationController() | Gets OAuthAuthorizationController |

