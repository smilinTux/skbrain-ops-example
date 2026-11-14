---
id: ci-widget-db
type: ci
namespace: ops
lifecycle: canon
title: widget database (definition)
tags: [widget, database]
edges:
  - {target: node-example-1, type: runs_on}
state_refs:
  actions: []
created: 2026-07-31
updated: 2026-07-31
---

# ci-widget-db

The DEFINITION of the widget database: a PostgreSQL instance owned by
[[service-widget]], intended to run on [[node-example-1]], listening on
`127.0.0.1:5432`, data under `/var/lib/widget/db`.

No live status here. Status is state, and state lives in the CMDB store.

## Runbooks that touch this item

- [[runbook-restart-widget-bridge]]
