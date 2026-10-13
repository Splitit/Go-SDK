
# Api Error Model

## Structure

`ApiErrorModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Code` | `*string` | Optional | - |
| `Message` | `*string` | Optional | - |
| `AdditionalInfo` | `*string` | Optional | - |
| `ExtraData` | `map[string]string` | Optional | - |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    apiErrorModel := models.ApiErrorModel{
        Code:                 models.ToPointer("Code6"),
        Message:              models.ToPointer("Message2"),
        AdditionalInfo:       models.ToPointer("AdditionalInfo2"),
        ExtraData:            map[string]string{
            "key0": "ExtraData6",
            "key1": "ExtraData7",
            "key2": "ExtraData8",
        },
    }

}
```

