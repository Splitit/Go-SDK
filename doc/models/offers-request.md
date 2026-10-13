
# Offers Request

## Structure

`OffersRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `MerchantOrderReference` | `*string` | Optional | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `PurchaseAmount` | `string` | Required | - |
| `Currency` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `ShopperDetails` | [`models.OffersShopperDetails`](../../doc/models/offers-shopper-details.md) | Required | - |
| `PaymentMethod` | [`models.OffersPaymentMethod`](../../doc/models/offers-payment-method.md) | Required | - |
| `MerchantDetails` | [`*models.OffersMerchantDetails`](../../doc/models/offers-merchant-details.md) | Optional | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    offersRequest := models.OffersRequest{
        MerchantOrderReference: models.ToPointer("MerchantOrderReference8"),
        PurchaseMethod:         models.PurchaseMethodEnum_ECOMMERCE,
        PurchaseAmount:         "PurchaseAmount4",
        Currency:               "Currency0",
        ShopperDetails:         models.OffersShopperDetails{
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
        },
        PaymentMethod:          models.OffersPaymentMethod{
            Type:                 "Card",
            CardDetails:          models.OffersCardDetails{
                FirstName:            models.ToPointer("FirstName6"),
                LastName:             models.ToPointer("LastName6"),
                CardNumber:           "CardNumber2",
                ExpMonth:             90,
                ExpYear:              228,
                Cvv:                  models.ToPointer("Cvv8"),
            },
        },
        MerchantDetails:        models.ToPointer(models.OffersMerchantDetails{
            StoreName:            models.ToPointer("StoreName8"),
            StoreId:              models.ToPointer("StoreId2"),
            StoreLocation:        models.OffersStoreLocation{
                Line1:                "Line14",
                Line2:                models.ToPointer("Line28"),
                City:                 models.ToPointer("City6"),
                State:                models.ToPointer("State2"),
                PostalCode:           "PostalCode2",
                Country:              "Country0",
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
        },
    }

}
```

