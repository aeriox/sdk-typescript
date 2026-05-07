# CreateGenerationRequest

## Example Usage

```typescript
import { CreateGenerationRequest } from "@aeriox-co/api/models/operations";

let value: CreateGenerationRequest = {
  model: "911",
  prompt: "<value>",
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `model`                                              | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `prompt`                                             | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `negativePrompt`                                     | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `aspectRatio`                                        | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `resolution`                                         | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `duration`                                           | *number*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `withAudio`                                          | *boolean*                                            | :heavy_minus_sign:                                   | N/A                                                  |
| `seedImageUrl`                                       | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `loras`                                              | [operations.Lora](../../models/operations/lora.md)[] | :heavy_minus_sign:                                   | N/A                                                  |