# Operation

## Example Usage

```typescript
import { Operation } from "@aeriox-co/api/models/operations";

let value: Operation = {
  operationId: "<id>",
  model: "Land Cruiser",
  provider: "<value>",
  unit: "kelvin",
  priceUsdMicros: 137101,
  priceUsd: 7854.78,
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `operationId`      | *string*           | :heavy_check_mark: | N/A                |
| `model`            | *string*           | :heavy_check_mark: | N/A                |
| `provider`         | *string*           | :heavy_check_mark: | N/A                |
| `unit`             | *string*           | :heavy_check_mark: | N/A                |
| `priceUsdMicros`   | *number*           | :heavy_check_mark: | N/A                |
| `priceUsd`         | *number*           | :heavy_check_mark: | N/A                |
| `notes`            | *string*           | :heavy_minus_sign: | N/A                |