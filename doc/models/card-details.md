
# Card Details

## Structure

`CardDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FirstName` | `*string` | Optional | - |
| `LastName` | `*string` | Optional | - |
| `CardNumber` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `ExpYear` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `ExpMonth` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `Cvv` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    cardDetails := models.CardDetails{
        FirstName:            models.ToPointer("FirstName0"),
        LastName:             models.ToPointer("LastName0"),
        CardNumber:           "CardNumber6",
        ExpYear:              "ExpYear4",
        ExpMonth:             "ExpMonth6",
        Cvv:                  models.ToPointer("Cvv8"),
    }

}
```

