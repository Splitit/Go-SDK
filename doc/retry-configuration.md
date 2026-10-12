
# RetryConfiguration

The following parameters are configurable for the RetryConfiguration:

## Properties

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| maxRetryAttempts | `int64` | Maximum number of retries.<br>*Default*: `0` | `WithMaxRetryAttempts` | `MaxRetryAttempts()` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` | `WithRetryOnTimeout` | `RetryOnTimeout()` |
| retryInterval | `timeDuration` | Interval before next retry. Used in calculation of wait time for next request in case of failure.<br>*Default*: `1` | `WithRetryInterval` | `RetryInterval()` |
| maximumRetryWaitTime | `timeDuration` | Overall wait time for the requests getting retried.<br>*Default*: `0` | `WithMaximumRetryWaitTime` | `MaximumRetryWaitTime()` |
| backoffFactor | `int64` | Used in calculation of wait time for next request in case of failure.<br>*Default*: `2` | `WithBackoffFactor` | `BackoffFactor()` |
| httpStatusCodesToRetry | `[]int64` | Http status codes to retry against.<br>*Default*: `[]int64{408, 413, 429, 500, 502, 503, 504, 521, 522, 524}` | `WithHttpStatusCodesToRetry` | `HttpStatusCodesToRetry()` |
| httpMethodsToRetry | `[]string` | Http methods to retry against.<br>*Default*: `[]string{"GET", "PUT"}` | `WithHttpMethodsToRetry` | `HttpMethodsToRetry()` |

The retryConfiguration can be initialized as follows:

```go
package main

import (
    "splititwebapiv3"
)

func main() {
    retryConfiguration := splititwebapiv3.CreateRetryConfiguration(
        splititwebapiv3.WithMaxRetryAttempts(0),
        splititwebapiv3.WithRetryOnTimeout(true),
        splititwebapiv3.WithRetryInterval(1),
        splititwebapiv3.WithMaximumRetryWaitTime(0),
        splititwebapiv3.WithBackoffFactor(2),
        splititwebapiv3.WithHttpStatusCodesToRetry([]int64{408, 413, 429, 500, 502, 503, 504, 521, 522, 524}),
        splititwebapiv3.WithHttpMethodsToRetry([]string{"GET", "PUT"}),
    )
}
```

