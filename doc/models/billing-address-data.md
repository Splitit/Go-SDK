
# Billing Address Data

## Structure

`BillingAddressData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Line1` | `*string` | Optional | - |
| `Line2` | `*string` | Optional | - |
| `City` | `*string` | Optional | - |
| `State` | `*string` | Optional | - |
| `PostalCode` | `*string` | Optional | - |
| `Country` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    billingAddressData := models.BillingAddressData{
        Line1:                models.ToPointer("Line16"),
        Line2:                models.ToPointer("Line20"),
        City:                 models.ToPointer("City4"),
        State:                models.ToPointer("State0"),
        PostalCode:           models.ToPointer("PostalCode0"),
    }

}
```

