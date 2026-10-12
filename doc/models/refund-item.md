
# Refund Item

## Structure

`RefundItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `SubmitDate` | `*time.Time` | Optional | - |
| `RequestedAmount` | `float64` | Required | - |
| `Status` | `*string` | Optional | - |
| `NonCreditRefundAmount` | `*float64` | Optional | - |
| `CreditRefundAmount` | `*float64` | Optional | - |
| `RefundId` | `*string` | Optional | - |
| `ReferenceId` | `*string` | Optional | - |

## Example

```go
package main

import (
    "log"
    "time"
    "splititwebapiv4/models"
)

func main() {
    parseTime := func(layout, value string, errCallback func(error)) time.Time {
        dateTime, err := time.Parse(layout, value)
        if err != nil {
            errCallback(err) 
       }
        return dateTime
    }
    refundItem := models.RefundItem{
        SubmitDate:            models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
        RequestedAmount:       float64(36.1),
        Status:                models.ToPointer("Status2"),
        NonCreditRefundAmount: models.ToPointer(float64(6.24)),
        CreditRefundAmount:    models.ToPointer(float64(69.22)),
        RefundId:              models.ToPointer("RefundId6"),
    }

}
```

