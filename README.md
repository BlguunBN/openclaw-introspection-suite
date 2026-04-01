# OpenClaw Introspection Suite

A small, opinionated skill suite for understanding, auditing, and improving OpenClaw-style runtimes without collapsing everything into one vague mega-skill.

## What’s inside

- `runtime-surface-inspector` — fit checks, architecture breakdowns, overlap mapping
- `tool-manifest-generator` — capability reports, inventories, runtime summaries
- `permission-risk-summarizer` — approvals, trust boundaries, hardening priorities
- `runtime-improvement-planner` — prioritized next steps and roadmaps

## Recommended flow

1. Inspect the runtime surface
2. Generate a capability manifest
3. Summarize risk and approvals
4. Turn the findings into a prioritized plan

See:
- `OPENCLAW-INTROSPECTION-SUITE.md`
- `OPENCLAW-INTROSPECTION-WORKFLOW.md`
- `TRIGGER-TEST-MATRIX.md`

## Why this exists

These skills stay separate on purpose:
- one skill for **fit / architecture judgment**
- one for **inventory / capability summaries**
- one for **risk / approval posture**
- one for **prioritized next steps**

That keeps trigger quality high and overlap low.
