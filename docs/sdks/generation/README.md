# Generation

## Overview

Image, video, audio, composition

### Available Operations

* [generateImage](#generateimage) - Generate an image
* [generateVideo](#generatevideo) - Generate a video
* [generateAudio](#generateaudio) - Generate audio (text-to-speech)
* [composeVideo](#composevideo) - Stitch multiple assets into a single video
* [~~createGeneration~~](#creategeneration) - (Deprecated) Submit a generation job :warning: **Deprecated**
* [listNodes](#listnodes) - List cards (legacy `nodes` alias)
* [createNode](#createnode) - Create a card (legacy `nodes` alias)
* [getNode](#getnode) - Get a single card with outgoing edges
* [deleteNode](#deletenode) - Soft-delete a card
* [searchCards](#searchcards) - Semantic search across the workspace card library
* [renderCard](#rendercard) - Render a card's structured back-side payload

## generateImage

Canonical image generation endpoint. Returns a queued job; clients
poll `/v1/generations/{id}` for status and asset URLs.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="generateImage" method="post" path="/v1/images/generate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.generateImage({
    model: "fal-ai/flux/schnell",
    prompt: "<value>",
    resolution: "1024x1024",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationGenerateImage } from "@aeriox-co/api/funcs/generation-generate-image.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationGenerateImage(aeriox, {
    model: "fal-ai/flux/schnell",
    prompt: "<value>",
    resolution: "1024x1024",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationGenerateImage failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.GenerateImageRequest](../../models/generate-image-request.md)                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GenerateImageResponse](../../models/operations/generate-image-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402, 422        | application/json          |
| errors.ErrorT             | 429                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## generateVideo

Canonical video generation endpoint. Returns a queued job; clients
poll `/v1/generations/{id}` for status and asset URLs.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="generateVideo" method="post" path="/v1/videos/generate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.generateVideo({
    model: "fal-ai/kling-3.0",
    prompt: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationGenerateVideo } from "@aeriox-co/api/funcs/generation-generate-video.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationGenerateVideo(aeriox, {
    model: "fal-ai/kling-3.0",
    prompt: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationGenerateVideo failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.GenerateVideoRequest](../../models/generate-video-request.md)                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GenerateVideoResponse](../../models/operations/generate-video-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402, 422        | application/json          |
| errors.ErrorT             | 429                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## generateAudio

Synthesize speech via ElevenLabs. Audio synthesis is fast enough
to be sync — returns a completed job inline with the audio URL.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="generateAudio" method="post" path="/v1/audio/generate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.generateAudio({
    text: "<value>",
    model: "eleven_v3_multilingual",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationGenerateAudio } from "@aeriox-co/api/funcs/generation-generate-audio.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationGenerateAudio(aeriox, {
    text: "<value>",
    model: "eleven_v3_multilingual",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationGenerateAudio failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.GenerateAudioRequest](../../models/generate-audio-request.md)                                                                                                          | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GenerateAudioResponse](../../models/operations/generate-audio-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402, 422        | application/json          |
| errors.ErrorT             | 429                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## composeVideo

Multi-shot video composition. Takes asset references and segment
timing, returns a queued composition job. Phase 3 ships the wallet
+ concurrency contract; dispatch implementation lands Phase 4
(returns 501 with refund until then).


### Example Usage

<!-- UsageSnippet language="typescript" operationID="composeVideo" method="post" path="/v1/compose" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.composeVideo({
    segments: [
      {
        assetId: "8c1107ec-d04b-42ed-899c-be92281827f9",
        startTime: 3346.69,
        duration: 5865.48,
      },
    ],
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationComposeVideo } from "@aeriox-co/api/funcs/generation-compose-video.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationComposeVideo(aeriox, {
    segments: [
      {
        assetId: "8c1107ec-d04b-42ed-899c-be92281827f9",
        startTime: 3346.69,
        duration: 5865.48,
      },
    ],
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationComposeVideo failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [models.ComposeRequest](../../models/compose-request.md)                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ComposeVideoResponse](../../models/operations/compose-video-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402             | application/json          |
| errors.ErrorT             | 429                       | application/json          |
| errors.ErrorT             | 501                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## ~~createGeneration~~

Legacy generation endpoint. Deprecated alias of `/v1/images/generate`
(and video equivalents). Returns a queued job; clients poll
`/v1/generations/{id}`.


> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="createGeneration" method="post" path="/v1/generate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.createGeneration({
    model: "Camry",
    prompt: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationCreateGeneration } from "@aeriox-co/api/funcs/generation-create-generation.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationCreateGeneration(aeriox, {
    model: "Camry",
    prompt: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationCreateGeneration failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateGenerationRequest](../../models/operations/create-generation-request.md)                                                                                     | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.CreateGenerationResponse](../../models/operations/create-generation-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 402             | application/json          |
| errors.ErrorT             | 429                       | application/json          |
| errors.ErrorT             | 503                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## listNodes

Backward-compat alias for `/v1/cards`. Response is dual-emitted with
both `nodes` and `cards` keys referencing the same array. Sunsets
on 2026-10-22.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="listNodes" method="get" path="/v1/nodes" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.listNodes({});

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationListNodes } from "@aeriox-co/api/funcs/generation-list-nodes.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationListNodes(aeriox, {});
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationListNodes failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.ListNodesRequest](../../models/operations/list-nodes-request.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.ListNodesResponse](../../models/operations/list-nodes-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## createNode

Backward-compat alias for `POST /v1/cards`. Request accepts either
`card_type` or legacy `node_type`. Response includes both `node` and
`card` fields referencing the same row.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="createNode" method="post" path="/v1/nodes" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.createNode({
    name: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationCreateNode } from "@aeriox-co/api/funcs/generation-create-node.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationCreateNode(aeriox, {
    name: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationCreateNode failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CreateNodeRequest](../../models/operations/create-node-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.CreateNodeResponse](../../models/operations/create-node-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## getNode

Get a single card with outgoing edges

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getNode" method="get" path="/v1/nodes/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.getNode({
    id: "1478d495-ce72-4a2b-addc-6f28215b7322",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationGetNode } from "@aeriox-co/api/funcs/generation-get-node.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationGetNode(aeriox, {
    id: "1478d495-ce72-4a2b-addc-6f28215b7322",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationGetNode failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetNodeRequest](../../models/operations/get-node-request.md)                                                                                                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetNodeResponse](../../models/operations/get-node-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## deleteNode

Soft-delete a card

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteNode" method="delete" path="/v1/nodes/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.deleteNode({
    id: "5f74c741-353b-46d5-a411-232a4c94ca8d",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationDeleteNode } from "@aeriox-co/api/funcs/generation-delete-node.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationDeleteNode(aeriox, {
    id: "5f74c741-353b-46d5-a411-232a4c94ca8d",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationDeleteNode failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteNodeRequest](../../models/operations/delete-node-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.DeleteNodeResponse](../../models/operations/delete-node-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## searchCards

Voyage-embedding-backed similarity search over cards. Workspace-scoped.
Returns 503 when `VOYAGE_API_KEY` is not configured on the deployment.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="searchCards" method="get" path="/v1/cards/search" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.searchCards({
    q: "<value>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationSearchCards } from "@aeriox-co/api/funcs/generation-search-cards.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationSearchCards(aeriox, {
    q: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationSearchCards failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.SearchCardsRequest](../../models/operations/search-cards-request.md)                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.SearchCardsResponse](../../models/operations/search-cards-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.ErrorT             | 503                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## renderCard

Returns the uniform `RenderedInputs` payload produced by the registered
renderer for the card's type — the same view the canvas executor uses
when wiring this card to a downstream node.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="renderCard" method="get" path="/v1/cards/{id}/render" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.generation.renderCard({
    id: "2c8356eb-1d57-41ea-8889-4f961f35d193",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { generationRenderCard } from "@aeriox-co/api/funcs/generation-render-card.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await generationRenderCard(aeriox, {
    id: "2c8356eb-1d57-41ea-8889-4f961f35d193",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("generationRenderCard failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.RenderCardRequest](../../models/operations/render-card-request.md)                                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.RenderCardResponse](../../models/operations/render-card-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401, 404             | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |