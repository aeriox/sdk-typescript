# ComposeRequest

## Example Usage

```typescript
import { ComposeRequest } from "@aeriox-co/api/models";

let value: ComposeRequest = {
  segments: [
    {
      assetId: "c773d9f5-7bce-4dbe-b320-a6eb823e9858",
      startTime: 8107.96,
      duration: 3353.81,
    },
  ],
};
```

## Fields

| Field                                             | Type                                              | Required                                          | Description                                       |
| ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------- |
| `segments`                                        | [models.Segment](../models/segment.md)[]          | :heavy_check_mark:                                | N/A                                               |
| `outputResolution`                                | *string*                                          | :heavy_minus_sign:                                | N/A                                               |
| `outputFormat`                                    | [models.OutputFormat](../models/output-format.md) | :heavy_minus_sign:                                | N/A                                               |