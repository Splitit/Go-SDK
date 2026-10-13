
# Installment Plan Search Request

## Structure

`InstallmentPlanSearchRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumbers` | `[]string` | Optional | - |
| `MerchantOrderReferenceIds` | `[]string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    installmentPlanSearchRequest := models.InstallmentPlanSearchRequest{
        InstallmentPlanNumbers:    []string{
            "InstallmentPlanNumbers9",
        },
        MerchantOrderReferenceIds: []string{
            "MerchantOrderReferenceIds9",
        },
    }

}
```

