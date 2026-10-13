
# Offers Merchant Details

## Structure

`OffersMerchantDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `StoreName` | `*string` | Optional | - |
| `StoreId` | `*string` | Optional | - |
| `StoreLocation` | [`models.OffersStoreLocation`](../../doc/models/offers-store-location.md) | Required | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    offersMerchantDetails := models.OffersMerchantDetails{
        StoreName:            models.ToPointer("StoreName0"),
        StoreId:              models.ToPointer("StoreId4"),
        StoreLocation:        models.OffersStoreLocation{
            Line1:                "Line14",
            Line2:                models.ToPointer("Line28"),
            City:                 models.ToPointer("City6"),
            State:                models.ToPointer("State2"),
            PostalCode:           "PostalCode2",
            Country:              "Country0",
        },
    }

}
```

