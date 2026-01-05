
# Getting Started with splitit-web-api-v3

## Introduction

### Requirements

The SDK requires **Go version 1.18 or above**.


## Building

### Install Dependencies

Resolve all the SDK dependencies, using the `go get` command.

## Installation

The following section explains how to use the splititwebapiv3 library in a new project.

### 1. Add SDK as a Dependency to the Application

- Add the following lines to your application's `go.mod` file:

```go
replace splititwebapiv3 => ".\\splitit-web-api-v3" // local path to the SDK

require splititwebapiv3 v0.0.0
```

- Resolve the dependencies in the updated `go.mod` file, using the `go get` command.

## Test the SDK

`Go Testing` is used as the testing framework. To run the unit tests of the SDK, navigate to the root directory of the SDK and run the following command in the terminal:

```bash
$ go test
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpConfiguration | [`HttpConfiguration`](doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| oAuth2SandboxCredentials | [`OAuth2SandboxCredentials`](doc/auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| oAuth2ProductionCredentials | [`OAuth2ProductionCredentials`](doc/auth/oauth-2-client-credentials-grant-1.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| production | **Default** Sandbox |
| environment2 | Production |

## Authorization

This API uses the following authentication schemes.

* [`OAuth2-sandbox (OAuth 2 Client Credentials Grant)`](doc/auth/oauth-2-client-credentials-grant.md)
* [`OAuth2-production (OAuth 2 Client Credentials Grant)`](doc/auth/oauth-2-client-credentials-grant-1.md)

## List of APIs

* [Installment Plan](doc/controllers/installment-plan.md)

## SDK Infrastructure

### Configuration

* [HttpConfiguration](doc/http-configuration.md)
* [RetryConfiguration](doc/retry-configuration.md)

### Utilities

* [ApiResponse](doc/api-response.md)

