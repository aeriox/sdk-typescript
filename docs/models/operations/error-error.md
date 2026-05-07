# ErrorError

## Example Usage

```typescript
import { ErrorError } from "@aeriox-co/api/models/operations";

let value: ErrorError = {
  code: "insufficient_funds",
};
```

## Fields

| Field                 | Type                  | Required              | Description           | Example               |
| --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| `code`                | *string*              | :heavy_check_mark:    | N/A                   | insufficient_funds    |
| `message`             | *string*              | :heavy_minus_sign:    | N/A                   |                       |
| `details`             | Record<string, *any*> | :heavy_minus_sign:    | N/A                   |                       |