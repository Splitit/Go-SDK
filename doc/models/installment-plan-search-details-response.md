
# Installment Plan Search Details Response

## Structure

`InstallmentPlanSearchDetailsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `PlanList` | [`[]models.InstallmentPlanDetailsResponse`](../../doc/models/installment-plan-details-response.md) | Optional | - |

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
    installmentPlanSearchDetailsResponse := models.InstallmentPlanSearchDetailsResponse{
        PlanList:             []models.InstallmentPlanDetailsResponse{
            models.InstallmentPlanDetailsResponse{
                DateCreated:            parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) }),
                Status:                 models.InstallmentPlanStatusEnum_INPROGRESS,
                InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber0"),
                MerchantOrderReference: models.ToPointer("MerchantOrderReference8"),
                InstallmentProvider:    models.ExternalProviderTypesEnum_MASTERCARD,
                PurchaseMethod:         models.PurchaseMethodEnum_ECOMMERCE,
                Currency:               models.ToPointer("Currency4"),
                PurchaseAmount:         float64(85.72),
                TotalAmount:            float64(116.66),
                TotalFees:              float64(58.1),
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
            },
            models.InstallmentPlanDetailsResponse{
                DateCreated:            parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) }),
                Status:                 models.InstallmentPlanStatusEnum_INPROGRESS,
                InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber0"),
                MerchantOrderReference: models.ToPointer("MerchantOrderReference8"),
                InstallmentProvider:    models.ExternalProviderTypesEnum_MASTERCARD,
                PurchaseMethod:         models.PurchaseMethodEnum_ECOMMERCE,
                Currency:               models.ToPointer("Currency4"),
                PurchaseAmount:         float64(85.72),
                TotalAmount:            float64(116.66),
                TotalFees:              float64(58.1),
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
            },
        },
    }

}
```

