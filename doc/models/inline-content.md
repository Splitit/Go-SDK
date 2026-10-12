
# Inline Content

## Structure

`InlineContent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Segments` | [`[]models.ContentSegment`](../../doc/models/content-segment.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    inlineContent := models.InlineContent{
        Segments:             []models.ContentSegment{
            models.ContentSegment{
                Type:                 models.ToPointer("Type2"),
                Value:                models.ToPointer("Value0"),
                Label:                models.ToPointer("Label0"),
                Url:                  models.ToPointer("Url0"),
            },
        },
    }

}
```

