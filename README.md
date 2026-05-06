# @aeriox/api

The TypeScript SDK for the [AERIOX Studio public API](https://create.aeriox.co/docs).

> **Auto-generated.** This SDK is regenerated from the canonical OpenAPI 3.1 spec at `https://api.aeriox.co/openapi.json` via [Speakeasy](https://www.speakeasy.com). Do not edit generated files directly — they will be overwritten on the next regeneration. Custom code lives in `src/hooks/` (preserved across regenerations).

## Installation

```bash
npm install @aeriox/api
```

## Quick start

```typescript
import { Aeriox } from '@aeriox/api';

const sdk = new Aeriox({
  apiKey: process.env.AERIOX_API_KEY,  // sk_live_*
});

// Submit an image generation job
const job = await sdk.generation.generateImage({
  model: 'fal-ai/flux/schnell',
  prompt: 'a cyberpunk samurai in neon Tokyo',
});

console.log(job.jobId);

// Poll the job
const status = await sdk.jobs.getJob({ id: job.jobId });
console.log(status.status, status.outputUrls);
```

## Authentication

Two paths:

1. **API key** — `Authorization: Bearer sk_live_*` or `X-Api-Key:` header. Best for backend / CI / server-to-server.
2. **OAuth 2.0 PKCE** — for end-user-facing apps where users authorize your app to act on their AERIOX workspace. See [the auth guide](https://create.aeriox.co/docs/auth).

## Versioning

SDK semver follows the SDK changelog independently from the API version. The API URL path stays at `/v1/*` across non-breaking changes. Breaking API changes ship as `/v2/*` with a deprecation period on `/v1/*`.

## Generation pipeline

This repo is regenerated on a schedule (Mondays 09:00 UTC) and on manual `workflow_dispatch` whenever the spec changes upstream. Speakeasy opens a PR for review; merging the PR triggers an OIDC-based publish to npm.

See `.speakeasy/workflow.yaml` for the generation config and `.github/workflows/` for the CI.

## Support

- Docs: https://create.aeriox.co/docs
- API reference: https://api.aeriox.co/openapi.json
- Issues: file in this repo for SDK-specific issues, or in [aeriox-studio](https://github.com/aeriox/aeriox-studio) for API behavior issues
