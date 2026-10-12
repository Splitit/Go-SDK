
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
    "splititwebapiv4/models"
)

func main() {
    amountData := models.AmountData{
        Value:                float64(229.08),
        Symbol:               models.ToPointer("Symbol6"),
    }

}
```

