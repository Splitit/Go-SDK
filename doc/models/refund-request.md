
# Refund Request

## Structure

`RefundRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Amount` | `string` | Required | - |
| `ReferenceId` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    refundRequest := models.RefundRequest{
        Amount:               "Amount6",
        ReferenceId:          models.ToPointer("ReferenceId2"),
    }

}
```

