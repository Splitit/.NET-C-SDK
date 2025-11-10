
# Verify Authorization Response

## Structure

`VerifyAuthorizationResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `IsAuthorized` | `bool` | Required | - |
| `AuthorizationAmount` | `double?` | Optional | - |
| `Authorization` | [`AuthorizationModel`](../../doc/models/authorization-model.md) | Optional | - |

## Example (as JSON)

```json
{
  "IsAuthorized": false,
  "AuthorizationAmount": 186.44,
  "Authorization": null
}
```

