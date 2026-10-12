
# Payment Link Response

## Structure

`PaymentLinkResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CheckoutUrl` | [`*models.CheckoutUrlData`](../../doc/models/checkout-url-data.md) | Optional | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `PurchaseAmount` | `float64` | Required | - |
| `Currency` | `*string` | Optional | - |

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
    paymentLinkResponse := models.PaymentLinkResponse{
        CheckoutUrl:            models.ToPointer(models.CheckoutUrlData{
            Url:                  models.ToPointer("Url8"),
            ValidUntil:           models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
        }),
        InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber0"),
        MerchantOrderReference: models.ToPointer("MerchantOrderReference8"),
        PurchaseAmount:         float64(144.52),
        Currency:               models.ToPointer("Currency4"),
    }

}
```

