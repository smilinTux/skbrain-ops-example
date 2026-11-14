# AGENTS.md (skbrain-ops-example)

This is the example estate canon. The page schema, slug rules, edge vocabulary
and linking rules live in the pinned framework, not here:
read `framework/docs/SCHEMA.md` first.

## Estate rules (the only things this file adds)

- This canon belongs to estate `example` and to nobody else. Never copy a page
  in from another estate's canon, and never cite another estate's evidence.
- Pages are authored by pull request. Never push to `main`. The author of a PR
  never merges it.
- No secrets in pages. Name the vault entry, never the value.
- No em or en dashes anywhere. `skbrain check` fails on them.

## Commands

```bash
skbrain check --canon .            # the CI check, runs offline
skbrain lint --canon .             # secret lint only
skbrain doctor --canon .           # install and pin health
```

Set `SKBRAIN_CANON` to this checkout. skbrain has no default canon.
