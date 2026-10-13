
# Amount Data

## Structure

`AmountData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Value` | `float64` | Required | - |
| `Symbol` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    amountData := models.AmountData{
        Value:                float64(229.08),
        Symbol:               models.ToPointer("Symbol6"),
    }

}
```

