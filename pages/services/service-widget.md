---
id: service-widget
type: service
namespace: ops
lifecycle: canon
title: widget (example service)
tags: [widget, example]
edges:
  - {target: node-example-1, type: runs_on}
state_refs:
  actions: [restart-widget-bridge]
created: 2026-07-31
updated: 2026-07-31
---

# service-widget

The example service.

## Definition

- Host process: `widget-bridge.service`.
- Runs on [[node-example-1]].

## Known errors and runbooks

- [[ke-widget-wedge]] -> [[runbook-restart-widget-bridge]].
