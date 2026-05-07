# GetGenerationResponse

Generation row

## Example Usage

```typescript
import { GetGenerationResponse } from "@aeriox-co/api/models/operations";

let value: GetGenerationResponse = {
  id: "10bc651e-336d-40d6-8080-0244af1216f7",
  status: "success",
  model: "Camaro",
};
```

## Fields

| Field                                                                                                | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `id`                                                                                                 | *string*                                                                                             | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `status`                                                                                             | [operations.GetGenerationStatus](../../models/operations/get-generation-status.md)                   | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `model`                                                                                              | *string*                                                                                             | :heavy_check_mark:                                                                                   | N/A                                                                                                  |
| `prompt`                                                                                             | *string*                                                                                             | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `kind`                                                                                               | *string*                                                                                             | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `creditsCharged`                                                                                     | *number*                                                                                             | :heavy_minus_sign:                                                                                   | Studio credit units charged (legacy display field; not USD; informational only for API-key callers). |
| `assetUrls`                                                                                          | *string*[]                                                                                           | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `error`                                                                                              | *string*                                                                                             | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `createdAt`                                                                                          | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)        | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |
| `updatedAt`                                                                                          | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)        | :heavy_minus_sign:                                                                                   | N/A                                                                                                  |