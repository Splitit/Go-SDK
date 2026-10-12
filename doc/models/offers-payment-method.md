
# Offers Payment Method

## Structure

`OffersPaymentMethod`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `string` | Required, Constant | **Value**: `"Card"` |
| `CardDetails` | [`models.OffersCardDetails`](../../doc/models/offers-card-details.md) | Required | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    offersPaymentMethod := models.OffersPaymentMethod{
        Type:                 "Card",
        CardDetails:          models.OffersCardDetails{
            FirstName:            models.ToPointer("FirstName6"),
            LastName:             models.ToPointer("LastName6"),
            CardNumber:           "CardNumber2",
            ExpMonth:             90,
            ExpYear:              228,
            Cvv:                  models.ToPointer("Cvv8"),
        },
    }

}
```

