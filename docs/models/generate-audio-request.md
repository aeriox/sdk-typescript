# GenerateAudioRequest

## Example Usage

```typescript
import { GenerateAudioRequest } from "@aeriox-co/api/models";

let value: GenerateAudioRequest = {
  text: "<value>",
  model: "eleven_v3_multilingual",
};
```

## Fields

| Field                                                     | Type                                                      | Required                                                  | Description                                               | Example                                                   |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| `text`                                                    | *string*                                                  | :heavy_check_mark:                                        | N/A                                                       |                                                           |
| `voiceId`                                                 | *string*                                                  | :heavy_minus_sign:                                        | N/A                                                       |                                                           |
| `characterVoiceId`                                        | *string*                                                  | :heavy_minus_sign:                                        | N/A                                                       |                                                           |
| `model`                                                   | *string*                                                  | :heavy_minus_sign:                                        | N/A                                                       | eleven_v3_multilingual                                    |
| `phonemeOverrides`                                        | [models.PhonemeOverride](../models/phoneme-override.md)[] | :heavy_minus_sign:                                        | N/A                                                       |                                                           |