# ListPrismsResponse

Prism catalog

## Example Usage

```typescript
import { ListPrismsResponse } from "@aeriox-co/api/models/operations";

let value: ListPrismsResponse = {
  data: [
    {
      id: "<id>",
      name: "<value>",
      category: "<value>",
      compatibleWith: [],
    },
  ],
};
```

## Fields

| Field                                   | Type                                    | Required                                | Description                             |
| --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| `data`                                  | [models.Prism](../../models/prism.md)[] | :heavy_check_mark:                      | N/A                                     |