<!-- Start SDK Example Usage [usage] -->
```typescript
import { Aeriox } from "@aeriox-co/api";

const aeriox = new Aeriox();

async function run() {
  const result = await aeriox.discovery.getOpenApiSpec();

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->