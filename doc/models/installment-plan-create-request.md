
# Installment Plan Create Request

## Structure

`InstallmentPlanCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AutoCapture` | `bool` | Required | - |
| `Attempt3dSecure` | `*bool` | Optional | - |
| `TermsAndConditionsAccepted` | `bool` | Required | - |
| `Shopper` | [`*models.ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `PlanData` | [`*models.PlanDataModel`](../../doc/models/plan-data-model.md) | Optional | - |
| `BillingAddress` | [`*models.AddressDataModel`](../../doc/models/address-data-model.md) | Optional | - |
| `PaymentMethod` | [`*models.PaymentMethodModel`](../../doc/models/payment-method-model.md) | Optional | - |
| `RedirectUrls` | [`*models.RedirectionEndpointsModel`](../../doc/models/redirection-endpoints-model.md) | Optional | - |
| `ProcessingData` | [`*models.ProcessingData`](../../doc/models/processing-data.md) | Optional | - |
| `EventsEndpoints` | [`*models.EventsEndpointsModel`](../../doc/models/events-endpoints-model.md) | Optional | - |

## Example (as JSON)

```json
{
  "AutoCapture": false,
  "Attempt3dSecure": false,
  "TermsAndConditionsAccepted": false,
  "Shopper": null,
  "PlanData": null,
  "BillingAddress": null,
  "PaymentMethod": null
}
```

