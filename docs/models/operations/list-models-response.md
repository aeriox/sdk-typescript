# ListModelsResponse

Model catalog

## Example Usage

```typescript
import { ListModelsResponse } from "@aeriox-co/api/models/operations";

let value: ListModelsResponse = {
  data: [
    {
      modelId: "<id>",
      type: "prism",
      provider: "<value>",
      costUsdPerUnit: 4377.26,
      unit: "volt",
    },
  ],
};
```

## Fields

| Field                                   | Type                                    | Required                                | Description                             |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `data`                                  | [models.Model](../../models/model.md)[] | :heavy_check_mark:                      | N/A                                     |