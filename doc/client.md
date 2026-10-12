
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
    "splititwebapiv4"
    "splititwebapiv4/models"
)

func main() {
    client := splititwebapiv4.NewClient(
    splititwebapiv4.CreateConfiguration(
            splititwebapiv4.WithHttpConfiguration(
                splititwebapiv4.CreateHttpConfiguration(
                    splititwebapiv4.WithTimeout(0),
                ),
            ),
            splititwebapiv4.WithEnvironment(splititwebapiv4.SANDBOX),
            splititwebapiv4.WithOAuth2Credentials(
                splititwebapiv4.NewOAuth2Credentials(
                    "OAuthClientId",
                    "OAuthClientSecret",
                ).
                WithOAuthScopes([]models.OAuthScopeOAuth2Enum{
        models.OAuthScopeOAuth2Enum_APIV4,
    }),
            ),
            splititwebapiv4.WithApiKeyCredentials(
                splititwebapiv4.NewApiKeyCredentials("X-Splitit-Api-Key"),
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

