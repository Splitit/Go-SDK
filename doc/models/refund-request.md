
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
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    refundRequest := models.RefundRequest{
        Amount:               "Amount6",
        ReferenceId:          models.ToPointer("ReferenceId2"),
    }

}
```

