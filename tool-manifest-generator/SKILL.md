---
name: tool-manifest-generator
description: Generate a compact manifest of tools, commands, skills, sessions, integrations, and practical capabilities for an OpenClaw workspace, runtime, repo, plugin, skill pack, or assistant setup. Use when the user asks for a capability report, tool inventory, command list, runtime summary, session snapshot, onboarding summary, or a clean explanation of what an agent/runtime can do right now. Trigger on requests like "generate a tool manifest", "what tools do I have", "what can my setup do", "show commands/tools/skills", "give me a capability report", or "summarize this runtime". Do not use for architecture fit checks, integration judgments, raw permission/risk analysis, roadmap planning, generic code review, bug fixing, or implementation work unless the main task is producing a manifest or capability summary.
---

# Tool Manifest Generator

Produce a clean, compact capability report for OpenClaw-adjacent systems.

## Goal

Turn a messy runtime, repo, or workspace into a readable manifest that answers:
- what exists?
- what executes real work?
- what is risky or approval-gated?
- what overlaps or duplicates?
- what matters to the user right now?

## Workflow

1. Identify scope.
   - OpenClaw runtime
   - local workspace
   - repo
   - plugin
   - skill pack
   - external tool/harness

2. Gather only high-signal evidence.
   - entrypoints
   - tool/command registries
   - skill folders and SKILL.md files
   - permission/security config
   - runtime/session status
   - docs only when needed for orientation

3. Build the manifest.
   - tools
   - commands
   - skills
   - sessions/runtime
   - permissions/risk
   - integrations
   - notable gaps or overlaps

4. Separate evidence types.
   - **executable**: code or runtime status that performs work
   - **declarative**: config, manifests, frontmatter, inventories
   - **narrative**: README/docs claims

5. Summarize for the actual user need.
   - inventory
   - risk view
   - overlap view
   - quick onboarding view
   - OpenClaw-specific capability report

## Output format

Default to this structure unless the user asks for a different one.

### Manifest summary
One short paragraph.

### Capability table
Use bullets, not markdown tables, on chat surfaces.
- tools:
- commands:
- skills:
- sessions/runtime:
- permissions/risk:
- integrations:

### Evidence quality
- executable:
- declarative:
- narrative:

### Notable overlaps or gaps
List only the things that matter.

### Recommendation
Give the next best action.

## OpenClaw-specific guidance

When the target is OpenClaw or an OpenClaw workspace, prefer checking:
- current runtime/session state via `openclaw status`
- workspace skills and SKILL.md frontmatter
- known tool availability from the runtime
- security/approval warnings that affect real use

Do not guess capability if runtime evidence is available.

## When to read references

Read these only when useful:
- `references/manifest-sections.md` for section design and prioritization
- `references/openclaw-manifest-patterns.md` for OpenClaw-specific output patterns
- `references/output-examples.md` for ready-made response shapes

## Heuristics

- Prefer small, accurate manifests over giant exhaustive dumps.
- Highlight what is actionable now.
- Separate what exists from what is safe to use.
- Call out duplicated surfaces instead of listing them passively.
- Optimize for clarity, not completeness theater.
