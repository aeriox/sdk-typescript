# GenerateImageRequest

## Example Usage

```typescript
import { GenerateImageRequest } from "@aeriox-co/api/models";

let value: GenerateImageRequest = {
  model: "fal-ai/flux/schnell",
  prompt: "<value>",
  resolution: "1024x1024",
};
```

## Fields

| Field                                           | Type                                            | Required                                        | Description                                     | Example                                         |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `model`                                         | *string*                                        | :heavy_check_mark:                              | N/A                                             | fal-ai/flux/schnell                             |
| `prompt`                                        | *string*                                        | :heavy_check_mark:                              | N/A                                             |                                                 |
| `negativePrompt`                                | *string*                                        | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `aspectRatio`                                   | [models.AspectRatio](../models/aspect-ratio.md) | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `resolution`                                    | *string*                                        | :heavy_minus_sign:                              | N/A                                             | 1024x1024                                       |
| `seedImageUrl`                                  | *string*                                        | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `loras`                                         | [models.Lora](../models/lora.md)[]              | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `seed`                                          | *number*                                        | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `characterId`                                   | *string*                                        | :heavy_minus_sign:                              | N/A                                             |                                                 |
| `prismId`                                       | *string*                                        | :heavy_minus_sign:                              | N/A                                             |                                                 |