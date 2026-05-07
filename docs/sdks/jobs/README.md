# Jobs

## Overview

Async job lifecycle

### Available Operations

* [~~getGeneration~~](#getgeneration) - (Deprecated) Poll generation status :warning: **Deprecated**
* [getJob](#getjob) - Poll unified job status
* [cancelJob](#canceljob) - Cancel a queued or running job

## ~~getGeneration~~

Deprecated alias of `/v1/jobs/{id}`. Workspace-scoped.

> :warning: **DEPRECATED**: This will be removed in a future release, please migrate away from it as soon as possible.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getGeneration" method="get" path="/v1/generations/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.jobs.getGeneration({
    id: "70a2db79-7239-411f-8b44-b6c2fd9c55dc",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { jobsGetGeneration } from "@aeriox-co/api/funcs/jobs-get-generation.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await jobsGetGeneration(aeriox, {
    id: "70a2db79-7239-411f-8b44-b6c2fd9c55dc",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("jobsGetGeneration failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetGenerationRequest](../../models/operations/get-generation-request.md)                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetGenerationResponse](../../models/operations/get-generation-response.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## getJob

Workspace-scoped read of a job's current state. Replaces `/v1/generations/{id}`.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getJob" method="get" path="/v1/jobs/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.jobs.getJob({
    id: "3f250f6c-b987-45c1-b9f9-6bac1e2299c4",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { jobsGetJob } from "@aeriox-co/api/funcs/jobs-get-job.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await jobsGetJob(aeriox, {
    id: "3f250f6c-b987-45c1-b9f9-6bac1e2299c4",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("jobsGetJob failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetJobRequest](../../models/operations/get-job-request.md)                                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Job](../../models/job.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404                  | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |

## cancelJob

Refunds any wallet reservation held by the job. Returns the job
in its new (cancelled) state. 409 if the job has already reached
a terminal state.


### Example Usage

<!-- UsageSnippet language="typescript" operationID="cancelJob" method="delete" path="/v1/jobs/{id}" -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const result = await aeriox.jobs.cancelJob({
    id: "98449c4f-d645-4124-86e8-d3fc6fb8b978",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { AerioxCore } from "@aeriox-co/api/core.js";
import { jobsCancelJob } from "@aeriox-co/api/funcs/jobs-cancel-job.js";

// Use `AerioxCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const aeriox = new AerioxCore({
  security: {
    apiKey: "<YOUR_BEARER_TOKEN_HERE>",
  },
});

async function run() {
  const res = await jobsCancelJob(aeriox, {
    id: "98449c4f-d645-4124-86e8-d3fc6fb8b978",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("jobsCancelJob failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.CancelJobRequest](../../models/operations/cancel-job-request.md)                                                                                                   | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[models.Job](../../models/job.md)\>**

### Errors

| Error Type                | Status Code               | Content Type              |
| ------------------------- | ------------------------- | ------------------------- |
| errors.ErrorT             | 401, 404, 409             | application/json          |
| errors.AerioxDefaultError | 4XX, 5XX                  | \*/\*                     |