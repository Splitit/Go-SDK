
# Payment Method Data

## Structure

`PaymentMethodData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `string` | Required, Constant | **Value**: `"Card"` |
| `CardDetails` | [`*models.MaskedCardDetails`](../../doc/models/masked-card-details.md) | Optional | - |
| `Par` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    paymentMethodData := models.PaymentMethodData{
        Type:                 "Card",
        CardDetails:          models.ToPointer(models.MaskedCardDetails{
            Last4Digits:          models.ToPointer("Last4Digits2"),
            BIN:                  models.ToPointer("BIN6"),
            IssuerName:           models.ToPointer("IssuerName6"),
        }),
        Par:                  models.ToPointer("Par8"),
    }

}
```

