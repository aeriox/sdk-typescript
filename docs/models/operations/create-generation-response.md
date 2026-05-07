# CreateGenerationResponse

## Example Usage

```typescript
import { CreateGenerationResponse } from "@aeriox-co/api/models/operations";

let value: CreateGenerationResponse = {
  headers: {},
  result: {
    generationId: "b77d0ad6-860f-4ff5-b559-8f2d972c662d",
    status: "queued",
    model: "Wrangler",
  },
};
```

## Fields

| Field                                                                                                 | Type                                                                                                  | Required                                                                                              | Description                                                                                           |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `headers`                                                                                             | Record<string, *string*[]>                                                                            | :heavy_check_mark:                                                                                    | N/A                                                                                                   |
| `result`                                                                                              | [operations.CreateGenerationResponseBody](../../models/operations/create-generation-response-body.md) | :heavy_check_mark:                                                                                    | N/A                                                                                                   |