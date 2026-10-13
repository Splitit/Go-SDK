
# Authorize Authorization Data

## Structure

`AuthorizeAuthorizationData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Status` | [`models.AuthorizationStatusEnum`](../../doc/models/authorization-status-enum.md) | Required | - |
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
    "github.com/Splitit/go-sdk/v2/models"
)

func main() {
    authorizeAuthorizationData := models.AuthorizeAuthorizationData{
        Status:                 models.AuthorizationStatusEnum_PENDING3DS,
        SplititErrorResultCode: models.ToPointer("SplititErrorResultCode4"),
        GatewayTransactionID:   models.ToPointer("GatewayTransactionID0"),
        GatewayResultCode:      models.ToPointer("GatewayResultCode2"),
        GatewayResultMessage:   models.ToPointer("GatewayResultMessage8"),
        ThreeDSRedirect:        models.ToPointer(models.ThreeDSRedirectData{
            Url:                  models.ToPointer("Url2"),
            Verb:                 models.ToPointer("Verb2"),
            Params:               map[string]string{
                "key0": "Params6",
                "key1": "Params7",
            },
            ClientRedirectUrl:    models.ToPointer("ClientRedirectUrl8"),
        }),
    }

}
```

