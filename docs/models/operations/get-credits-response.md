# GetCreditsResponse

Credit balance

## Example Usage

```typescript
import { GetCreditsResponse } from "@aeriox-co/api/models/operations";

let value: GetCreditsResponse = {
  plan: "<value>",
  credits: {},
};
```

## Fields

| Field                                                    | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `plan`                                                   | *string*                                                 | :heavy_check_mark:                                       | N/A                                                      |
| `credits`                                                | [operations.Credits](../../models/operations/credits.md) | :heavy_check_mark:                                       | N/A                                                      |
| `image`                                                  | Record<string, *any*>                                    | :heavy_minus_sign:                                       | N/A                                                      |
| `video`                                                  | Record<string, *any*>                                    | :heavy_minus_sign:                                       | N/A                                                      |
| `apiKey24hSpendUsd`                                      | *number*                                                 | :heavy_minus_sign:                                       | N/A                                                      |
| `apiKeyDailyCapUsd`                                      | *number*                                                 | :heavy_minus_sign:                                       | N/A                                                      |