
# Masked Card Details

## Structure

`MaskedCardDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Last4Digits` | `*string` | Optional | - |
| `BIN` | `*string` | Optional | - |
| `IssuerName` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    maskedCardDetails := models.MaskedCardDetails{
        Last4Digits:          models.ToPointer("Last4Digits2"),
        BIN:                  models.ToPointer("BIN4"),
        IssuerName:           models.ToPointer("IssuerName6"),
    }

}
```

