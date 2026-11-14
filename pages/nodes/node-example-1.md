---
id: node-example-1
type: node
namespace: ops
lifecycle: canon
title: example-1 (primary node)
tags: [node, example, primary]
edges:
  - {target: node-example-2, type: connects_to}
state_refs:
  actions: []
created: 2026-07-31
updated: 2026-07-31
---

# node-example-1: the primary node

Hostname `example-1`, the primary box of the example estate.

## Role

- Primary host for [[service-widget]].
- Runs the local projection database.

## Runbooks that touch this node

- [[runbook-restart-widget-bridge]].

## Notes

No secrets on this page; credentials live in the secret vault.
