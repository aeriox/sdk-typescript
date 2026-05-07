# ErrorT

## Example Usage

```typescript
import { ErrorT } from "@aeriox-co/api/models/operations";

let value: ErrorT = {
  error: {
    code: "insufficient_funds",
  },
};
```

## Fields

| Field                                                           | Type                                                            | Required                                                        | Description                                                     |
| --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------- |
| `error`                                                         | [operations.ErrorError](../../models/operations/error-error.md) | :heavy_check_mark:                                              | N/A                                                             |