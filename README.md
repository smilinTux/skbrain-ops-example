# skbrain-ops-example

Maturity tier: T0 (N/A, no key material). Phase: example instance of the skbrain framework.

This is the fixture the public `skbrain-ops-template` repo is generated from. It is
a fake estate called `example`, with one page of each type. Copy it to start a real
estate canon, then replace every value.

## Quickstart

```bash
git submodule add https://github.com/smilinTux/skbrain framework
git -C framework checkout skbrain-v1.0.0
pip install ./framework
skbrain check --canon .
```

## Layout

| Path | What |
|---|---|
| `skbrain.yaml` | Instance config (schema `skbrain.instance.v1`) |
| `framework/` | The pinned framework, a read-only submodule |
| `pages/` | Canon pages, one slug space, directories are presentation |
| `baselines/cmdb-drift.json` | The CMDB drift baseline (lowered as findings are fixed) |
| `.forgejo/workflows/skbrain-check.yml` | CI: runs the pinned framework's check |

## Related projects / See also

- Depends on: [skbrain](https://github.com/smilinTux/skbrain), the framework pinned in `framework/`.
- Siblings: [skrsi](https://github.com/smilinTux/skrsi), which produces the evidence pages cite.
- Standards: [sk-standards](https://github.com/smilinTux/sk-standards).
