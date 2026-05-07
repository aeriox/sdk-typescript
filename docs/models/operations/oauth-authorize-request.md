# OauthAuthorizeRequest

## Example Usage

```typescript
import { OauthAuthorizeRequest } from "@aeriox-co/api/models/operations";

let value: OauthAuthorizeRequest = {
  responseType: "code",
  clientId: "<id>",
  redirectUri: "https://blank-bowling.com",
  codeChallenge: "<value>",
  codeChallengeMethod: "S256",
};
```

## Fields

| Field                                                                              | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `responseType`                                                                     | [operations.ResponseType](../../models/operations/response-type.md)                | :heavy_check_mark:                                                                 | N/A                                                                                |
| `clientId`                                                                         | *string*                                                                           | :heavy_check_mark:                                                                 | N/A                                                                                |
| `redirectUri`                                                                      | *string*                                                                           | :heavy_check_mark:                                                                 | N/A                                                                                |
| `codeChallenge`                                                                    | *string*                                                                           | :heavy_check_mark:                                                                 | N/A                                                                                |
| `codeChallengeMethod`                                                              | [operations.CodeChallengeMethod](../../models/operations/code-challenge-method.md) | :heavy_check_mark:                                                                 | N/A                                                                                |
| `scope`                                                                            | *string*                                                                           | :heavy_minus_sign:                                                                 | N/A                                                                                |
| `state`                                                                            | *string*                                                                           | :heavy_minus_sign:                                                                 | N/A                                                                                |