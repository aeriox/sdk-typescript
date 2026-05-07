# OauthTokenResponse

Token response

## Example Usage

```typescript
import { OauthTokenResponse } from "@aeriox-co/api/models/operations";

let value: OauthTokenResponse = {
  accessToken: "<value>",
  tokenType: "Bearer",
  expiresIn: 939345,
};
```

## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `accessToken`                                                 | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `tokenType`                                                   | [operations.TokenType](../../models/operations/token-type.md) | :heavy_check_mark:                                            | N/A                                                           |
| `expiresIn`                                                   | *number*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `refreshToken`                                                | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |
| `scope`                                                       | *string*                                                      | :heavy_minus_sign:                                            | N/A                                                           |