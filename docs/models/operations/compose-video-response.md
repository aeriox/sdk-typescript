# ComposeVideoResponse

## Example Usage

```typescript
import { ComposeVideoResponse } from "@aeriox-co/api/models/operations";

let value: ComposeVideoResponse = {
  headers: {
    "key": [
      "<value 1>",
      "<value 2>",
      "<value 3>",
    ],
  },
  result: {
    id: "239c54b0-75fd-4768-8c96-eb90b91cbe07",
    type: "compose",
    status: "queued",
    operationId: "compose.stitch_per_minute",
    estimatedCostUsdMicros: 879434,
    estimatedCostUsd: 2284.11,
    createdAt: new Date("2024-07-03T02:39:01.919Z"),
  },
};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `headers`                                               | Record<string, *string*[]>                              | :heavy_check_mark:                                      | N/A                                                     |
| `result`                                                | [models.ComposeJobAck](../../models/compose-job-ack.md) | :heavy_check_mark:                                      | N/A                                                     |