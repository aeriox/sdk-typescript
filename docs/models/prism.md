# Prism

## Example Usage

```typescript
import { Prism } from "@aeriox-co/api/models";

let value: Prism = {
  id: "<id>",
  name: "<value>",
  category: "<value>",
  compatibleWith: [],
};
```

## Fields

| Field                                                   | Type                                                    | Required                                                | Description                                             |
| ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------- |
| `id`                                                    | *string*                                                | :heavy_check_mark:                                      | N/A                                                     |
| `name`                                                  | *string*                                                | :heavy_check_mark:                                      | N/A                                                     |
| `description`                                           | *string*                                                | :heavy_minus_sign:                                      | N/A                                                     |
| `category`                                              | *string*                                                | :heavy_check_mark:                                      | N/A                                                     |
| `compatibleWith`                                        | [models.CompatibleWith](../models/compatible-with.md)[] | :heavy_check_mark:                                      | N/A                                                     |
| `previewUrl`                                            | *string*                                                | :heavy_minus_sign:                                      | N/A                                                     |