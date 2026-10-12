
# Installment Plan Update Request

## Structure

`InstallmentPlanUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefOrderNumber` | `*string` | Optional | - |
| `TrackingNumber` | `*string` | Optional | - |
| `Capture` | `*bool` | Optional | - |
| `ShippingStatus` | [`*models.ShippingStatusEnum`](../../doc/models/shipping-status-enum.md) | Optional | - |
| `NewAmount` | `*string` | Optional | - |

## Example (as JSON)

```json
{
  "RefOrderNumber": "RefOrderNumber2",
  "TrackingNumber": "TrackingNumber6",
  "Capture": false,
  "ShippingStatus": "Shipped",
  "NewAmount": "NewAmount4"
}
```

