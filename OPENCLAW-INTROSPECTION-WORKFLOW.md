# OpenClaw Introspection Workflow

Use this as the default end-to-end workflow for evaluating or improving an OpenClaw setup, runtime, plugin, or external repo.

## When to use this workflow

Use it when the user is not asking for just one narrow answer, but wants a fuller picture like:
- "Should I use this repo with OpenClaw?"
- "What does my setup actually do?"
- "What is risky here?"
- "What should I improve next?"

## Step 1 — Understand the thing
Use:
- `runtime-surface-inspector`

Goal:
- identify the runtime shape
- understand overlap with OpenClaw
- decide whether the thing should be borrowed, wrapped, isolated, or avoided

Example question:
- "Do a fit check for OpenClaw on this repo."

## Step 2 — Inventory what exists
Use:
- `tool-manifest-generator`

Goal:
- list tools, commands, skills, sessions, and integrations
- produce a compact capability report
- show what the runtime can actually do right now

Example question:
- "Give me a capability report for this setup."

## Step 3 — Explain the risk posture
Use:
- `permission-risk-summarizer`

Goal:
- separate safe/internal from approval-gated and external/risky
- explain security warnings in plain language
- identify the first hardening move

Example question:
- "What is risky here, and what should I harden first?"

## Step 4 — Turn it into action
Use:
- `runtime-improvement-planner`

Goal:
- prioritize improvements
- decide what to do now vs later
- avoid low-value busywork

Example question:
- "Given all that, what should I improve next?"

## Minimal version

If the user wants speed over completeness:

- fit question → `runtime-surface-inspector`
- inventory question → `tool-manifest-generator`
- safety question → `permission-risk-summarizer`
- action plan question → `runtime-improvement-planner`

## Full example sequence

A realistic conversation could go like this:

1. "Do a fit check for OpenClaw on this repo."
2. "Now give me a capability report for my setup."
3. "What is risky here, and what requires approval?"
4. "Okay, what should I improve next?"

That sequence maps cleanly to the four skills without forcing one skill to do everything.

## Anti-pattern

Do not start with the full workflow if the user clearly wants one narrow answer.

Examples:
- if they only ask "what is risky here?" use the risk skill
- if they only ask "what tools do I have?" use the manifest skill
- if they only ask "does this fit OpenClaw?" use the surface inspector

Use the full workflow only when the task genuinely calls for it.
