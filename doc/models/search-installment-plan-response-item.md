
# Search Installment Plan Response Item

## Structure

`SearchInstallmentPlanResponseItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `InstallmentPlanNumber` | `string` | Optional | - |
| `DateCreated` | `DateTime` | Required | - |
| `RefOrderNumber` | `string` | Optional | - |
| `PurchaseMethod` | [`PurchaseMethodEnum?`](../../doc/models/purchase-method-enum.md) | Optional | - |
| `Status` | [`PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `Currency` | `string` | Optional | - |
| `OriginalAmount` | `double?` | Optional | - |
| `Amount` | `double?` | Optional | - |
| `Authorization` | [`AuthorizationModel`](../../doc/models/authorization-model.md) | Optional | - |
| `Shopper` | [`ShopperData`](../../doc/models/shopper-data.md) | Optional | - |
| `BillingAddress` | [`AddressData`](../../doc/models/address-data.md) | Optional | - |
| `PaymentMethod` | [`PaymentMethodModel`](../../doc/models/payment-method-model.md) | Optional | - |
| `ExtendedParams` | `Dictionary<string, string>` | Optional | - |
| `Installments` | [`List<Installment>`](../../doc/models/installment.md) | Optional | - |
| `Refunds` | [`List<RefundModel>`](../../doc/models/refund-model.md) | Optional | - |
| `Links` | [`LinksData`](../../doc/models/links-data.md) | Optional | - |

## Example (as JSON)

```json
{
  "InstallmentPlanNumber": "InstallmentPlanNumber2",
  "DateCreated": "2016-03-13T12:52:32.123Z",
  "RefOrderNumber": "RefOrderNumber2",
  "PurchaseMethod": "PhoneOrder",
  "Status": "PendingCapture",
  "Currency": "Currency6",
  "OriginalAmount": 4.38
}
```

