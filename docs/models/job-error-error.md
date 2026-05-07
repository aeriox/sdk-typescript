# JobErrorError

## Example Usage

```typescript
import { JobErrorError } from "@aeriox-co/api/models";

let value: JobErrorError = {
  code: "insufficient_funds",
};
```

## Fields

| Field                 | Type                  | Required              | Description           | Example               |
| --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| `code`                | *string*              | :heavy_check_mark:    | N/A                   | insufficient_funds    |
| `message`             | *string*              | :heavy_minus_sign:    | N/A                   |                       |
| `details`             | Record<string, *any*> | :heavy_minus_sign:    | N/A                   |                       |