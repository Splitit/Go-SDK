
# Installment Plan Initiate Request

## Structure

`InstallmentPlanInitiateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AutoCapture` | `*bool` | Optional | - |
| `Attempt3dSecure` | `*bool` | Optional | - |
| `Shopper` | [`*models.ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `PlanData` | [`*models.PlanDataModel`](../../doc/models/plan-data-model.md) | Optional | - |
| `BillingAddress` | [`*models.AddressDataModel`](../../doc/models/address-data-model.md) | Optional | - |
| `RedirectUrls` | [`*models.InitiateRedirectionEndpointsModel`](../../doc/models/initiate-redirection-endpoints-model.md) | Optional | - |
| `UxSettings` | [`*models.UxSettingsModel`](../../doc/models/ux-settings-model.md) | Optional | - |
| `EventsEndpoints` | [`*models.EventsEndpointsModel`](../../doc/models/events-endpoints-model.md) | Optional | - |
| `ProcessingData` | [`*models.ProcessingData`](../../doc/models/processing-data.md) | Optional | - |

## Example (as JSON)

```json
{
  "AutoCapture": false,
  "Attempt3dSecure": false,
  "Shopper": null,
  "PlanData": null,
  "BillingAddress": null
}
```

