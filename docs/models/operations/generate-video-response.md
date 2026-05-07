# GenerateVideoResponse

## Example Usage

```typescript
import { GenerateVideoResponse } from "@aeriox-co/api/models/operations";

let value: GenerateVideoResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
    ],
    "key1": [],
  },
  result: {
    jobId: "c4e68329-ad78-4034-95e9-19920a47cf2d",
    type: "compose",
    status: "cancelled",
    error: {
      error: {
        code: "insufficient_funds",
      },
    },
    createdAt: new Date("2024-04-15T02:02:37.416Z"),
  },
};
```

## Fields

| Field                             | Type                              | Required                          | Description                       |
| --------------------------------- | --------------------------------- | --------------------------------- | --------------------------------- |
| `headers`                         | Record<string, *string*[]>        | :heavy_check_mark:                | N/A                               |
| `result`                          | [models.Job](../../models/job.md) | :heavy_check_mark:                | N/A                               |