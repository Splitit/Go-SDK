
# Installment Plan Refund Request

## Structure

`InstallmentPlanRefundRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Amount` | `string` | Required | - |
| `RefundStrategy` | [`*models.RefundStrategyEnum`](../../doc/models/refund-strategy-enum.md) | Optional | - |
| `ReferenceId` | `*string` | Optional | - |

## Example (as JSON)

```json
{
  "Amount": "Amount4",
  "RefundStrategy": "FutureInstallmentsNotAllowed",
  "ReferenceId": "ReferenceId0"
}
```

