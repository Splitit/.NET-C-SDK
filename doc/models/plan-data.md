
# Plan Data

## Structure

`PlanData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TerminalId` | `string` | Optional | - |
| `TotalAmount` | `string` | Required | - |
| `FirstInstallmentAmount` | `double?` | Optional | - |
| `Currency` | `string` | Optional | - |
| `NumberOfInstallments` | `int` | Required | - |
| `PurchaseMethod` | [`PurchaseMethodEnum`](../../doc/models/purchase-method-enum.md) | Required | - |
| `RefOrderNumber` | `string` | Optional | - |
| `AllowedInstallmentOptions` | `List<int>` | Optional | - |
| `Tags` | `Dictionary<string, string>` | Optional | - |
| `ProcessingData` | [`ProcessingData`](../../doc/models/processing-data.md) | Optional | - |
| `FirstInstallmentDate` | `DateTime?` | Optional | - |

## Example (as JSON)

```json
{
  "TerminalId": "TerminalId8",
  "TotalAmount": "TotalAmount4",
  "FirstInstallmentAmount": 11.28,
  "Currency": "Currency6",
  "NumberOfInstallments": 2,
  "PurchaseMethod": "PhoneOrder",
  "RefOrderNumber": "RefOrderNumber2",
  "AllowedInstallmentOptions": [
    46,
    47
  ]
}
```

