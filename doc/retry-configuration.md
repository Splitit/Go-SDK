
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
    "github.com/Splitit/go-sdk/v2"
)

func main() {
    retryConfiguration := github.com/Splitit/go-sdk/v2.CreateRetryConfiguration(
        github.com/Splitit/go-sdk/v2.WithMaxRetryAttempts(0),
        github.com/Splitit/go-sdk/v2.WithRetryOnTimeout(true),
        github.com/Splitit/go-sdk/v2.WithRetryInterval(1),
        github.com/Splitit/go-sdk/v2.WithMaximumRetryWaitTime(0),
        github.com/Splitit/go-sdk/v2.WithBackoffFactor(2),
        github.com/Splitit/go-sdk/v2.WithHttpStatusCodesToRetry([]int64{408, 413, 429, 500, 502, 503, 504, 521, 522, 524}),
        github.com/Splitit/go-sdk/v2.WithHttpMethodsToRetry([]string{"GET", "PUT"}),
    )
}
```

