
# Validation Error

## Structure

`ValidationError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Code` | [`*models.PisErrorCodesEnum`](../../doc/models/pis-error-codes-enum.md) | Optional | - |
| `Message` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    validationError := models.ValidationError{
        Code:                 models.ToPointer(models.PisErrorCodesEnum_ACTIVITYNOTALLOWEDDUETOPRIVACYPROTECTION),
        Message:              models.ToPointer("Message4"),
    }

}
```

