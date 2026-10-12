
# Three DS Redirect Data

## Structure

`ThreeDSRedirectData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Url` | `*string` | Optional | - |
| `Verb` | `*string` | Optional | - |
| `Params` | `map[string]string` | Optional | - |
| `ClientRedirectUrl` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    threeDSRedirectData := models.ThreeDSRedirectData{
        Url:                  models.ToPointer("Url0"),
        Verb:                 models.ToPointer("Verb4"),
        Params:               map[string]string{
            "key0": "Params8",
            "key1": "Params9",
            "key2": "Params0",
        },
        ClientRedirectUrl:    models.ToPointer("ClientRedirectUrl0"),
    }

}
```

