
# Metadata Item

## Structure

`MetadataItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Key` | `*string` | Optional | - |
| `Value` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    metadataItem := models.MetadataItem{
        Key:                  models.ToPointer("Key0"),
        Value:                models.ToPointer("Value6"),
    }

}
```

