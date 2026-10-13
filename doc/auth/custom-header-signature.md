
# Custom Header Signature



Documentation for accessing and setting credentials for ApiKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| xSplititApiKey | `string` | Terminal API Key | `WithXSplititApiKey` | `XSplititApiKey()` |



**Note:** Required auth credentials can be set using `WithApiKeyCredentials()` by providing a credentials instance with `NewApiKeyCredentials()` in the configuration initialization and accessed using the `ApiKeyCredentials()` method in the configuration instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```go
package main

import (
    "github.com/Splitit/go-sdk/v2"
)

func main() {
    client := github.com/Splitit/go-sdk/v2.NewClient(
    github.com/Splitit/go-sdk/v2.CreateConfiguration(
            github.com/Splitit/go-sdk/v2.WithApiKeyCredentials(
                github.com/Splitit/go-sdk/v2.NewApiKeyCredentials("X-Splitit-Api-Key"),
            ),
        ),
    )
}
```


