
# Payment Method

## Structure

`PaymentMethod`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `string` | Required, Constant | **Value**: `"Card"` |
| `Value` | `string` | Required | **Constraints**: *Minimum Length*: `1` |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    paymentMethod := models.PaymentMethod{
        Type:                 "Card",
        Value:                "Value0",
    }

}
```

