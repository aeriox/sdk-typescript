# Characters

## Overview

Custom character training and reuse

### Available Operations

* [createCharacter](#createcharacter) - Create + train a custom character from reference images
* [listCharacters](#listcharacters) - List workspace characters (cursor-paginated)
* [getCharacter](#getcharacter) - Fetch a single character
* [deleteCharacter](#deletecharacter) - Soft-delete a character

## createCharacter

Creates a character card and queues a training job. Returns a Job
descriptor (status `queued`) plus the new `character_id`. Poll
`/v1/jobs/{id}` for completion. Wallet is charged at the
`char.train_soul` rate.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createCharacter" method="post" path="/v1/characters" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.characters.createCharacter({
    name: "<value>",
    imageUrls: [],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { charactersCreateCharacter } from "@aeriox-co/api/funcs/characters-create-character.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await charactersCreateCharacter(aeriox, {
    name: "<value>",
    imageUrls: [],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("charactersCreateCharacter failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateCharacterRequest](../../models/operations/create-character-request.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.CreateCharacterResponse](../../models/operations/create-character-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402             | application/json          |
| errors.ErrorT             | 503                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## listCharacters

Cursor-paginated list of characters in the calling workspace. Soft-deleted rows are excluded.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="listCharacters" method="get" path="/v1/characters" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.characters.listCharacters({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { charactersListCharacters } from "@aeriox-co/api/funcs/characters-list-characters.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await charactersListCharacters(aeriox, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("charactersListCharacters failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListCharactersRequest](../../models/operations/list-characters-request.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ListCharactersResponse](../../models/operations/list-characters-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## getCharacter

Returns a single character. 404 (not 403) for cross-workspace ids so existence is never leaked.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getCharacter" method="get" path="/v1/characters/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.characters.getCharacter({
    id: "171190e6-4026-4a76-98a1-2a72ac075729",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { charactersGetCharacter } from "@aeriox-co/api/funcs/characters-get-character.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await charactersGetCharacter(aeriox, {
    id: "171190e6-4026-4a76-98a1-2a72ac075729",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("charactersGetCharacter failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetCharacterRequest](../../models/operations/get-character-request.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Character](../../models/character.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## deleteCharacter

Requires `admin` scope. Returns 204 with no body.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteCharacter" method="delete" path="/v1/characters/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  await aeriox.characters.deleteCharacter({
    id: "e6a45710-3c5d-4c41-8d0b-a6a9827770a6",
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { charactersDeleteCharacter } from "@aeriox-co/api/funcs/characters-delete-character.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await charactersDeleteCharacter(aeriox, {
    id: "e6a45710-3c5d-4c41-8d0b-a6a9827770a6",
  });
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("charactersDeleteCharacter failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteCharacterRequest](../../models/operations/delete-character-request.md)                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |