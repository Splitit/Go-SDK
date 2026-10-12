
# Three DS Request Data

## Structure

`ThreeDSRequestData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Execute` | `*bool` | Optional | - |
| `ThreeDSURLs` | [`*models.RedirectUrls`](../../doc/models/redirect-urls.md) | Optional | - |
| `AuthenticationData` | [`*models.ThreeDSAuthenticationData`](../../doc/models/three-ds-authentication-data.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    threeDSRequestData := models.ThreeDSRequestData{
        Execute:              models.ToPointer(false),
        ThreeDSURLs:          models.ToPointer(models.RedirectUrls{
            SuccessUrl:           "SuccessUrl2",
            FailureUrl:           models.ToPointer("FailureUrl2"),
            CancelUrl:            models.ToPointer("CancelUrl4"),
        }),
        AuthenticationData:   models.ToPointer(models.ThreeDSAuthenticationData{
            ECI:                          "ECI6",
            CAVV:                         "CAVV4",
            DirectoryServerTransactionId: "DirectoryServerTransactionId0",
            Version:                      "Version8",
        }),
    }

}
```

