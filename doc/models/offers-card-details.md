
# Offers Card Details

## Structure

`OffersCardDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FirstName` | `*string` | Optional | - |
| `LastName` | `*string` | Optional | - |
| `CardNumber` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `ExpMonth` | `int` | Required | - |
| `ExpYear` | `int` | Required | - |
| `Cvv` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    offersCardDetails := models.OffersCardDetails{
        FirstName:            models.ToPointer("FirstName4"),
        LastName:             models.ToPointer("LastName4"),
        CardNumber:           "CardNumber2",
        ExpMonth:             148,
        ExpYear:              30,
        Cvv:                  models.ToPointer("Cvv2"),
    }

}
```

