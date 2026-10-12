
# HttpConfiguration

The following parameters are configurable for the HttpConfiguration:

## Properties

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| timeout | `float64` | Timeout in seconds.<br>*Default*: `0` | `WithTimeout` | `Timeout()` |
| transport | `httpRoundTripper` | Establishes network connection and caches them for reuse.<br>*Default*: `http.DefaultTransport` | `WithTransport` | `Transport()` |
| retryConfiguration | [`splititwebapiv4RetryConfiguration`](../doc/retry-configuration.md) | Configurations to retry requests.<br>*Default*: `splititwebapiv4.DefaultRetryConfiguration()` | `WithRetryConfiguration` | `RetryConfiguration()` |

The httpConfiguration can be initialized as follows:

```go
package main

import (
    "splititwebapiv4"
    "net/http"
)

func main() {
    httpConfiguration := splititwebapiv4.CreateHttpConfiguration(
        splititwebapiv4.WithTimeout(0),
        splititwebapiv4.WithTransport(http.DefaultTransport),
        splititwebapiv4.WithRetryConfiguration(splititwebapiv4.DefaultRetryConfiguration()),
    )
}
```

