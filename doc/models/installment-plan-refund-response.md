
# Installment Plan Refund Response

## Structure

`InstallmentPlanRefundResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefundId` | `*string` | Optional | - |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `Currency` | `*string` | Optional | - |
| `NonCreditRefundAmount` | `*float64` | Optional | - |
| `CreditRefundAmount` | `*float64` | Optional | - |
| `Summary` | [`*models.RefundSummary`](../../doc/models/refund-summary.md) | Optional | - |
| `ReferenceId` | `*string` | Optional | - |

## Example (as JSON)

```json
{
  "RefundId": "RefundId8",
  "InstallmentPlanNumber": "InstallmentPlanNumber6",
  "Currency": "Currency0",
  "NonCreditRefundAmount": 1.76,
  "CreditRefundAmount": 182.3
}
```

