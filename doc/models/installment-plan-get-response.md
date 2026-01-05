
# Installment Plan Get Response

## Structure

`InstallmentPlanGetResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumber` | `*string` | Optional | - |
| `DateCreated` | `time.Time` | Required | - |
| `RefOrderNumber` | `*string` | Optional | - |
| `PurchaseMethod` | [`*models.PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Optional | - |
| `Status` | [`models.PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `Currency` | `*string` | Optional | - |
| `OriginalAmount` | `*float64` | Optional | - |
| `Amount` | `*float64` | Optional | - |
| `Authorization` | [`*models.AuthorizationModel`](../../doc/models/authorization-model.md) | Optional | - |
| `Shopper` | [`*models.ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `BillingAddress` | [`*models.AddressData`](../../doc/models/address-data.md) | Optional | - |
| `PaymentMethod` | [`*models.PaymentMethodModel`](../../doc/models/payment-method-model.md) | Optional | - |
| `ExtendedParams` | `map[string]string` | Optional | - |
| `Installments` | [`[]models.Installment`](../../doc/models/installment.md) | Optional | - |
| `Refunds` | [`[]models.RefundModel`](../../doc/models/refund-model.md) | Optional | - |
| `Links` | [`*models.LinksData`](../../doc/models/links-data.md) | Optional | - |

## Example (as JSON)

```json
{
  "InstallmentPlanNumber": "InstallmentPlanNumber4",
  "DateCreated": "2016-03-13T12:52:32.123Z",
  "RefOrderNumber": "RefOrderNumber4",
  "PurchaseMethod": "InStore",
  "Status": "Cleared",
  "Currency": "Currency8",
  "OriginalAmount": 2.6
}
```

