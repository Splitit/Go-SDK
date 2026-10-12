
# Checkout Url Data

## Structure

`CheckoutUrlData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Url` | `*string` | Optional | - |
| `ValidUntil` | `*time.Time` | Optional | - |

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
    checkoutUrlData := models.CheckoutUrlData{
        Url:                  models.ToPointer("Url6"),
        ValidUntil:           models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
    }

}
```

