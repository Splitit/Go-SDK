
# Offers Payment Method Response

## Structure

`OffersPaymentMethodResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Last4Digits` | `*string` | Optional | - |
| `BIN` | `*string` | Optional | - |
| `IssuerName` | `*string` | Optional | - |
| `Type` | `string` | Required, Constant | **Value**: `"Card"` |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    offersPaymentMethodResponse := models.OffersPaymentMethodResponse{
        Last4Digits:          models.ToPointer("Last4Digits6"),
        BIN:                  models.ToPointer("BIN0"),
        IssuerName:           models.ToPointer("IssuerName0"),
        Type:                 "Card",
    }

}
```

