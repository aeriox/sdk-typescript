# JobStatus

## Example Usage

```typescript
import { JobStatus } from "@aeriox-co/api/models";

let value: JobStatus = "running";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"queued" | "running" | "completed" | "failed" | "cancelled" | "nsfw_blocked" | Unrecognized<string>
```