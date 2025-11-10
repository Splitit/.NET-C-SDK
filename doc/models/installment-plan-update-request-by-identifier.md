
# Installment Plan Update Request by Identifier

## Structure

`InstallmentPlanUpdateRequestByIdentifier`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefOrderNumber` | `string` | Optional | - |
| `TrackingNumber` | `string` | Optional | - |
| `Capture` | `bool?` | Optional | - |
| `ShippingStatus` | [`ShippingStatusEnum?`](../../doc/models/shipping-status-enum.md) | Optional | - |
| `NewAmount` | `double?` | Optional | - |
| `Identifier` | [`IdentifierContract`](../../doc/models/identifier-contract.md) | Optional | - |

## Example (as JSON)

```json
{
  "RefOrderNumber": "RefOrderNumber2",
  "TrackingNumber": "TrackingNumber6",
  "Capture": false,
  "ShippingStatus": "Pending",
  "NewAmount": 233.74
}
```

