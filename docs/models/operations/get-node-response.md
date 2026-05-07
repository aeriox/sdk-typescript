# GetNodeResponse

Node + edges

## Example Usage

```typescript
import { GetNodeResponse } from "@aeriox-co/api/models/operations";

let value: GetNodeResponse = {
  node: {
    "key": "<value>",
  },
  edges: [],
};
```

## Fields

| Field                   | Type                    | Required                | Description             |
| ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| `node`                  | Record<string, *any*>   | :heavy_check_mark:      | N/A                     |
| `edges`                 | Record<string, *any*>[] | :heavy_check_mark:      | N/A                     |