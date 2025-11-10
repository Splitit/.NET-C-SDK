
# Plan Error Response Exception

## Structure

`PlanErrorResponseException`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TraceId` | `string` | Optional | - |
| `Error` | [`ErrorExtended`](../../doc/models/error-extended.md) | Optional | - |
| `InstallmentPlanNumber` | `string` | Optional | - |
| `PaymentInfo` | [`PaymentInfo`](../../doc/models/payment-info.md) | Optional | - |

## Example (as JSON)

```json
{
  "TraceId": "TraceId8",
  "Error": null,
  "InstallmentPlanNumber": "InstallmentPlanNumber6",
  "PaymentInfo": null
}
```

