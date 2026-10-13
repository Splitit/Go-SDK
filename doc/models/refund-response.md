
# Refund Response

## Structure

`RefundResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefundId` | `*string` | Optional | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `Currency` | `*string` | Optional | - |
| `RequestedAmount` | `float64` | Required | - |
| `ReferenceId` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    refundResponse := models.RefundResponse{
        RefundId:              models.ToPointer("RefundId6"),
        InstallmentPlanNumber: models.ToPointer("InstallmentPlanNumber8"),
        Currency:              models.ToPointer("Currency2"),
        RequestedAmount:       float64(24.4),
        ReferenceId:           models.ToPointer("ReferenceId8"),
    }

}
```

