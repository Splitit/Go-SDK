
# Payment Link Request

## Structure

`PaymentLinkRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Amount` | `string` | Required | - |
| `Currency` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `AutoCapture` | `*bool` | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `ShopperDetails` | [`models.OffersShopperDetails`](../../doc/models/offers-shopper-details.md) | Required | - |
| `MerchantDetails` | [`*models.OffersMerchantDetails`](../../doc/models/offers-merchant-details.md) | Optional | - |
| `CheckoutUrlValidity` | `*time.Time` | Optional | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |
| `RedirectUrls` | [`*models.RedirectUrls`](../../doc/models/redirect-urls.md) | Optional | - |
| `ProcessingData` | [`*models.ProcessingData`](../../doc/models/processing-data.md) | Optional | - |
| `ThreeDS` | [`*models.ThreeDSExecute`](../../doc/models/three-ds-execute.md) | Optional | - |

## Example

```go
package main

import (
    "log"
    "time"
    "splititwebapiv4/models"
)

func main() {
    parseTime := func(layout, value string, errCallback func(error)) time.Time {
        dateTime, err := time.Parse(layout, value)
        if err != nil {
            errCallback(err) 
       }
        return dateTime
    }
    paymentLinkRequest := models.PaymentLinkRequest{
        Amount:                 "Amount2",
        Currency:               "Currency8",
        AutoCapture:            models.ToPointer(false),
        MerchantOrderReference: models.ToPointer("MerchantOrderReference4"),
        PurchaseMethod:         models.PurchaseMethodEnum_ECOMMERCE,
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
        CheckoutUrlValidity:    models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
        Metadata:               []models.MetadataItem{
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
        },
    }

}
```

