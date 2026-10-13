
# HttpConfiguration

The following parameters are configurable for the HttpConfiguration:

## Properties

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| timeout | `float64` | Timeout in seconds.<br>*Default*: `0` | `WithTimeout` | `Timeout()` |
| transport | `httpRoundTripper` | Establishes network connection and caches them for reuse.<br>*Default*: `http.DefaultTransport` | `WithTransport` | `Transport()` |
| retryConfiguration | [`github.com/Splitit/go-sdk/v2RetryConfiguration`](../doc/retry-configuration.md) | Configurations to retry requests.<br>*Default*: `github.com/Splitit/go-sdk/v2.DefaultRetryConfiguration()` | `WithRetryConfiguration` | `RetryConfiguration()` |

The httpConfiguration can be initialized as follows:

```go
package main

import (
    "github.com/Splitit/go-sdk/v2"
    "net/http"
)

func main() {
    httpConfiguration := github.com/Splitit/go-sdk/v2.CreateHttpConfiguration(
        github.com/Splitit/go-sdk/v2.WithTimeout(0),
        github.com/Splitit/go-sdk/v2.WithTransport(http.DefaultTransport),
        github.com/Splitit/go-sdk/v2.WithRetryConfiguration(github.com/Splitit/go-sdk/v2.DefaultRetryConfiguration()),
    )
}
```

