# Security

## Threat model summary

This canon is private operations knowledge for one estate. The risks are secrets
committed into pages, another estate's content crossing the wall, and a bad page
being projected into retrieval.

## Reporting

Report a leak or a wall breach to the estate operator immediately, privately. Do
not open a public issue.

## Secret handling

Pages name vault entries, never values. `skbrain lint` runs in CI and in every
sync and fails on secret-shaped material.

## Dependency posture

The only dependency is the pinned framework submodule. CI holds no secrets and
uploads no artifacts.
