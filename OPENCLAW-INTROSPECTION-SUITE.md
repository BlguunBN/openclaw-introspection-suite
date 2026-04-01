# OpenClaw Introspection Suite

A small skill family for understanding, auditing, and improving OpenClaw-style runtimes without collapsing everything into one vague mega-skill.

## Skills in the suite

### 1. `runtime-surface-inspector`
Use for:
- fit checks
- architecture breakdowns
- overlap mapping
- integration judgment

Core question:
- **What is this thing, and how does it fit or conflict with OpenClaw?**

### 2. `tool-manifest-generator`
Use for:
- capability reports
- tool/command/skill inventories
- runtime summaries
- onboarding snapshots

Core question:
- **What exists here, and what can it do right now?**

### 3. `permission-risk-summarizer`
Use for:
- permission summaries
- approval boundaries
- trust-boundary explanations
- security warning interpretation
- hardening-first guidance

Core question:
- **What is risky here, what needs approval, and what should be tightened first?**

### 4. `runtime-improvement-planner`
Use for:
- next-step plans
- prioritization
- now-vs-later decisions
- highest-leverage change selection

Core question:
- **What should be improved next, and in what order?**

## Recommended flow

When doing a full pass on a runtime or repo:

1. `runtime-surface-inspector`
2. `tool-manifest-generator`
3. `permission-risk-summarizer`
4. `runtime-improvement-planner`

This gives a clean sequence:
- understand
- inventory
- assess risk
- decide what to do next

## Why these stay separate

They are adjacent on purpose, but each one owns a different job:
- **inspector** = fit and architecture judgment
- **manifest** = inventory and capability summary
- **risk** = permissions and trust posture
- **planner** = prioritized action plan

Merging them too early would make trigger quality worse and outputs blur together.

## Trigger reference

See:
- `skills/TRIGGER-TEST-MATRIX.md`

Use that file when refining frontmatter or auditing false positives/false negatives.
