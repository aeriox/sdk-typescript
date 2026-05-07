# ListNodesResponse

Card list (dual-emitted)

## Example Usage

```typescript
import { ListNodesResponse } from "@aeriox-co/api/models/operations";

let value: ListNodesResponse = {
  nodes: [
    {},
  ],
  cards: [
    {
      "key": "<value>",
    },
    {
      "key": "<value>",
    },
    {
      "key": "<value>",
    },
  ],
  count: 997101,
  limit: 86884,
  offset: 860696,
};
```

## Fields

| Field                   | Type                    | Required                | Description             |
| ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| `nodes`                 | Record<string, *any*>[] | :heavy_check_mark:      | N/A                     |
| `cards`                 | Record<string, *any*>[] | :heavy_check_mark:      | N/A                     |
| `count`                 | *number*                | :heavy_check_mark:      | N/A                     |
| `limit`                 | *number*                | :heavy_check_mark:      | N/A                     |
| `offset`                | *number*                | :heavy_check_mark:      | N/A                     |