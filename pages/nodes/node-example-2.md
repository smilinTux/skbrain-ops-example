---
id: node-example-2
type: node
namespace: ops
lifecycle: canon
title: example-2 (secondary node)
tags: [node, example, secondary]
edges:
  - {target: node-example-1, type: connects_to}
state_refs:
  actions: []
created: 2026-07-31
updated: 2026-07-31
---

# node-example-2: the secondary node

Hostname `example-2`, the secondary box of the example estate.

## Role

- Secondary host for [[service-widget]].
- Holds a warm standby.

## Runbooks that touch this node

- [[runbook-restart-widget-bridge]].

## Notes

No secrets on this page; credentials live in the secret vault.
