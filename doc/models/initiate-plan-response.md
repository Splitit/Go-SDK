
# Initiate Plan Response

## Structure

`InitiatePlanResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `RefOrderNumber` | `*string` | Optional | - |
| `PurchaseMethod` | [`*models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Optional | - |
| `Status` | [`models.PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `Currency` | `*string` | Optional | - |
| `Amount` | `*float64` | Optional | - |
| `ExtendedParams` | `map[string]string` | Optional | - |
| `Shopper` | [`*models.ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `BillingAddress` | [`*models.AddressData`](../../doc/models/address-data.md) | Optional | - |
| `CheckoutUrl` | `*string` | Optional | - |
| `PrincipalAmount` | `*float64` | Optional | - |

## Example (as JSON)

```json
{
  "InstallmentPlanNumber": "InstallmentPlanNumber6",
  "RefOrderNumber": "RefOrderNumber6",
  "PurchaseMethod": "InStore",
  "Status": "Initialized",
  "Currency": "Currency0",
  "Amount": 69.84
}
```

