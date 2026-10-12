
# Getting Started with splitit-web-api-v4

## Introduction

Splitit Orchestration API for managing installment plans.

### Requirements

The SDK requires **Go version 1.18 or above**.

## Building

### Install Dependencies

Resolve all the SDK dependencies, using the `go get` command.

## Installation

The following section explains how to use the splititwebapiv4 library in a new project.

### 1. Add SDK as a Dependency to the Application

- Add the following lines to your application's `go.mod` file:

```go
replace splititwebapiv4 => ".\\splitit-web-api-v4" // local path to the SDK

require splititwebapiv4 v0.0.0
```

- Resolve the dependencies in the updated `go.mod` file, using the `go get` command.

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](README.md#environments) | The API environment. <br> **Default: `Environment.SANDBOX`** |
| httpConfiguration | [`HttpConfiguration`](doc/http-configuration.md) | Configurable http client options like timeout and retries. |
| oAuth2Credentials | [`OAuth2Credentials`](doc/auth/oauth-2-client-credentials-grant.md) | The Credentials Setter for OAuth 2 Client Credentials Grant |
| apiKeyCredentials | [`ApiKeyCredentials`](doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

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

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| SANDBOX | **Default** Sandbox Environment (Transactional API) |
| PRODUCTION | Production Environment (Transactional API) |

## Authorization

This API uses the following authentication schemes.

* [`OAuth2 (OAuth 2 Client Credentials Grant)`](doc/auth/oauth-2-client-credentials-grant.md)
* [`ApiKey (Custom Header Signature)`](doc/auth/custom-header-signature.md)

## List of APIs

* [Installment Plan](doc/controllers/installment-plan.md)

## SDK Infrastructure

### Configuration

* [HttpConfiguration](doc/http-configuration.md)
* [RetryConfiguration](doc/retry-configuration.md)

### Utilities

* [ApiResponse](doc/api-response.md)

