
# Content Segment

## Structure

`ContentSegment`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | `*string` | Optional | - |
| `Value` | `*string` | Optional | - |
| `Label` | `*string` | Optional | - |
| `Url` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    contentSegment := models.ContentSegment{
        Type:                 models.ToPointer("Type8"),
        Value:                models.ToPointer("Value4"),
        Label:                models.ToPointer("Label6"),
        Url:                  models.ToPointer("Url6"),
    }

}
```

