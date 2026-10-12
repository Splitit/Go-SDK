
# Update Order Response

## Structure

`UpdateOrderResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Status` | [`models.PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `MerchantOrderReference` | `*string` | Optional | - |
| `TrackingNumber` | `*string` | Optional | - |
| `ShippingStatus` | [`*models.ShippingStatusEnum`](../../doc/models/shipping-status-enum.md) | Optional | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    updateOrderResponse := models.UpdateOrderResponse{
        Status:                 models.PlanStatusEnum_ACTIVE,
        MerchantOrderReference: models.ToPointer("MerchantOrderReference0"),
        TrackingNumber:         models.ToPointer("TrackingNumber0"),
        ShippingStatus:         models.ToPointer(models.ShippingStatusEnum_PENDING),
        Metadata:               []models.MetadataItem{
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
        },
        InstallmentPlanNumber:  models.ToPointer("InstallmentPlanNumber8"),
    }

}
```

