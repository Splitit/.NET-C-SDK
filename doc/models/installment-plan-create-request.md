
# Installment Plan Create Request

## Structure

`InstallmentPlanCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AutoCapture` | `bool` | Required | - |
| `Attempt3dSecure` | `bool?` | Optional | - |
| `TermsAndConditionsAccepted` | `bool` | Required | - |
| `Shopper` | [`ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `PlanData` | [`PlanDataModel`](../../doc/models/plan-data-model.md) | Optional | - |
| `BillingAddress` | [`AddressDataModel`](../../doc/models/address-data-model.md) | Optional | - |
| `PaymentMethod` | [`PaymentMethodModel`](../../doc/models/payment-method-model.md) | Optional | - |
| `RedirectUrls` | [`RedirectionEndpointsModel`](../../doc/models/redirection-endpoints-model.md) | Optional | - |
| `ProcessingData` | [`ProcessingData`](../../doc/models/processing-data.md) | Optional | - |
| `EventsEndpoints` | [`EventsEndpointsModel`](../../doc/models/events-endpoints-model.md) | Optional | - |

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

