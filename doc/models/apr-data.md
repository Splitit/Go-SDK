
# Apr Data

## Structure

`AprData`

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
    aprData := models.AprData{
        Value:                float64(88.62),
        Symbol:               models.ToPointer("Symbol8"),
    }

}
```

