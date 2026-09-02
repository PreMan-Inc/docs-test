# docs-test

Documentation site for the Greptile Codex API. Published to
<https://preman-inc.github.io/docs-test/> by `.github/workflows/pages.yml` on
every push to `main`.

## What is generated and what is not

`mkdocs.yml`, `docs/api/**`, `docs/sdk/**`, and `docs/changelog.md` are written
by PreMan. It composes an OpenAPI document from the live API contract, diffs it
against the previously released one, and opens a pull request here whenever the
contract moves. Do not hand-edit those paths; the next release overwrites them.

`docs/index.md` and `docs/getting-started.md` are hand-written and listed in
`.fernignore`, which is the mechanism that stops the generator from touching
them. Add any other page you want to keep to that file.

## Two things PreMan cannot do here

The `preman-guard` GitHub App holds `contents:write`, `metadata:read`, and
`pull_requests:write`. It has neither `workflows:write` nor `administration`,
which means:

1. It cannot create or modify anything under `.github/workflows/`. The Pages
   build workflow is committed by a person and stays under human control.
2. It cannot enable GitHub Pages. That is a one-time manual step in
   **Settings → Pages → Source: GitHub Actions**.

Both are deliberate. PreMan can change what the site says; it cannot change how
the site is built or where it is served from.

## Building locally

```bash
pip install -r requirements.txt
mkdocs serve
```

The workflow deliberately does not pass `--strict`. A hand-written page that is
absent from the generated nav produces an mkdocs warning, and under `--strict`
that warning would fail the build — meaning a routine generated pull request
could take the published site down.
