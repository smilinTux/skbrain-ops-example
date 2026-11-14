# skbrain-ops-example: Standard Operating Procedures

The example estate canon: runbooks, known errors, postmortems and CMDB
definitions for one estate, checked by the pinned skbrain framework.

## 1. Overview

Purpose: hold this estate's durable operations knowledge as reviewed pages in git.
It does not hold state (incidents, live status) and it holds no secrets.

## 2. Architecture

```mermaid
flowchart LR
  PR["pull request"] --> CI["skbrain check (pinned framework)"]
  CI --> M["merge to main (reviewer, never the author)"]
  M --> T["projector node: git pull, skbrain sync --commit"]
  T --> DB["ops schema in the node-local Postgres"]
  DB --> A["agents retrieve before acting"]
```

## 3. Build

None. The canon is Markdown. `pip install ./framework` installs the checker.

## 4. Test

`skbrain check --canon .` is the gate. It fails on a bad front matter, a secret,
an em or en dash, or a page that does not belong to this estate.

## 5. Release / Deploy

Merge to `main`. The projector node pulls with `--ff-only` and projects. Bump the
framework by a PR that changes the submodule and `framework:` in `skbrain.yaml`.
Front-end / Exposure: N/A, no network surface.

## 6. Configuration / Usage

`skbrain.yaml` is the only config. `SKBRAIN_CANON` points tools at this checkout.

## 7. API / Reference

See `framework/docs/SCHEMA.md` for the page schema and `framework/docs/SKRSI-CONTRACT.md`
for how skrsi proposes pages.

## 8. Troubleshooting

| Symptom | Check |
|---|---|
| `skbrain check` reports `estate-repo-name` | The repo must be named `skbrain-ops-<estate>` |
| `skbrain doctor` reports `skbrain:pin` | Installed version, `framework:` and the submodule tag must be equal |
| `sync --commit` refuses | `SKBRAIN_ESTATE` and the host must match `skbrain.yaml` |

## 9. Maturity-tier + Version reference

T0 (N/A, no key material). Example instance; pins `skbrain-v1.0.1`.

<!-- docs-evidence
verified: 2026-11-14
checks:
  - name: instance config present
    run: test -f skbrain.yaml
  - name: pages directory present
    run: test -d pages
  - name: CI workflow present
    run: test -f .forgejo/workflows/skbrain-check.yml
-->
