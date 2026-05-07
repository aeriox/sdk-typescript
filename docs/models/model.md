# Model

## Example Usage

```typescript
import { Model } from "@aeriox-co/api/models";

let value: Model = {
  modelId: "<id>",
  type: "compose",
  provider: "<value>",
  costUsdPerUnit: 3432.22,
  unit: "second",
};
```

## Fields

| Field                                       | Type                                        | Required                                    | Description                                 |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| `modelId`                                   | *string*                                    | :heavy_check_mark:                          | N/A                                         |
| `type`                                      | [models.ModelType](../models/model-type.md) | :heavy_check_mark:                          | N/A                                         |
| `provider`                                  | *string*                                    | :heavy_check_mark:                          | N/A                                         |
| `maxResolution`                             | *string*                                    | :heavy_minus_sign:                          | N/A                                         |
| `maxDurationS`                              | *number*                                    | :heavy_minus_sign:                          | N/A                                         |
| `supportsAudio`                             | *boolean*                                   | :heavy_minus_sign:                          | N/A                                         |
| `costUsdPerUnit`                            | *number*                                    | :heavy_check_mark:                          | N/A                                         |
| `unit`                                      | *string*                                    | :heavy_check_mark:                          | N/A                                         |