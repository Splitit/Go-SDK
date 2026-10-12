
# Plan Data Model

## Structure

`PlanDataModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TotalAmount` | `string` | Required | - |
| `Currency` | `*string` | Optional | - |
| `NumberOfInstallments` | `models.Optional[int]` | Optional | - |
| `TerminalId` | `*string` | Optional | - |
| `PurchaseMethod` | [`models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `RefOrderNumber` | `*string` | Optional | - |
| `ExtendedParams` | `map[string]string` | Optional | - |
| `FirstInstallmentAmount` | `*string` | Optional | - |
| `FirstInstallmentDate` | `*time.Time` | Optional | - |

## Example (as JSON)

```json
{
  "TotalAmount": "TotalAmount4",
  "Currency": "Currency6",
  "NumberOfInstallments": 154,
  "TerminalId": "TerminalId8",
  "PurchaseMethod": "ECommerce",
  "RefOrderNumber": "RefOrderNumber2",
  "ExtendedParams": {
    "key0": "ExtendedParams6",
    "key1": "ExtendedParams5",
    "key2": "ExtendedParams4"
  }
}
```

