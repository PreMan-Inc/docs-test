# Getting started

## Base URL

```
https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws
```

Every path in the [API reference](index.md) is relative to that host.

## Authentication

The mock catalogue endpoints under `/api/v1/mock/` are open and need no
credential, which makes them the easiest place to confirm you can reach the
API at all:

```bash
curl https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws/health
```

The project and task endpoints require a bearer token. Register, then exchange
your credentials for one:

```bash
curl -X POST "$BASE_URL/api/v1/auth/register" \
  -H 'Content-Type: application/json' \
  -d '{"email":"you@example.com","password":"..."}'
```

Send the token you get back as `Authorization: Bearer <token>` on every
subsequent request. The generated SDKs take the token once when you construct
the client and attach it for you — see the SDK page for your language.

## Which client should I use?

If a generated SDK exists for your language, use it. The clients are produced
from the same contract as this reference and are regenerated together with it,
so a required field added to a request body becomes a compile error rather
than a runtime 422.

If you are calling the API directly, read the [changelog](changelog.md) before
you upgrade across a major version — it lists every breaking change and what
it costs a caller pinned to the previous release.
