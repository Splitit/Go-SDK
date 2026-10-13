
# Update Offers Payment Method

## Structure

`UpdateOffersPaymentMethod`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `string` | Required, Constant | **Value**: `"Card"` |
| `CardDetails` | [`models.CardDetails`](../../doc/models/card-details.md) | Required | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    updateOffersPaymentMethod := models.UpdateOffersPaymentMethod{
        Type:                 "Card",
        CardDetails:          models.CardDetails{
            FirstName:            models.ToPointer("FirstName6"),
            LastName:             models.ToPointer("LastName6"),
            CardNumber:           "CardNumber2",
            ExpYear:              "ExpYear0",
            ExpMonth:             "ExpMonth2",
            Cvv:                  models.ToPointer("Cvv8"),
        },
    }

}
```

