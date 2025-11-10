
# Installment Plan Update Response

## Structure

`InstallmentPlanUpdateResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefOrderNumber` | `string` | Optional | - |
| `InstallmentPlanNumber` | `string` | Optional | - |
| `Status` | [`PlanStatusEnum`](../../doc/models/plan-status-enum.md) | Required | - |
| `ShippingStatus` | [`ShippingStatusEnum`](../../doc/models/shipping-status-enum.md) | Required | - |
| `NewAmount` | `double?` | Optional | - |

## Example (as JSON)

```json
{
  "RefOrderNumber": "RefOrderNumber2",
  "InstallmentPlanNumber": "InstallmentPlanNumber2",
  "Status": "PendingCapture",
  "ShippingStatus": "Delivered",
  "NewAmount": 233.54
}
```

