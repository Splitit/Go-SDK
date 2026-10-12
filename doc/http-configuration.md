
# HttpConfiguration

The following parameters are configurable for the HttpConfiguration:

## Properties

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| timeout | `float64` | Timeout in seconds.<br>*Default*: `0` | `WithTimeout` | `Timeout()` |
| transport | `httpRoundTripper` | Establishes network connection and caches them for reuse.<br>*Default*: `http.DefaultTransport` | `WithTransport` | `Transport()` |
| retryConfiguration | [`splititwebapiv3RetryConfiguration`](../doc/retry-configuration.md) | Configurations to retry requests.<br>*Default*: `splititwebapiv3.DefaultRetryConfiguration()` | `WithRetryConfiguration` | `RetryConfiguration()` |

The httpConfiguration can be initialized as follows:

```go
package main

import (
    "splititwebapiv3"
    "net/http"
)

func main() {
    httpConfiguration := splititwebapiv3.CreateHttpConfiguration(
        splititwebapiv3.WithTimeout(0),
        splititwebapiv3.WithTransport(http.DefaultTransport),
        splititwebapiv3.WithRetryConfiguration(splititwebapiv3.DefaultRetryConfiguration()),
    )
}
```

