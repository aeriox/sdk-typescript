# OauthTokenRequest

## Example Usage

```typescript
import { OauthTokenRequest } from "@aeriox-co/api/models/operations";

let value: OauthTokenRequest = {
  grantType: "authorization_code",
  clientId: "<id>",
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `grantType`                                                   | [operations.GrantType](../../models/operations/grant-type.md) | :heavy_check_mark:                                            | N/A                                                           |
| `code`                                                        | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |
| `redirectUri`                                                 | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |
| `codeVerifier`                                                | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |
| `refreshToken`                                                | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |
| `clientId`                                                    | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |