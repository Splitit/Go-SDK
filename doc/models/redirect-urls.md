
# Redirect Urls

## Structure

`RedirectUrls`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `SuccessUrl` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `FailureUrl` | `*string` | Optional | - |
| `CancelUrl` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    redirectUrls := models.RedirectUrls{
        SuccessUrl:           "SuccessUrl6",
        FailureUrl:           models.ToPointer("FailureUrl6"),
        CancelUrl:            models.ToPointer("CancelUrl0"),
    }

}
```

