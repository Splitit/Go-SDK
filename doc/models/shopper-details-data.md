
# Shopper Details Data

## Structure

`ShopperDetailsData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FirstName` | `*string` | Optional | - |
| `LastName` | `*string` | Optional | - |
| `Email` | `*string` | Optional | - |
| `PhoneNumber` | `*string` | Optional | - |
| `Culture` | `*string` | Optional | - |
| `BillingAddress` | [`*models.BillingAddressData`](../../doc/models/billing-address-data.md) | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    shopperDetailsData := models.ShopperDetailsData{
        FirstName:            models.ToPointer("FirstName2"),
        LastName:             models.ToPointer("LastName2"),
        Email:                models.ToPointer("Email2"),
        PhoneNumber:          models.ToPointer("PhoneNumber4"),
        Culture:              models.ToPointer("Culture8"),
    }

}
```

