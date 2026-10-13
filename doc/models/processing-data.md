
# Processing Data

## Structure

`ProcessingData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `SoftDescriptor` | `*string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    processingData := models.ProcessingData{
        SoftDescriptor:       models.ToPointer("SoftDescriptor2"),
    }

}
```

