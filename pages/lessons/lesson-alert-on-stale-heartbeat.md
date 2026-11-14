---
schema: skrsi.lesson.v1
id: lesson-alert-on-stale-heartbeat
type: lesson
title: Alert on a stale heartbeat, not only on a dead process
service: [widget]
tags: [job-failure-streak]
class: reliability
evidence:
  - {kind: artifact, ref: "skrsi-config-example@a1b2c3d:evidence/example-1/2026-01-15.json"}
rule: Any long-running unit that can hang without exiting must publish a heartbeat and alert when it goes stale.
check: none yet
status: proposed
visibility: private
namespace: ops
lifecycle: draft
edges:
  - {target: ke-widget-wedge, type: remediates}
created: 2026-01-15
updated: 2026-01-15
---

# Alert on a stale heartbeat, not only on a dead process

The widget bridge hung for two hours while its process stayed alive. A process
check could not see it. See [[postmortem-2026-01-15-widget-wedge]].
