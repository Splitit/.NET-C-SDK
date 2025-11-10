
# Initiate Plan Response

## Structure

`InitiatePlanResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumber` | `string` | Optional | - |
| `RefOrderNumber` | `string` | Optional | - |
| `PurchaseMethod` | [`PurchaseMethodEnum?`](../../doc/models/purchase-method-enum.md) | Optional | - |
| `Status` | [`PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `Currency` | `string` | Optional | - |
| `Amount` | `double?` | Optional | - |
| `ExtendedParams` | `Dictionary<string, string>` | Optional | - |
| `Shopper` | [`ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `BillingAddress` | [`AddressData`](../../doc/models/address-data.md) | Optional | - |
| `CheckoutUrl` | `string` | Optional | - |
| `PrincipalAmount` | `double?` | Optional | - |

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

