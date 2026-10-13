
# Authorization Status Enum

## Enumeration

`AuthorizationStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SUCCEEDED` | Authorization succeeded |
| `PENDING3DS` | Waiting for 3DS authentication |
| `FAILED` | Authorization Failed |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    authorizationStatus := models.AuthorizationStatusEnum_PENDING3DS

}
```

