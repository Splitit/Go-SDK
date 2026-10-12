
# Offers Store Location

## Structure

`OffersStoreLocation`

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
    "splititwebapiv4/models"
)

func main() {
    offersStoreLocation := models.OffersStoreLocation{
        Line1:                "Line12",
        Line2:                models.ToPointer("Line26"),
        City:                 models.ToPointer("City8"),
        State:                models.ToPointer("State4"),
        PostalCode:           "PostalCode4",
        Country:              "Country8",
    }

}
```

