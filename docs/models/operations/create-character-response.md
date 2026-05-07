# CreateCharacterResponse

Training queued

## Example Usage

```typescript
import { CreateCharacterResponse } from "@aeriox-co/api/models/operations";

let value: CreateCharacterResponse = {
  jobId: "1d805a66-7295-44be-adc9-6979e866b252",
  type: "video",
  status: "completed",
  error: {
    error: {
      code: "insufficient_funds",
    },
  },
  createdAt: new Date("2026-04-15T16:45:27.901Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `jobId`                                                                                       | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `type`                                                                                        | [operations.Type](../../models/operations/type.md)                                            | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `status`                                                                                      | [operations.CreateCharacterStatus](../../models/operations/create-character-status.md)        | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `progressPct`                                                                                 | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `estimatedCostUsd`                                                                            | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `chargedCostUsd`                                                                              | *number*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `outputUrls`                                                                                  | *string*[]                                                                                    | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `error`                                                                                       | [operations.ErrorT](../../models/operations/error-t.md)                                       | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `createdAt`                                                                                   | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `completedAt`                                                                                 | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_minus_sign:                                                                            | N/A                                                                                           |
| `prismId`                                                                                     | *string*                                                                                      | :heavy_minus_sign:                                                                            | Present only when `type=prism_apply`. Identifies the prism that was applied.                  |
| `characterId`                                                                                 | *string*                                                                                      | :heavy_minus_sign:                                                                            | N/A                                                                                           |