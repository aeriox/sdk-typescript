# EstimateGenerationResponse

Estimate result

## Example Usage

```typescript
import { EstimateGenerationResponse } from "@aeriox-co/api/models/operations";

let value: EstimateGenerationResponse = {
  credits: 8498.99,
  usd: 1914.88,
  estimatedSeconds: 4470.21,
  model: "Camaro",
  wouldSucceed: true,
  reasonsBlocked: [],
};
```

## Fields

| Field                                                                                    | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `credits`                                                                                | *number*                                                                                 | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `usd`                                                                                    | *number*                                                                                 | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `estimatedSeconds`                                                                       | *number*                                                                                 | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `model`                                                                                  | *string*                                                                                 | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `kind`                                                                                   | [operations.EstimateGenerationKind](../../models/operations/estimate-generation-kind.md) | :heavy_minus_sign:                                                                       | N/A                                                                                      |
| `wouldSucceed`                                                                           | *boolean*                                                                                | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `reasonsBlocked`                                                                         | [operations.ReasonsBlocked](../../models/operations/reasons-blocked.md)[]                | :heavy_check_mark:                                                                       | N/A                                                                                      |
| `currentBalance`                                                                         | *number*                                                                                 | :heavy_minus_sign:                                                                       | N/A                                                                                      |
| `spendCap`                                                                               | Record<string, *any*>                                                                    | :heavy_minus_sign:                                                                       | N/A                                                                                      |