---
name: runtime-surface-inspector
description: Inspect, summarize, and compare the architecture and execution surface of a repo, CLI, agent harness, plugin, skill, or assistant runtime. Use when the user asks for an OpenClaw fit check, runtime or repo architecture breakdown, overlap mapping, integration assessment, or whether to borrow, wrap, port, isolate, or avoid another runtime. Trigger on requests like "fit check for OpenClaw", "how does this repo/runtime work", "what overlaps with OpenClaw", "should I integrate this repo/plugin/skill", or "does this duplicate OpenClaw". Do not use for generic capability inventories, raw permission/risk summaries, roadmap planning, ordinary code review, bug fixing, or feature implementation unless the main task is architecture/fit analysis.
---

# Runtime Surface Inspector

Map a system's real execution surface, then compare it against OpenClaw without hand-waving.

## Core rule

Prefer **behavior-defining files** over narrative claims.

Start with:
- README only for orientation
- then entrypoints, command registries, tool registries, session/runtime code, permission code, and tests

Do not assume "parity", "port", or "clean-room" claims are true unless executable code supports them.

## Workflow

1. Identify the target type.
   - Repo
   - CLI tool
   - assistant runtime
   - coding harness
   - OpenClaw workspace/plugin/skill

2. Read the smallest high-signal file set.
   - Start with the main entrypoint.
   - Then inspect only the files that define command dispatch, tool execution, session/state, permissions, routing, and memory.
   - Read extra files only if a core area is still unclear.

3. Build the surface map.
   - commands
   - tools
   - sessions/state
   - permissions
   - memory
   - routing/bootstrap
   - external integrations

4. Classify each area.
   - **native-fit**: maps directly onto OpenClaw concepts
   - **adaptable**: useful with wrapping or refactoring
   - **duplicate-runtime**: overlaps with OpenClaw core runtime; avoid importing wholesale
   - **research-only**: interesting but low practical value

5. Compare against OpenClaw.
   - Check whether OpenClaw already provides the capability via tools, skills, sessions, ACP, memory, heartbeat, or gateway/runtime features.
   - Call out duplication explicitly.

6. Recommend one outcome.
   - **borrow pattern**
   - **wrap as helper**
   - **port a narrow slice**
   - **do not integrate**

## Output format

Default to this shape unless the user wants something shorter.

### Verdict
One short paragraph with the actual conclusion.

### Surface map
- commands:
- tools:
- sessions/state:
- permissions:
- memory:
- routing/bootstrap:
- external integrations:

### OpenClaw fit
- native-fit:
- adaptable:
- duplicate-runtime:
- research-only:

### Best extraction opportunities
List 3-5 concrete ideas worth reusing.

### Recommendation
State the highest-leverage next step.

## OpenClaw grounding

When comparing, ground against real OpenClaw concepts:
- first-class tools
- SKILL.md-driven skills
- direct sessions and sub-agents
- ACP harness sessions
- memory retrieval
- heartbeat behavior
- gateway/runtime status
- approval and security boundaries

If the current OpenClaw runtime shape matters, run `openclaw status` instead of guessing.

## When to read references

Read these only when needed:
- `references/fit-criteria.md` for scoring and decision rules
- `references/patterns-worth-stealing.md` when turning findings into concrete reuse ideas
- `references/output-examples.md` when the user wants a polished fit-check or architecture comparison

## Heuristics

- Prefer executable evidence over repo storytelling.
- A mirrored inventory is weaker evidence than code that actually performs work.
- A second orchestrator inside OpenClaw is usually a bad integration idea.
- Optimize for Bilguuntugs-style output: concise, practical, low fluff, clear tradeoffs.
