# GenerateVideoRequest

## Example Usage

```typescript
import { GenerateVideoRequest } from "@aeriox-co/api/models";

let value: GenerateVideoRequest = {
  model: "fal-ai/kling-3.0",
  prompt: "<value>",
};
```

## Fields

| Field              | Type               | Required           | Description        | Example            |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| `model`            | *string*           | :heavy_check_mark: | N/A                | fal-ai/kling-3.0   |
| `prompt`           | *string*           | :heavy_check_mark: | N/A                |                    |
| `imageUrl`         | *string*           | :heavy_minus_sign: | N/A                |                    |
| `durationS`        | *number*           | :heavy_minus_sign: | N/A                |                    |
| `withAudio`        | *boolean*          | :heavy_minus_sign: | N/A                |                    |
| `motionId`         | *string*           | :heavy_minus_sign: | N/A                |                    |
| `characterId`      | *string*           | :heavy_minus_sign: | N/A                |                    |
| `prismId`          | *string*           | :heavy_minus_sign: | N/A                |                    |