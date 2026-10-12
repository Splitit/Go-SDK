
# Update Order Request

## Structure

`UpdateOrderRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TrackingNumber` | `*string` | Optional | - |
| `ShippingStatus` | [`models.ShippingStatusEnum`](../../doc/models/shipping-status-enum.md) | Required | - |
| `Metadata` | [`[]models.MetadataItem`](../../doc/models/metadata-item.md) | Optional | - |
| `MerchantOrderReference` | `*string` | Optional | - |

## Example

```go
package main

import (
    "splititwebapiv4/models"
)

func main() {
    updateOrderRequest := models.UpdateOrderRequest{
        TrackingNumber:         models.ToPointer("TrackingNumber2"),
        ShippingStatus:         models.ShippingStatusEnum_PENDING,
        Metadata:               []models.MetadataItem{
            models.MetadataItem{
                Key:                  models.ToPointer("Key2"),
                Value:                models.ToPointer("Value4"),
            },
        },
        MerchantOrderReference: models.ToPointer("MerchantOrderReference2"),
    }

}
```

