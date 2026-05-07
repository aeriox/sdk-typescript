# OauthRevokeRequest

## Example Usage

```typescript
import { OauthRevokeRequest } from "@aeriox-co/api/models/operations";

let value: OauthRevokeRequest = {
  token: "<value>",
};
```

## Fields

| Field                                                                  | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `token`                                                                | *string*                                                               | :heavy_check_mark:                                                     | N/A                                                                    |
| `tokenTypeHint`                                                        | [operations.TokenTypeHint](../../models/operations/token-type-hint.md) | :heavy_minus_sign:                                                     | N/A                                                                    |
| `clientId`                                                             | *string*                                                               | :heavy_minus_sign:                                                     | N/A                                                                    |