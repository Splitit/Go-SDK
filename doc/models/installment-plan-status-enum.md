
# Installment Plan Status Enum

## Enumeration

`InstallmentPlanStatusEnum`

## Fields

| Name |
|  --- |
| `NONE` |
| `PENDINGAPPROVAL` |
| `PENDINGMERCHANTSHIPMENTNOTICE` |
| `INPROGRESS` |
| `DELETED` |
| `CLEARED` |
| `PENDINGPAYMENTUPDATE` |
| `CANCELED` |
| `DELAYED` |
| `INITIALIZING` |
| `ALLSTATUSES` |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    installmentPlanStatus := models.InstallmentPlanStatusEnum_PENDINGAPPROVAL

}
```

