
# Authorization Model

## Structure

`AuthorizationModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Status` | [`GwAuthorizationStatusEnum`](../../doc/models/gw-authorization-status-enum.md) | Required | - |
| `Date` | `DateTime?` | Optional | - |
| `SplititErrorResultCode` | `string` | Optional | - |
| `GatewayTransactionID` | `string` | Optional | - |
| `GatewayResultCode` | `string` | Optional | - |
| `GatewayResultMessage` | `string` | Optional | - |
| `ThreeDSRedirect` | [`ThreeDsRedirectDataV3`](../../doc/models/three-ds-redirect-data-v3.md) | Optional | - |
| `CAVV` | `string` | Optional | - |
| `ECI` | `string` | Optional | - |
| `GatewaySourceResponse` | `string` | Optional | - |

## Example (as JSON)

```json
{
  "Status": "Canceled",
  "Date": "2016-03-13T12:52:32.123Z",
  "SplititErrorResultCode": "SplititErrorResultCode6",
  "GatewayTransactionID": "GatewayTransactionID0",
  "GatewayResultCode": "GatewayResultCode2",
  "GatewayResultMessage": "GatewayResultMessage8"
}
```

