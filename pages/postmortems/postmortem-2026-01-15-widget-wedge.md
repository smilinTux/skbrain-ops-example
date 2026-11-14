---
id: postmortem-2026-01-15-widget-wedge
type: postmortem
namespace: ops
lifecycle: reviewed
title: widget bridge wedged for two hours
tags: [widget, bridge]
lesson_tags: [job-failure-streak]
edges:
  - {target: service-widget, type: about}
  - {target: runbook-restart-widget-bridge, type: promoted}
state_refs:
  kedb: ke-widget-wedge
evidence:
  - {kind: skrsi-evidence, ref: "skrsi-config-example@a1b2c3d:evidence/example-1/2026-01-15.json"}
created: 2026-01-15
updated: 2026-01-15
---

# widget bridge wedged for two hours

## What happened

The widget bridge stopped polling but the process stayed up, so nothing alerted.

## Timeline

- 10:00 last successful poll.
- 12:05 an operator noticed missing deliveries.
- 12:10 the unit was restarted and polling resumed.

## Root cause

A connect timeout hung the poll loop without exiting. See [[ke-widget-wedge]].

## What changed

[[runbook-restart-widget-bridge]] was written, and [[lesson-alert-on-stale-heartbeat]] proposed.

## Open items

- A watchdog that exits on a stale heartbeat.
