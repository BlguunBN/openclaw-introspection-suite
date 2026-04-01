# Trigger Test Matrix

Use this file to sanity-check trigger quality for the four OpenClaw introspection skills.

## Skills covered
- `runtime-surface-inspector`
- `tool-manifest-generator`
- `permission-risk-summarizer`
- `runtime-improvement-planner`

---

# 1. runtime-surface-inspector

## Should fire

- "Do a fit check for OpenClaw on this repo."
- "How does this repo/runtime work internally?"
- "Map its tools, commands, sessions, and permissions."
- "What overlaps with OpenClaw here?"
- "Should I integrate this plugin into OpenClaw or keep it isolated?"
- "Compare this harness architecture against OpenClaw."
- "Break down this runtime surface and tell me if it duplicates OpenClaw."
- "Should I borrow, wrap, port, or avoid this repo?"

## Should not fire

- "What tools do I have right now in OpenClaw?"
- "Give me a capability report for my setup."
- "Summarize the risk posture of my runtime."
- "What should I improve next in my setup?"
- "Fix this bug in the repo."
- "Implement a new command in this CLI."
- "Review this code for correctness."

## Borderline

- "Summarize this runtime."
  - Prefer `tool-manifest-generator` if the user wants inventory/capabilities.
  - Prefer `runtime-surface-inspector` if the user wants architecture/overlap analysis.

- "Explain this repo to me."
  - Use this skill if the explanation is architecture/runtime-focused.

---

# 2. tool-manifest-generator

## Should fire

- "Generate a tool manifest for my OpenClaw setup."
- "What tools and capabilities do I have?"
- "What can my setup do right now?"
- "Show commands, tools, skills, and sessions."
- "Give me a capability report for this runtime."
- "Summarize this runtime in a practical way."
- "Create a clean inventory of this repo's commands and tools."
- "Give me an onboarding summary of this assistant setup."

## Should not fire

- "Does this repo fit OpenClaw?"
- "What overlaps with OpenClaw architecture here?"
- "Should I integrate or avoid this runtime?"
- "What is risky here?"
- "What requires approval?"
- "What should I improve next?"
- "Audit the security posture of this setup."
- "Fix this shell command bug."

## Borderline

- "Map this runtime surface."
  - Prefer this skill if the user wants a capability inventory.
  - Prefer `runtime-surface-inspector` if the user wants fit/overlap judgment.

- "Show me what exists in this setup."
  - Usually this skill.

---

# 3. permission-risk-summarizer

## Should fire

- "Summarize the permission and risk posture of my OpenClaw setup."
- "What is risky here?"
- "What can auto-execute?"
- "What requires approval?"
- "Explain these security warnings."
- "Is this setup safe enough for normal use?"
- "What should I harden first?"
- "Tell me what is safe/internal versus external or risky."
- "Audit the risk of this plugin/runtime."

## Should not fire

- "What tools do I have?"
- "Generate a capability report."
- "Summarize the runtime surface."
- "Does this repo fit OpenClaw?"
- "What overlaps with OpenClaw architecture?"
- "What should I improve next?"
- "Implement approval handling in this codebase."
- "Review this code for security bugs."

## Borderline

- "What can this setup do without asking?"
  - Prefer this skill if the user is asking about autonomy/approval boundaries.
  - Prefer `tool-manifest-generator` if they mainly want a capability inventory.

- "How dangerous is this repo/runtime?"
  - Use this skill if the focus is trust boundaries and risk.

---

# 4. runtime-improvement-planner

## Should fire

- "What should I improve next in my OpenClaw setup?"
- "What should I fix first?"
- "Prioritize improvements for safety and usefulness."
- "Give me a next-step plan."
- "What is the highest-leverage change?"
- "What should I do now versus later?"
- "Turn this analysis into an action plan."
- "Give me a roadmap for improving this setup."
- "What is worth doing now, and what is not worth it yet?"

## Should not fire

- "What tools do I have?"
- "Generate a capability report."
- "What is risky here?"
- "What requires approval?"
- "Does this repo fit OpenClaw?"
- "How does this runtime work internally?"
- "Fix this bug in the repo."
- "Implement this feature."

## Borderline

- "What should I harden first?"
  - Prefer `permission-risk-summarizer` if the question is mainly about safety posture.
  - Prefer this skill if the user wants a prioritized plan across safety, usefulness, and effort.

- "What should I do with this repo/runtime?"
  - Prefer `runtime-surface-inspector` if the choice is integrate vs isolate.
  - Prefer this skill if the user wants a staged action plan after that judgment.

---

# Conflict resolution rules

If two skills seem plausible, prefer based on the user's real intent:

1. **Fit / overlap / integrate?**
   - `runtime-surface-inspector`

2. **What exists / what can it do / give me a report?**
   - `tool-manifest-generator`

3. **What is risky / what needs approval / what should I harden?**
   - `permission-risk-summarizer`

4. **What should I change next / what is highest leverage / what is worth doing now?**
   - `runtime-improvement-planner`

## Fast keyword guide

- **fit, overlap, integrate, borrow, wrap, port, avoid**
  - `runtime-surface-inspector`

- **manifest, capability, inventory, what tools, what can it do, runtime summary**
  - `tool-manifest-generator`

- **risky, approval, auto-execute, safe, dangerous, harden, security warnings**
  - `permission-risk-summarizer`

- **improve next, fix first, roadmap, prioritize, next-step plan, highest leverage, now vs later**
  - `runtime-improvement-planner`

## Anti-patterns

Avoid firing any of these skills for:
- routine code review
- bug fixing
- feature implementation
- generic repo explanation with no runtime/capability/risk/planning angle

---

# Recommended next use

Use this matrix whenever you refine frontmatter descriptions or notice false-positive / false-negative skill activation.