
# Offers Shopper Details

## Structure

`OffersShopperDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FirstName` | `*string` | Optional | - |
| `LastName` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `Email` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `PhoneNumber` | `*string` | Optional | - |
| `ShopperLocale` | `*string` | Optional | - |
| `BillingAddress` | [`*models.OffersBillingAddress`](../../doc/models/offers-billing-address.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    offersShopperDetails := models.OffersShopperDetails{
        FirstName:            models.ToPointer("FirstName8"),
        LastName:             "LastName8",
        Email:                "Email8",
        PhoneNumber:          models.ToPointer("PhoneNumber8"),
        ShopperLocale:        models.ToPointer("ShopperLocale6"),
        BillingAddress:       models.ToPointer(models.OffersBillingAddress{
            Line1:                "Line14",
            Line2:                models.ToPointer("Line28"),
            City:                 models.ToPointer("City4"),
            State:                models.ToPointer("State2"),
            PostalCode:           "PostalCode8",
            Country:              "Country0",
        }),
    }

}
```

