
# Refund Model

## Structure

`RefundModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `RefundId` | `string` | Optional | - |
| `SubmitDate` | `DateTime` | Required | - |
| `TotalAmount` | `double` | Required | - |
| `Status` | [`RefundStatusEnum`](../../doc/models/refund-status-enum.md) | Required | - |
| `NonCreditRefundAmount` | `double` | Required | - |
| `CreditRefundAmount` | `double` | Required | - |
| `ReferenceId` | `string` | Optional | - |

## Example (as JSON)

```json
{
  "RefundId": "RefundId0",
  "SubmitDate": "2016-03-13T12:52:32.123Z",
  "TotalAmount": 115.92,
  "Status": "Pending",
  "NonCreditRefundAmount": 172.08,
  "CreditRefundAmount": 159.38,
  "ReferenceId": "ReferenceId8"
}
```

