# GetPricingResponse

Rate card

## Example Usage

```typescript
import { GetPricingResponse } from "@aeriox-co/api/models/operations";

let value: GetPricingResponse = {
  currency: "Barbados Dollar",
  microsPerUnit: 669872,
  operations: [],
  generatedAt: new Date("2025-02-23T02:56:08.222Z"),
};
```

## Fields

| Field                                                                                         | Type                                                                                          | Required                                                                                      | Description                                                                                   |
| --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| `currency`                                                                                    | *string*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `microsPerUnit`                                                                               | *number*                                                                                      | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `operations`                                                                                  | [operations.Operation](../../models/operations/operation.md)[]                                | :heavy_check_mark:                                                                            | N/A                                                                                           |
| `generatedAt`                                                                                 | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) | :heavy_check_mark:                                                                            | N/A                                                                                           |