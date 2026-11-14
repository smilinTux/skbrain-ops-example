---
id: synthesis-restart-before-redesign
type: synthesis
namespace: ops
lifecycle: canon
title: restart before redesign
tags: [operations]
edges:
  - {target: service-widget, type: documents}
state_refs:
  actions: []
created: 2026-07-31
updated: 2026-07-31
---

# restart before redesign

When a service wedges, the first move is the reviewed restart runbook, not a
redesign: [[runbook-restart-widget-bridge]] for [[service-widget]]. Record the
cause in a known error ([[ke-widget-wedge]]) so the redesign has evidence.
