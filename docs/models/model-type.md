# ModelType

## Example Usage

```typescript
import { ModelType } from "@aeriox-co/api/models";

let value: ModelType = "video";

// Open enum: unrecognized values are captured as Unrecognized<string>
```

## Values

```typescript
"image" | "video" | "audio" | "compose" | "training" | "prism" | Unrecognized<string>
```