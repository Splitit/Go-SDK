
# Card Validity Request

## Structure

`CardValidityRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `PaymentMethod` | [`*models.PaymentMethod`](../../doc/models/payment-method.md) | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    cardValidityRequest := models.CardValidityRequest{
        PaymentMethod:        models.ToPointer(models.PaymentMethod{
            Type:                 "Type4",
            Value:                "Value2",
        }),
    }

}
```

