# Greptile Codex API

The REST API behind Greptile Codex, with generated client libraries for every
language we publish.

Two halves of this site are maintained differently, and it is worth knowing
which is which:

- **The API reference and the SDK pages are generated.** They are rebuilt from
  the live API contract every time that contract changes, so they cannot drift
  from what the service actually accepts and returns.
- **This page and [Getting started](getting-started.md) are hand-written.** They
  are listed in `.fernignore`, which is what stops the generator from
  overwriting them.

Start with [Getting started](getting-started.md) for authentication and your
first request. The [changelog](changelog.md) records every contract change,
which release it landed in, and whether it was breaking.

## How this site stays current

PreMan watches the API repository. When a push changes the shape of an
endpoint, it composes a fresh OpenAPI document, diffs it against the last
released one, derives the semantic version bump from the severity of what
moved, regenerates the client libraries, and opens a pull request here with the
updated reference. Merging that pull request publishes the site.

Nothing on this site is written by hand from an endpoint's source. If the
reference says an endpoint takes a required `region` query parameter, that is
because the contract says so.
