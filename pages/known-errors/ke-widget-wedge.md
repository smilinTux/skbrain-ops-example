---
id: ke-widget-wedge
type: known-error
namespace: ops
lifecycle: canon
title: widget bridge silent wedge
tags: [operator, widget, bridge]
edges:
  - {target: service-widget, type: touches}
  - {target: node-example-1, type: touches}
state_refs:
  kedb: ke-widget-wedge
  actions: [restart-widget-bridge]
created: 2026-07-31
updated: 2026-07-31
---

# ke-widget-wedge: widget bridge silent wedge

Canon known-error for the operator condition `BridgeAlive`.

## Symptoms

- `BridgeAlive` is False.
- The bridge last-poll heartbeat is older than 600s while the daemon is up.

## Root cause

The poll loop hung on a connect timeout and stopped polling without exiting, so
the process looks alive but delivers nothing.

## Workaround

Restart the wedged unit. Full procedure: [[runbook-restart-widget-bridge]].

## Permanent fix status

Workaround only. A poll watchdog that exits on a stale heartbeat would let the
init system restart it automatically.

## Links

Remediated by [[runbook-restart-widget-bridge]]. Affects [[service-widget]] on
[[node-example-1]].
