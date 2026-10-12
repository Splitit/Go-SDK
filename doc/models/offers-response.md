
# Offers Response

## Structure

`OffersResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `PurchaseAmount` | `float64` | Required | - |
| `Currency` | `*string` | Optional | - |
| `PaymentMethod` | [`*models.OffersPaymentMethodResponse`](../../doc/models/offers-payment-method-response.md) | Optional | - |
| `Offers` | [`[]models.OfferItem`](../../doc/models/offer-item.md) | Optional | - |
| `ValidUntil` | `*time.Time` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    offersResponse := models.OffersResponse{
        InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber8"),
        MerchantOrderReference: models.ToPointer("MerchantOrderReference0"),
        PurchaseMethod:         models.PurchaseMethodEnum_ECOMMERCE,
        PurchaseAmount:         float64(1.74),
        Currency:               models.ToPointer("Currency2"),
        PaymentMethod:          models.ToPointer(models.OffersPaymentMethodResponse{
            Last4Digits:          models.ToPointer("Last4Digits6"),
            BIN:                  models.ToPointer("BIN0"),
            IssuerName:           models.ToPointer("IssuerName0"),
            Type:                 "Type4",
        }),
        Offers:                 []models.OfferItem{
            models.OfferItem{
                OfferId:                models.ToPointer("OfferId2"),
                Apr:                    models.ToPointer(models.AprData{
                    Value:                float64(24.74),
                    Symbol:               models.ToPointer("Symbol8"),
                }),
                Currency:               models.ToPointer("Currency8"),
                TotalAmount:            float64(35.88),
                TotalFees:              float64(210.64),
                NumberOfInstallments:   194,
                Frequency:              models.ToPointer("Frequency2"),
                InstallmentAmount:      float64(52.64),
                FirstInstallmentAmount: float64(121.96),
                LastInstallmentAmount:  models.ToPointer(models.AmountData{
                    Value:                float64(181.16),
                    Symbol:               models.ToPointer("Symbol2"),
                }),
            },
        },
    }

}
```

