
# Card Validity Response

## Structure

`CardValidityResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Result` | `bool` | Required | - |
| `ValidationErrors` | [`[]models.ValidationError`](../../doc/models/validation-error.md) | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    cardValidityResponse := models.CardValidityResponse{
        Result:               false,
        ValidationErrors:     []models.ValidationError{
            models.ValidationError{
                Code:                 models.ToPointer(models.PisErrorCodesEnum_PLANHASMOREOPENAUTHORIZATIONS),
                Message:              models.ToPointer("Message8"),
            },
            models.ValidationError{
                Code:                 models.ToPointer(models.PisErrorCodesEnum_PLANHASMOREOPENAUTHORIZATIONS),
                Message:              models.ToPointer("Message8"),
            },
        },
    }

}
```

