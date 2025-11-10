
# Payment Method Model

## Structure

`PaymentMethodModel`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | [`PaymentMethodTypeEnum`](../../doc/models/payment-method-type-enum.md) | Required | - |
| `Card` | [`CardData`](../../doc/models/card-data.md) | Optional | - |
| `Token` | `string` | Optional | - |
| `BluesnapVaultedShopperToken` | [`BluesnapVaultedShopperToken`](../../doc/models/bluesnap-vaulted-shopper-token.md) | Optional | - |
| `MockerShopperToken` | [`MockerShopperToken`](../../doc/models/mocker-shopper-token.md) | Optional | - |
| `SpreedlyToken` | [`SpreedlyToken`](../../doc/models/spreedly-token.md) | Optional | - |
| `CardPAR` | `string` | Optional | - |

## Example (as JSON)

```json
{
  "Type": "Card",
  "Card": null,
  "Token": "Token6",
  "BluesnapVaultedShopperToken": null,
  "MockerShopperToken": null,
  "SpreedlyToken": null
}
```

