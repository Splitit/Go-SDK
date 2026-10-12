
# Installment Plan Details Response

## Structure

`InstallmentPlanDetailsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `DateCreated` | `time.Time` | Required | - |
| `Status` | [`models.InstallmentPlanStatusEnum`](../../doc/models/installment-plan-status-enum.md) | Required | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `InstallmentProvider` | [`models.ExternalProviderTypesEnum`](../../doc/models/external-provider-types-enum.md) | Required | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `Currency` | `*string` | Optional | - |
| `PurchaseAmount` | `float64` | Required | - |
| `TotalAmount` | `float64` | Required | - |
| `TotalFees` | `float64` | Required | - |
| `Apr` | [`*models.AprData`](../../doc/models/apr-data.md) | Optional | - |
| `Authorization` | [`*models.PlanAuthorizationData`](../../doc/models/plan-authorization-data.md) | Optional | - |
| `ShopperDetails` | [`*models.ShopperDetailsData`](../../doc/models/shopper-details-data.md) | Optional | - |
| `PaymentMethod` | [`*models.PaymentMethodData`](../../doc/models/payment-method-data.md) | Optional | - |
| `Installments` | [`[]models.InstallmentItem`](../../doc/models/installment-item.md) | Optional | - |
| `Refunds` | [`[]models.RefundItem`](../../doc/models/refund-item.md) | Optional | - |
| `Links` | [`[]models.PlanLinksData`](../../doc/models/plan-links-data.md) | Optional | - |
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
    installmentPlanDetailsResponse := models.InstallmentPlanDetailsResponse{
        DateCreated:            parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) }),
        Status:                 models.InstallmentPlanStatusEnum_PENDINGPAYMENTUPDATE,
        InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber6"),
        MerchantOrderReference: models.ToPointer("MerchantOrderReference2"),
        InstallmentProvider:    models.ExternalProviderTypesEnum_WORLDPAY,
        PurchaseMethod:         models.PurchaseMethodEnum_INSTORE,
        Currency:               models.ToPointer("Currency0"),
        PurchaseAmount:         float64(3.16),
        TotalAmount:            float64(34.1),
        TotalFees:              float64(140.66),
        Apr:                    models.ToPointer(models.AprData{
            Value:                float64(24.74),
            Symbol:               models.ToPointer("Symbol8"),
        }),
        Authorization:          models.ToPointer(models.PlanAuthorizationData{
            Status:                 models.AuthorizationStatusEnum_PENDING3DS,
            Date:                   models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
            SplititErrorResultCode: models.ToPointer("SplititErrorResultCode4"),
            GatewayTransactionID:   models.ToPointer("GatewayTransactionID0"),
            GatewayResultCode:      models.ToPointer("GatewayResultCode2"),
            GatewayResultMessage:   models.ToPointer("GatewayResultMessage8"),
        }),
    }

}
```

