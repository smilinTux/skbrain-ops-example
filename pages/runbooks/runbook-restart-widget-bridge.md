---
id: runbook-restart-widget-bridge
type: runbook
namespace: ops
lifecycle: canon
title: Recover a silently wedged widget bridge
tags: [widget, bridge, restart, operator]
edges:
  - {target: ke-widget-wedge, type: remediates}
  - {target: service-widget, type: touches}
  - {target: node-example-1, type: touches}
state_refs:
  kedb: ke-widget-wedge
  actions: [restart-widget-bridge]
created: 2026-07-31
updated: 2026-07-31
---

# Recover a silently wedged widget bridge

Standard operator action `restart-widget-bridge` (reversible, blast radius
low). Remediates [[ke-widget-wedge]] on [[service-widget]].

## Preconditions

- The fleet is NOT frozen.
- `BridgeAlive` is False: the last-poll heartbeat is older than 600s while the
  daemon is up.

## Steps

1. Confirm the wedge:

   ```bash
   systemctl --user status widget-bridge.service --no-pager | head -20
   ```

2. Restart the wedged unit:

   ```bash
   systemctl --user restart widget-bridge.service
   ```

## Verify

```bash
systemctl --user is-active widget-bridge.service   # -> active
```

## Rollback

Idempotent; nothing to undo.

## Escalate

If it re-wedges quickly, the network path is the real problem; see
[[ke-widget-wedge]].
