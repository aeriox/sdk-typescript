# Discovery

## Overview

Models, pricing

### Available Operations

* [getOpenApiSpec](#getopenapispec) - Fetch the AERIOX OpenAPI 3.1 spec as JSON
* [getPricing](#getpricing) - Get USD price list for all operations
* [estimateGeneration](#estimategeneration) - Estimate cost and feasibility for a generation
* [listModels](#listmodels) - Capability + price catalog for every supported model

## getOpenApiSpec

Returns the canonical OpenAPI 3.1 document for the AERIOX public API
as JSON. The spec is also available as YAML at
`docs/api/aeriox.openapi.yaml` in the source repo. Public — no
authentication required. Cached at the edge for one hour.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="getOpenApiSpec" method="get" path="/openapi.json" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  const result = await aeriox.discovery.getOpenApiSpec();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { discoveryGetOpenApiSpec } from "@aeriox-co/api/funcs/discovery-get-open-api-spec.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await discoveryGetOpenApiSpec(aeriox);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("discoveryGetOpenApiSpec failed:", res.error);
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

## getPricing

Public endpoint — no authentication required.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getPricing" method="get" path="/v1/pricing" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  const result = await aeriox.discovery.getPricing();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { discoveryGetPricing } from "@aeriox-co/api/funcs/discovery-get-pricing.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore();

async function run() {
  const res = await discoveryGetPricing(aeriox);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("discoveryGetPricing failed:", res.error);
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

**Promise\<[operations.GetPricingResponse](../../models/operations/get-pricing-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 503                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## estimateGeneration

Returns credit + USD cost, p95 wall-clock estimate, and a feasibility
check (`would_succeed`) with structured `reasons_blocked`. Does not
commit funds or call upstream providers.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="estimateGeneration" method="post" path="/v1/estimate" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.discovery.estimateGeneration({
    model: "CX-9",
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
import { discoveryEstimateGeneration } from "@aeriox-co/api/funcs/discovery-estimate-generation.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await discoveryEstimateGeneration(aeriox, {
    model: "CX-9",
    prompt: "<value>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("discoveryEstimateGeneration failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.EstimateGenerationRequest](../../models/operations/estimate-generation-request.md)                                                                                 | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.EstimateGenerationResponse](../../models/operations/estimate-generation-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 400, 401                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## listModels

Returns every active model in the cost spine with capabilities (max resolution, duration, audio support) and per-unit USD pricing.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="listModels" method="get" path="/v1/models" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.discovery.listModels();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { discoveryListModels } from "@aeriox-co/api/funcs/discovery-list-models.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await discoveryListModels(aeriox);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("discoveryListModels failed:", res.error);
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

**Promise\<[operations.ListModelsResponse](../../models/operations/list-models-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401                       | application/json          |
| errors.ErrorT             | 503                       | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |