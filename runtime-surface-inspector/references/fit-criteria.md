# Fit Criteria

Use this file when you need a more systematic OpenClaw fit assessment.

## Scoring dimensions

Score each from 1-10 if the user wants a numeric assessment.

### 1. Runtime overlap
How much does the target duplicate OpenClaw core responsibilities?

- 1-3: mostly complements OpenClaw
- 4-6: some overlap, manageable with wrapping
- 7-10: strongly duplicates orchestration, sessions, routing, permissions, or tool execution

High overlap is usually bad.

### 2. Extraction value
How valuable are the reusable ideas, patterns, or components?

- 1-3: little worth reusing
- 4-6: some useful patterns
- 7-10: strong source of ideas, utilities, or abstractions

High extraction value is good.

### 3. Integration friction
How hard would it be to make this useful inside OpenClaw?

Consider:
- language/runtime mismatch
- approval/security mismatch
- session/state mismatch
- deployment complexity
- maintenance burden

High friction is bad.

### 4. Assistant alignment
How well does the target support personal-assistant workflows versus coding-harness workflows?

Consider:
- messaging orientation
- memory/continuity model
- approval-aware actions
- human-facing UX
- multi-channel behavior

High alignment is good.

## Decision rules

### Borrow pattern
Choose when:
- extraction value is high
- runtime overlap is medium or high
- direct integration would be messy

This is the most common result.

### Wrap as helper
Choose when:
- the target does one narrow thing well
- it can stay isolated behind one tool or script boundary
- OpenClaw remains the orchestrator

### Port a narrow slice
Choose when:
- one component is clearly valuable
- the component can be rewritten or adapted cleanly
- importing the whole runtime would be overkill

### Do not integrate
Choose when:
- overlap is high
- friction is high
- assistant alignment is low
- the best parts are conceptual rather than operational

## Common anti-patterns

### Parallel orchestrator
A second turn loop or bootstrap runtime inside OpenClaw.

Usually a bad idea because it creates:
- unclear authority
- duplicated state
- harder debugging
- extra token spend
- awkward permissions

### Metadata theater
A repo exposes beautiful manifests, indexes, or parity claims, but little real execution capability.

Treat as research or inspiration unless executable evidence says otherwise.

### False fit from adjacent vocabulary
A project may talk about tools, sessions, runtime, or routing and still not fit OpenClaw well.

Shared words do not imply shared architecture.
