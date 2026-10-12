
# Authorize Request

## Structure

`AuthorizeRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `OfferId` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `AutoCapture` | `bool` | Required | - |
| `ShopperAcceptedTerms` | `bool` | Required | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `ThreeDS` | [`*models.ThreeDSRequestData`](../../doc/models/three-ds-request-data.md) | Optional | - |
| `ProcessingData` | [`*models.ProcessingData`](../../doc/models/processing-data.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    authorizeRequest := models.AuthorizeRequest{
        OfferId:                "OfferId0",
        AutoCapture:            false,
        ShopperAcceptedTerms:   false,
        MerchantOrderReference: models.ToPointer("MerchantOrderReference6"),
        ThreeDS:                models.ToPointer(models.ThreeDSRequestData{
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
        }),
        ProcessingData:         models.ToPointer(models.ProcessingData{
            SoftDescriptor:       models.ToPointer("SoftDescriptor6"),
        }),
    }

}
```

