# APIKeys

## Overview

Key management

### Available Operations

* [getMe](#getme) - Get current API key + workspace
* [rotateApiKey](#rotateapikey) - Rotate an API key
* [oauthAuthorize](#oauthauthorize) - Begin OAuth 2.0 PKCE authorization
* [oauthToken](#oauthtoken) - Exchange authorization code or refresh token for an access token
* [oauthRevoke](#oauthrevoke) - Revoke an OAuth access or refresh token
* [oauthJwks](#oauthjwks) - JSON Web Key Set for OAuth access token verification

## getMe

Returns the workspace and API key metadata for the calling key.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getMe" method="get" path="/v1/me" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.apiKeys.getMe();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysGetMe } from "@aeriox-co/api/funcs/api-keys-get-me.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await apiKeysGetMe(aeriox);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("apiKeysGetMe failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetMeResponse](../../models/operations/get-me-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## rotateApiKey

Issues a new key value for the given key id. The old key is scheduled
for expiry; the response includes the new plaintext (returned exactly
once) and the old key's expiry timestamp.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="rotateApiKey" method="post" path="/v1/api-keys/{id}/rotate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.apiKeys.rotateApiKey({
    id: "3d03cca4-b23a-43b1-8b6e-2d9a0e5df640",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysRotateAPIKey } from "@aeriox-co/api/funcs/api-keys-rotate-api-key.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await apiKeysRotateAPIKey(aeriox, {
    id: "3d03cca4-b23a-43b1-8b6e-2d9a0e5df640",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("apiKeysRotateAPIKey failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RotateApiKeyRequest](../../models/operations/rotate-api-key-request.md)                                                                                            | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.RotateApiKeyResponse](../../models/operations/rotate-api-key-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404, 409             | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## oauthAuthorize

Authorization endpoint for the PKCE-only flow. Validates the request
and redirects the user-agent to the consent screen.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="oauthAuthorize" method="get" path="/v1/oauth/authorize" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  await aeriox.apiKeys.oauthAuthorize({
    responseType: "code",
    clientId: "<id>",
    redirectUri: "https://coordinated-dime.biz/",
    codeChallenge: "<value>",
    codeChallengeMethod: "S256",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysOauthAuthorize } from "@aeriox-co/api/funcs/api-keys-oauth-authorize.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await apiKeysOauthAuthorize(aeriox, {
    responseType: "code",
    clientId: "<id>",
    redirectUri: "https://coordinated-dime.biz/",
    codeChallenge: "<value>",
    codeChallengeMethod: "S256",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("apiKeysOauthAuthorize failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.OauthAuthorizeRequest](../../models/operations/oauth-authorize-request.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## oauthToken

Token endpoint. Accepts `authorization_code` (after PKCE) or
`refresh_token` grants. Returns a JWT access token bound to the
granting workspace and the requested scopes.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="oauthToken" method="post" path="/v1/oauth/token" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  const result = await aeriox.apiKeys.oauthToken({
    grantType: "refresh_token",
    clientId: "<id>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysOauthToken } from "@aeriox-co/api/funcs/api-keys-oauth-token.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await apiKeysOauthToken(aeriox, {
    grantType: "refresh_token",
    clientId: "<id>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("apiKeysOauthToken failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.OauthTokenRequest](../../models/operations/oauth-token-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.OauthTokenResponse](../../models/operations/oauth-token-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## oauthRevoke

Idempotent revocation. Returns 200 whether or not the token was
previously valid (per RFC 7009).


### Example Usage

<!-- UsageSnippet language="typescript" operationID="oauthRevoke" method="post" path="/v1/oauth/revoke" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  await aeriox.apiKeys.oauthRevoke({
    token: "<value>",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysOauthRevoke } from "@aeriox-co/api/funcs/api-keys-oauth-revoke.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await apiKeysOauthRevoke(aeriox, {
    token: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("apiKeysOauthRevoke failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.OauthRevokeRequest](../../models/operations/oauth-revoke-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## oauthJwks

Public JWKS used by clients/resource servers to verify access-token
signatures. Cached aggressively; rotated infrequently.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="oauthJwks" method="get" path="/v1/oauth/jwks" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  const result = await aeriox.apiKeys.oauthJwks();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { apiKeysOauthJwks } from "@aeriox-co/api/funcs/api-keys-oauth-jwks.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await apiKeysOauthJwks(aeriox);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("apiKeysOauthJwks failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[{ [k: string]: any }](../../models/.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |