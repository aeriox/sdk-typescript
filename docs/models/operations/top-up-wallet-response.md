# TopUpWalletResponse

PaymentIntent created

## Example Usage

```typescript
import { TopUpWalletResponse } from "@aeriox-co/api/models/operations";

let value: TopUpWalletResponse = {
  paymentIntentId: "<id>",
  status: "<value>",
  amountUsd: 7243.23,
};
```

## Fields

| Field                 | Type                  | Required              | Description           |
| --------------------- | --------------------- | --------------------- | --------------------- |
| `paymentIntentId`     | *string*              | :heavy_check_mark:    | N/A                   |
| `clientSecret`        | *string*              | :heavy_minus_sign:    | N/A                   |
| `status`              | *string*              | :heavy_check_mark:    | N/A                   |
| `amountUsd`           | *number*              | :heavy_check_mark:    | N/A                   |
| `nextAction`          | Record<string, *any*> | :heavy_minus_sign:    | N/A                   |