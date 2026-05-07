# CreateNodeRequest

## Example Usage

```typescript
import { CreateNodeRequest } from "@aeriox-co/api/models/operations";

let value: CreateNodeRequest = {
  name: "<value>",
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `cardType`                                           | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `nodeType`                                           | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `name`                                               | *string*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `description`                                        | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `attributes`                                         | Record<string, *any*>                                | :heavy_minus_sign:                                   | N/A                                                  |
| `previewUrl`                                         | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `thumbUrl`                                           | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `parentId`                                           | *string*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `visibilityScopes`                                   | *string*[]                                           | :heavy_minus_sign:                                   | N/A                                                  |
| `edges`                                              | [operations.Edge](../../models/operations/edge.md)[] | :heavy_minus_sign:                                   | N/A                                                  |