
# Plan Links Data

## Structure

`PlanLinksData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Key` | `*string` | Optional | - |
| `Label` | `*string` | Optional | - |
| `Value` | `*string` | Optional | - |
| `Description` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    planLinksData := models.PlanLinksData{
        Key:                  models.ToPointer("Key2"),
        Label:                models.ToPointer("Label6"),
        Value:                models.ToPointer("Value4"),
        Description:          models.ToPointer("Description2"),
    }

}
```

