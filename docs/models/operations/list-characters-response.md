# ListCharactersResponse

List of characters

## Example Usage

```typescript
import { ListCharactersResponse } from "@aeriox-co/api/models/operations";

let value: ListCharactersResponse = {
  data: [
    {
      id: "a0af01dc-3b6c-4e14-8a99-23bcc9d581f3",
      name: "<value>",
      status: "ready",
      createdAt: new Date("2024-10-06T09:55:02.249Z"),
    },
  ],
};
```

## Fields

| Field                                           | Type                                            | Required                                        | Description                                     |
| ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| `data`                                          | [models.Character](../../models/character.md)[] | :heavy_check_mark:                              | N/A                                             |
| `nextCursor`                                    | *string*                                        | :heavy_minus_sign:                              | N/A                                             |