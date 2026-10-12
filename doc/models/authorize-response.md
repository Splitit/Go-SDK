
# Authorize Response

## Structure

`AuthorizeResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `DateCreated` | `time.Time` | Required | - |
| `PlanStatus` | [`models.InstallmentPlanStatusEnum`](../../doc/models/installment-plan-status-enum.md) | Required | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `Currency` | `*string` | Optional | - |
| `PurchaseAmount` | `float64` | Required | - |
| `TotalFees` | `float64` | Required | - |
| `TotalAmount` | `float64` | Required | - |
| `Apr` | [`*models.AprData`](../../doc/models/apr-data.md) | Optional | - |
| `Authorization` | [`*models.AuthorizeAuthorizationData`](../../doc/models/authorize-authorization-data.md) | Optional | - |
| `PaymentMethod` | [`*models.PaymentMethodData`](../../doc/models/payment-method-data.md) | Optional | - |
| `Installments` | [`[]models.InstallmentItem`](../../doc/models/installment-item.md) | Optional | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |

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
    authorizeResponse := models.AuthorizeResponse{
        DateCreated:            parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) }),
        PlanStatus:             models.InstallmentPlanStatusEnum_ALLSTATUSES,
        InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber0"),
        MerchantOrderReference: models.ToPointer("MerchantOrderReference2"),
        PurchaseMethod:         models.PurchaseMethodEnum_INSTORE,
        Currency:               models.ToPointer("Currency4"),
        PurchaseAmount:         float64(47.42),
        TotalFees:              float64(96.4),
        TotalAmount:            float64(78.36),
        Apr:                    models.ToPointer(models.AprData{
            Value:                float64(24.74),
            Symbol:               models.ToPointer("Symbol8"),
        }),
        Authorization:          models.ToPointer(models.AuthorizeAuthorizationData{
            Status:                 models.AuthorizationStatusEnum_PENDING3DS,
            SplititErrorResultCode: models.ToPointer("SplititErrorResultCode4"),
            GatewayTransactionID:   models.ToPointer("GatewayTransactionID0"),
            GatewayResultCode:      models.ToPointer("GatewayResultCode2"),
            GatewayResultMessage:   models.ToPointer("GatewayResultMessage8"),
            ThreeDSRedirect:        models.ToPointer(models.ThreeDSRedirectData{
                Url:                  models.ToPointer("Url2"),
                Verb:                 models.ToPointer("Verb2"),
                Params:               map[string]string{
                    "key0": "Params6",
                    "key1": "Params7",
                },
                ClientRedirectUrl:    models.ToPointer("ClientRedirectUrl8"),
            }),
        }),
    }

}
```

