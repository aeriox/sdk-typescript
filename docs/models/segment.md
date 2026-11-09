# Segment

## Example Usage

```typescript
import { Segment } from "@aeriox-co/api/models";

let value: Segment = {
  assetId: "eed83f17-51ce-4c43-bbb7-cbe966267f50",
  startTime: 1952.28,
  duration: 4077.22,
};
```

## Fields

| Field                                                                                                                                                        | Type                                                                                                                                                         | Required                                                                                                                                                     | Description                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `assetId`                                                                                                                                                    | *string*                                                                                                                                                     | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `startTime`                                                                                                                                                  | *number*                                                                                                                                                     | :heavy_check_mark:                                                                                                                                           | Position of this segment on the output timeline, in seconds. Each asset plays from its own start for `duration` seconds; segments are joined in array order. |
| `duration`                                                                                                                                                   | *number*                                                                                                                                                     | :heavy_check_mark:                                                                                                                                           | N/A                                                                                                                                                          |
| `effects`                                                                                                                                                    | Record<string, *any*>                                                                                                                                        | :heavy_minus_sign:                                                                                                                                           | N/A                                                                                                                                                          |