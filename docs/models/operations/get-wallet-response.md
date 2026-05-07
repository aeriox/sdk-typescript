# GetWalletResponse

Wallet snapshot

## Example Usage

```typescript
import { GetWalletResponse } from "@aeriox-co/api/models/operations";

let value: GetWalletResponse = {
  balance: {
    "key": "<value>",
    "key1": "<value>",
    "key2": "<value>",
  },
  recentTransactions: [
    {
      "key": "<value>",
      "key1": "<value>",
      "key2": "<value>",
    },
    {},
    {
      "key": "<value>",
      "key1": "<value>",
      "key2": "<value>",
    },
  ],
};
```

## Fields

| Field                   | Type                    | Required                | Description             |
| ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| `balance`               | Record<string, *any*>   | :heavy_check_mark:      | N/A                     |
| `recentTransactions`    | Record<string, *any*>[] | :heavy_check_mark:      | N/A                     |