
# Offer Item

## Structure

`OfferItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `OfferId` | `*string` | Optional | - |
| `Apr` | [`*models.AprData`](../../doc/models/apr-data.md) | Optional | - |
| `Currency` | `*string` | Optional | - |
| `TotalAmount` | `float64` | Required | - |
| `TotalFees` | `float64` | Required | - |
| `NumberOfInstallments` | `int` | Required | - |
| `Frequency` | `*string` | Optional | - |
| `InstallmentAmount` | `float64` | Required | - |
| `FirstInstallmentAmount` | `float64` | Required | - |
| `LastInstallmentAmount` | [`*models.AmountData`](../../doc/models/amount-data.md) | Optional | - |
| `InlineContent` | [`*models.InlineContent`](../../doc/models/inline-content.md) | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    offerItem := models.OfferItem{
        OfferId:                models.ToPointer("OfferId2"),
        Apr:                    models.ToPointer(models.AprData{
            Value:                float64(24.74),
            Symbol:               models.ToPointer("Symbol8"),
        }),
        Currency:               models.ToPointer("Currency8"),
        TotalAmount:            float64(199.92),
        TotalFees:              float64(230.84),
        NumberOfInstallments:   90,
        Frequency:              models.ToPointer("Frequency2"),
        InstallmentAmount:      float64(32.44),
        FirstInstallmentAmount: float64(101.76),
        LastInstallmentAmount:  models.ToPointer(models.AmountData{
            Value:                float64(181.16),
            Symbol:               models.ToPointer("Symbol2"),
        }),
    }

}
```

