
# Update Offers Request

## Structure

`UpdateOffersRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `MerchantOrderReference` | `*string` | Optional | - |
| `ShopperDetails` | [`*models.OffersShopperDetails`](../../doc/models/offers-shopper-details.md) | Optional | - |
| `PaymentMethod` | [`*models.UpdateOffersPaymentMethod`](../../doc/models/update-offers-payment-method.md) | Optional | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    updateOffersRequest := models.UpdateOffersRequest{
        MerchantOrderReference: models.ToPointer("MerchantOrderReference4"),
        ShopperDetails:         models.ToPointer(models.OffersShopperDetails{
            FirstName:            models.ToPointer("FirstName6"),
            LastName:             "LastName6",
            Email:                "Email6",
            PhoneNumber:          models.ToPointer("PhoneNumber2"),
            ShopperLocale:        models.ToPointer("ShopperLocale8"),
            BillingAddress:       models.ToPointer(models.OffersBillingAddress{
                Line1:                "Line14",
                Line2:                models.ToPointer("Line28"),
                City:                 models.ToPointer("City4"),
                State:                models.ToPointer("State2"),
                PostalCode:           "PostalCode8",
                Country:              "Country0",
            }),
        }),
        PaymentMethod:          models.ToPointer(models.UpdateOffersPaymentMethod{
            Type:                 "Type4",
            CardDetails:          models.CardDetails{
                FirstName:            models.ToPointer("FirstName6"),
                LastName:             models.ToPointer("LastName6"),
                CardNumber:           "CardNumber2",
                ExpYear:              "ExpYear0",
                ExpMonth:             "ExpMonth2",
                Cvv:                  models.ToPointer("Cvv8"),
            },
        }),
        Metadata:               []models.MetadataItem{
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
        },
    }

}
```

