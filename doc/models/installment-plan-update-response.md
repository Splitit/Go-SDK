
# Installment Plan Update Response

## Structure

`InstallmentPlanUpdateResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefOrderNumber` | `*string` | Optional | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `Status` | [`models.PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `ShippingStatus` | [`models.ShippingStatusEnum`](../../doc/models/shipping-status-enum.md) | Required | - |
| `NewAmount` | `*float64` | Optional | - |

## Example (as JSON)

```json
{
  "RefOrderNumber": "RefOrderNumber2",
  "InstallmentPlanNumber": "InstallmentPlanNumber2",
  "Status": "PendingCapture",
  "ShippingStatus": "Delivered",
  "NewAmount": 233.54
}
```

