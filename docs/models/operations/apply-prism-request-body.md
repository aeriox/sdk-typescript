# ApplyPrismRequestBody

## Example Usage

```typescript
import { ApplyPrismRequestBody } from "@aeriox-co/api/models/operations";

let value: ApplyPrismRequestBody = {
  imageParams: {
    model: "fal-ai/flux/schnell",
    prompt: "<value>",
    resolution: "1024x1024",
  },
  videoParams: {
    model: "fal-ai/kling-3.0",
    prompt: "<value>",
  },
};
```

## Fields

| Field                                                                 | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `assetId`                                                             | *string*                                                              | :heavy_minus_sign:                                                    | N/A                                                                   |
| `imageParams`                                                         | [models.GenerateImageRequest](../../models/generate-image-request.md) | :heavy_minus_sign:                                                    | N/A                                                                   |
| `videoParams`                                                         | [models.GenerateVideoRequest](../../models/generate-video-request.md) | :heavy_minus_sign:                                                    | N/A                                                                   |