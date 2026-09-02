# TypeScript

Generated client for greptile-codex-backend, regenerated from the API contract on every release. Method names and request types come from the same document as the [reference](../index.md), so the two cannot disagree.

## Install

```bash
npm install greptile-codex-backend
```

## Construct the client

```typescript
import { Client } from "greptile-codex-backend";

const client = new Client({
  baseUrl: "https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws",
  # no credential required,
});
```

## Make a call

`GET /` — Get the API root

```typescript
const response = await client.root();
console.log(response);
```

Every other operation is listed in the [reference](../index.md), one page per tag.
