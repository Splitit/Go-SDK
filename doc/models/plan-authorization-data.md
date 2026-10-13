
# Plan Authorization Data

## Structure

`PlanAuthorizationData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Status` | [`models.AuthorizationStatusEnum`](../../doc/models/authorization-status-enum.md) | Required | - |
| `Date` | `*time.Time` | Optional | - |
| `SplititErrorResultCode` | `*string` | Optional | - |
| `GatewayTransactionID` | `*string` | Optional | - |
| `GatewayResultCode` | `*string` | Optional | - |
| `GatewayResultMessage` | `*string` | Optional | - |
| `ThreeDSRedirect` | [`*models.ThreeDSRedirectData`](../../doc/models/three-ds-redirect-data.md) | Optional | - |
| `CAVV` | `*string` | Optional | - |
| `ECI` | `*string` | Optional | - |
| `GatewaySourceResponse` | `*string` | Optional | - |

## Example

```go
package main

import (
    "log"
    "time"
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    parseTime := func(layout, value string, errCallback func(error)) time.Time {
        dateTime, err := time.Parse(layout, value)
        if err != nil {
            errCallback(err) 
       }
        return dateTime
    }
    planAuthorizationData := models.PlanAuthorizationData{
        Status:                 models.AuthorizationStatusEnum_SUCCEEDED,
        Date:                   models.ToPointer(parseTime(time.RFC3339, "2016-03-13T12:52:32.123Z", func(err error) { log.Fatalln(err) })),
        SplititErrorResultCode: models.ToPointer("SplititErrorResultCode2"),
        GatewayTransactionID:   models.ToPointer("GatewayTransactionID8"),
        GatewayResultCode:      models.ToPointer("GatewayResultCode4"),
        GatewayResultMessage:   models.ToPointer("GatewayResultMessage0"),
    }

}
```

