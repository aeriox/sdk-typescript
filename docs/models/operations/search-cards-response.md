# SearchCardsResponse

Search results

## Example Usage

```typescript
import { SearchCardsResponse } from "@aeriox-co/api/models/operations";

let value: SearchCardsResponse = {
  items: [
    {
      id: "eecb4dc2-9d2e-4e84-9d68-c91d9976fdc1",
      cardType: "<value>",
      name: "<value>",
      similarity: 4087.84,
      createdAt: new Date("2026-04-17T19:31:01.357Z"),
    },
  ],
  total: 616886,
};
```

## Fields

| Field                                                | Type                                                 | Required                                             | Description                                          |
| ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `items`                                              | [operations.Item](../../models/operations/item.md)[] | :heavy_check_mark:                                   | N/A                                                  |
| `total`                                              | *number*                                             | :heavy_check_mark:                                   | N/A                                                  |
| `queryTokens`                                        | *number*                                             | :heavy_minus_sign:                                   | N/A                                                  |
| `queryDocChars`                                      | *number*                                             | :heavy_minus_sign:                                   | N/A                                                  |