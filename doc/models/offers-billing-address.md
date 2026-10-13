
# Offers Billing Address

## Structure

`OffersBillingAddress`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Line1` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `Line2` | `*string` | Optional | - |
| `City` | `*string` | Optional | - |
| `State` | `*string` | Optional | - |
| `PostalCode` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `Country` | `string` | Required | **Constraints**: *Minimum Length*: `1` |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    offersBillingAddress := models.OffersBillingAddress{
        Line1:                "Line16",
        Line2:                models.ToPointer("Line20"),
        City:                 models.ToPointer("City6"),
        State:                models.ToPointer("State0"),
        PostalCode:           "PostalCode0",
        Country:              "Country2",
    }

}
```

