# Job

## Example Usage

```typescript
import { Job } from "@aeriox-co/api/models";

let value: Job = {
  jobId: "53a43d25-8a99-4abd-974b-dd35d9ef88d7",
  type: "image",
  status: "cancelled",
  error: {
    error: {
      code: "insufficient_funds",
    },
  },
  createdAt: new Date("2026-09-27T03:35:04.769Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `jobId`                                                                                       | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `type`                                                                                        | [models.JobType](../models/job-type.md)                                                       | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `status`                                                                                      | [models.JobStatus](../models/job-status.md)                                                   | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `progressPct`                                                                                 | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `estimatedCostUsd`                                                                            | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `chargedCostUsd`                                                                              | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `outputUrls`                                                                                  | *string*[]                                                                                    | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `error`                                                                                       | [models.JobError](../models/job-error.md)                                                     | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `createdAt`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `completedAt`                                                                                 | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `prismId`                                                                                     | *string*                                                                                      | :heavy_minus_sign:                                                                            | Present only when `type=prism_apply`. Identifies the prism that was applied.                  |