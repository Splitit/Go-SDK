
# Payment Plan Option Model

## Structure

`PaymentPlanOptionModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `NumberOfInstallments` | `int` | Required | - |
| `FirstInstallmentAmount` | `float64` | Required | - |
| `InstallmentAmount` | `float64` | Required | - |
| `LastInstallmentAmount` | `float64` | Required | - |
| `Links` | [`*models.LinksModel`](../../doc/models/links-model.md) | Optional | - |
| `TermsAndConditionsBrief` | `*string` | Optional | - |
| `InstallmentFrequency` | `*string` | Optional | - |

## Example (as JSON)

```json
{
  "NumberOfInstallments": 148,
  "FirstInstallmentAmount": 45.62,
  "InstallmentAmount": 232.3,
  "LastInstallmentAmount": 187.9,
  "Links": null,
  "TermsAndConditionsBrief": "TermsAndConditionsBrief6",
  "InstallmentFrequency": "InstallmentFrequency2"
}
```

