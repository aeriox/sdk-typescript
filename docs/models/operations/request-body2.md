# RequestBody2

## Example Usage

```typescript
import { RequestBody2 } from "@aeriox-co/api/models/operations";

let value: RequestBody2 = {
  enabled: true,
  thresholdUsd: 507.72,
  amountUsd: 7706.01,
  stripePaymentMethodId: "<id>",
};
```

## Fields

| Field                   | Type                    | Required                | Description             |
| ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| `enabled`               | *true*                  | :heavy_check_mark:      | N/A                     |
| `thresholdUsd`          | *number*                | :heavy_check_mark:      | N/A                     |
| `amountUsd`             | *number*                | :heavy_check_mark:      | N/A                     |
| `stripePaymentMethodId` | *string*                | :heavy_check_mark:      | N/A                     |