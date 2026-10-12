
# Three DS Authentication Data

## Structure

`ThreeDSAuthenticationData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ECI` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `CAVV` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `DirectoryServerTransactionId` | `string` | Required | **Constraints**: *Minimum Length*: `1` |
| `Version` | `string` | Required | **Constraints**: *Minimum Length*: `1` |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    threeDSAuthenticationData := models.ThreeDSAuthenticationData{
        ECI:                          "ECI2",
        CAVV:                         "CAVV0",
        DirectoryServerTransactionId: "DirectoryServerTransactionId4",
        Version:                      "Version6",
    }

}
```

