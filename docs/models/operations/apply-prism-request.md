# ApplyPrismRequest

## Example Usage

```typescript
import { ApplyPrismRequest } from "@aeriox-co/api/models/operations";

let value: ApplyPrismRequest = {
  id: "<id>",
  body: {
    imageParams: {
      model: "fal-ai/flux/schnell",
      prompt: "<value>",
      resolution: "1024x1024",
    },
    videoParams: {
      model: "fal-ai/kling-3.0",
      prompt: "<value>",
    },
  },
};
```

## Fields

| Field                                                                                   | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `id`                                                                                    | *string*                                                                                | :heavy_check_mark:                                                                      | N/A                                                                                     |
| `body`                                                                                  | [operations.ApplyPrismRequestBody](../../models/operations/apply-prism-request-body.md) | :heavy_check_mark:                                                                      | N/A                                                                                     |