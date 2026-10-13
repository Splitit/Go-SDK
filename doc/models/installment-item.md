
# Installment Item

## Structure

`InstallmentItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentNumber` | `int` | Required | - |
| `Amount` | [`*models.AmountData`](../../doc/models/amount-data.md) | Optional | - |
| `Status` | [`models.InstallmentStatusEnum`](../../doc/models/installment-status-enum.md) | Required | - |
| `ProcessDateTime` | `*time.Time` | Optional | - |

## Example

```go
package main

import (
    "log"
    "time"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    parseTime := func(layout, value string, errCallback func(error)) time.Time {
        dateTime, err := time.Parse(layout, value)
        if err != nil {
            errCallback(err) 
       }
        return dateTime
    }
    installmentItem := models.InstallmentItem{
        InstallmentNumber:    150,
        Amount:               models.ToPointer(models.AmountData{
            Value:                float64(247.24),
            Symbol:               models.ToPointer("Symbol0"),
        }),
        Status:               models.InstallmentStatusEnum_STOPPED,
        ProcessDateTime:      models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
    }

}
```

