# ComposeJobAck

Acknowledgement returned by `POST /v1/compose` when a stitch job has
been queued. The job is asynchronous — clients poll
`GET /v1/jobs/{id}` (with the `id` returned here) for terminal
status and the stitched output URL.


## Example Usage

```typescript
import { ComposeJobAck } from "@aeriox-co/api/models";

let value: ComposeJobAck = {
  id: "7aa6f13d-e89d-4338-adeb-c7d2769da623",
  type: "compose",
  status: "queued",
  operationId: "compose.stitch_per_minute",
  estimatedCostUsdMicros: 811498,
  estimatedCostUsd: 7431.15,
  createdAt: new Date("2026-06-29T06:14:11.799Z"),
};
```

## Fields

| Field                                                                                              | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `id`                                                                                               | *string*                                                                                           | :heavy_check_mark:                                                                                 | Job id; pass to `GET /v1/jobs/{id}` to poll.                                                       |
| `type`                                                                                             | [models.ComposeJobAckType](../models/compose-job-ack-type.md)                                      | :heavy_check_mark:                                                                                 | Discriminator. Always `compose` for this endpoint.                                                 |
| `status`                                                                                           | [models.ComposeJobAckStatus](../models/compose-job-ack-status.md)                                  | :heavy_check_mark:                                                                                 | Initial status. The job advances to `running` and then a terminal state asynchronously.            |
| `operationId`                                                                                      | [models.OperationId](../models/operation-id.md)                                                    | :heavy_check_mark:                                                                                 | Cost-spine operation id used to price this job.                                                    |
| `estimatedCostUsdMicros`                                                                           | *number*                                                                                           | :heavy_check_mark:                                                                                 | Reserved wallet amount in USD micros (`1 USD = 1_000_000`).                                        |
| `estimatedCostUsd`                                                                                 | *number*                                                                                           | :heavy_check_mark:                                                                                 | Reserved wallet amount in USD (convenience field; equals `estimated_cost_usd_micros / 1_000_000`). |
| `createdAt`                                                                                        | [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)      | :heavy_check_mark:                                                                                 | N/A                                                                                                |