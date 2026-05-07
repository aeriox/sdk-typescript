# CreateGenerationResponseBody

Generation queued

## Example Usage

```typescript
import { CreateGenerationResponseBody } from "@aeriox-co/api/models/operations";

let value: CreateGenerationResponseBody = {
  generationId: "f3b2becf-369c-4279-bb18-c337adb7c7c7",
  status: "queued",
  model: "ATS",
};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `generationId`                                                                                       | *string*                                                                                             | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `providerRequestId`                                                                                  | *string*                                                                                             | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `status`                                                                                             | [operations.CreateGenerationStatus](../../models/operations/create-generation-status.md)             | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `model`                                                                                              | *string*                                                                                             | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `kind`                                                                                               | [operations.CreateGenerationKind](../../models/operations/create-generation-kind.md)                 | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `creditsCharged`                                                                                     | *number*                                                                                             | :heavy_minus_sign:                                                                                   | Studio credit units charged (legacy display field; not USD; informational only for API-key callers). |
| `cost`                                                                                               | [operations.Cost](../../models/operations/cost.md)                                                   | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `pollUrl`                                                                                            | *string*                                                                                             | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |