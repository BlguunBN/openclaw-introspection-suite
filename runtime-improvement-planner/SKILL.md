---
name: runtime-improvement-planner
description: Turn runtime, capability, and risk findings into a prioritized improvement plan for an OpenClaw workspace, runtime, repo, plugin, skill pack, or assistant setup. Use when the user asks what to improve next, what to fix first, what is the highest-leverage change, how to prioritize setup improvements, what is worth doing now versus later, or what roadmap makes sense. Trigger on requests like "what should I improve next", "what should I fix first", "prioritize improvements", "give me a next-step plan", "what is the highest-leverage change", "what should I do now vs later", or "turn this analysis into an action plan". Do not use for generic manifests, architecture fit checks, raw permission/risk summaries, generic capability summaries, code review, bug fixing, or implementation work unless the main task is prioritizing improvements.
---

# Runtime Improvement Planner

Convert runtime observations into an action plan instead of stopping at analysis.

## Goal

Answer the questions that matter after inspection:
- what should be changed first?
- what gives the biggest payoff for the least effort?
- what improves safety without killing usefulness?
- what reduces token waste?
- what is interesting but not worth doing now?

## Workflow

1. Gather findings.
   - runtime/capability summary
   - fit/integration findings
   - permission/risk findings
   - known user goals and preferences

2. Identify candidate improvements.
   - hardening changes
   - capability/reporting improvements
   - skill cleanup or consolidation
   - workflow simplifications
   - cost/token-efficiency improvements
   - integration or isolation decisions

3. Score each candidate.
   - **user value**: how much it improves day-to-day usefulness
   - **safety gain**: how much risk it reduces
   - **effort**: how hard it is to implement and maintain
   - **token efficiency**: whether it reduces wasted analysis or repeated work
   - **complexity cost**: whether it adds cognitive or runtime overhead

4. Sort into action buckets.
   - **do now**
   - **do next**
   - **nice to have**
   - **not worth it right now**

5. Recommend one best next move.
   - Give the single highest-leverage step first.
   - Then list 2-4 follow-ups only if useful.

## Output format

Default to this structure unless the user wants something shorter.

### Best next move
One short paragraph with the top recommendation and why it wins.

### Do now
- highest-leverage actions

### Do next
- valuable but not first-priority actions

### Nice to have
- good ideas with lower immediate payoff

### Not worth it right now
- tempting but low-leverage or duplicative work

### Tradeoffs
- safety vs usefulness
- effort vs payoff
- token cost vs clarity

## OpenClaw-specific guidance

For OpenClaw, optimize around:
- practical usefulness
- clear approval boundaries
- avoiding duplicate/overlapping skills
- reducing token waste
- keeping runtime behavior understandable

Prefer fewer better skills over many adjacent ones.
Prefer one high-value hardening change over a pile of minor tweaks.

## When to read references

Read these only when useful:
- `references/prioritization-rules.md` for scoring heuristics
- `references/openclaw-improvement-patterns.md` for common high-value improvements
- `references/output-examples.md` for concise planning formats

## Heuristics

- Recommend the smallest change that produces a meaningful improvement.
- Penalize ideas that mostly add surface area.
- If an idea is clever but low leverage, put it in "not worth it right now".
- Reflect Bilguuntugs-style priorities: concise, practical, low waste, clear tradeoffs.
- When in doubt, choose the option that keeps the system simpler and safer.
