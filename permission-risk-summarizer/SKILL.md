---
name: permission-risk-summarizer
description: Summarize permissions, approvals, trust boundaries, risky capabilities, security warnings, and hardening priorities for an OpenClaw workspace, runtime, repo, plugin, skill pack, or assistant setup. Use when the user asks what is risky, what can auto-execute, what requires approval, what is safe/internal versus external, how dangerous a setup is, why a security warning matters, or what should be hardened first. Trigger on requests like "summarize permissions", "what is risky here", "what can auto-execute", "what requires approval", "audit the risk", "explain the security warnings", "is this setup safe", or "what should I harden first". Do not use for generic capability manifests, runtime inventories, architecture fit checks, broader improvement roadmaps, code review, bug fixing, or implementation work unless the main task is permission/risk analysis.
---

# Permission Risk Summarizer

Produce a practical risk summary for an agent/runtime without drowning the user in raw audit noise.

## Goal

Answer the questions users actually care about:
- what can this setup do without asking?
- what can affect the outside world?
- what can write, execute, or message externally?
- what trust assumptions exist?
- what should be tightened first?

## Workflow

1. Identify the target.
   - OpenClaw runtime
   - workspace
   - repo
   - plugin
   - skill pack
   - external harness/tool

2. Gather high-signal risk evidence.
   - runtime status and security audit output
   - tool availability and write/exec capabilities
   - channel/integration surfaces
   - session/sub-agent/ACP execution paths
   - config or docs only when they change the real risk posture

3. Classify capabilities.
   - **safe/internal**: read-only or low-risk internal actions
   - **approval-gated**: actions that should require explicit user consent
   - **external or risky**: messaging, exec, web writes, broad file writes, multi-user exposure
   - **unclear**: claims not backed by runtime evidence

4. Summarize trust boundaries.
   - single-user vs multi-user concerns
   - local-only vs externally reachable surfaces
   - plugin compatibility or policy warnings
   - broad trust settings like permissive exec

5. Recommend the minimum useful tightening.
   - reduce broad trust
   - harden approvals
   - limit external actions
   - isolate risky runtimes
   - keep the useful parts

## Output format

Default to this structure unless the user wants something shorter.

### Risk summary
One short paragraph.

### Safe/internal
- items that are low-risk and useful

### Approval-gated
- items that should involve explicit consent

### External or risky
- items that can affect the outside world or materially increase risk

### Trust-boundary notes
- local-only vs exposed
- multi-user concerns
- plugin or policy warnings

### Best next hardening step
Give one concrete recommendation first, then optional follow-ups.

## OpenClaw-specific guidance

When analyzing OpenClaw, prefer checking:
- `openclaw status`
- security audit warnings
- exec trust level
- channel/message surfaces
- session/sub-agent/ACP availability
- file/workspace scope

Translate raw warnings into plain language. Do not just repeat audit text.

## When to read references

Read these only when useful:
- `references/risk-categories.md` for classification rules
- `references/openclaw-risk-patterns.md` for common OpenClaw warning patterns
- `references/output-examples.md` for concise reporting styles

## Heuristics

- Optimize for practical caution, not fear-mongering.
- Highlight the first fix that gives the best safety gain per token/effort.
- Distinguish internal reads from external effects.
- Call out when a setup is safe enough for normal use versus risky enough to warrant immediate changes.
- If the setup is intentionally broad-trust, say so plainly instead of pretending it is hardened.
