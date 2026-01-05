
# Plan Data

## Structure

`PlanData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TerminalId` | `*string` | Optional | - |
| `TotalAmount` | `string` | Required | - |
| `FirstInstallmentAmount` | `*float64` | Optional | - |
| `Currency` | `*string` | Optional | - |
| `NumberOfInstallments` | `int` | Required | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `RefOrderNumber` | `*string` | Optional | - |
| `AllowedInstallmentOptions` | `[]int` | Optional | - |
| `Tags` | `map[string]string` | Optional | - |
| `ProcessingData` | [`*models.ProcessingData`](../../doc/models/processing-data.md) | Optional | - |
| `FirstInstallmentDate` | `*time.Time` | Optional | - |

## Example (as JSON)

```json
{
  "TerminalId": "TerminalId8",
  "TotalAmount": "TotalAmount4",
  "FirstInstallmentAmount": 11.28,
  "Currency": "Currency6",
  "NumberOfInstallments": 2,
  "PurchaseMethod": "PhoneOrder",
  "RefOrderNumber": "RefOrderNumber2",
  "AllowedInstallmentOptions": [
    46,
    47
  ]
}
```

