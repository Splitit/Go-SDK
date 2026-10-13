
# Installment Status Enum

## Enumeration

`InstallmentStatusEnum`

## Fields

| Name |
|  --- |
| `NONE` |
| `WAITINGFORPROCESSDATE` |
| `FINISHED` |
| `DELETED` |
| `STOPPED` |
| `CANCELED` |
| `AWAITINGCAPTURE` |
| `AWAITINGVOID` |

## Example

```go
package main

import (
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    installmentStatus := models.InstallmentStatusEnum_AWAITINGCAPTURE

}
```

