# Patterns Worth Stealing

Use this file after a fit-check identifies reusable ideas.

## High-value patterns for OpenClaw-inspired reuse

### 1. Capability manifest
A machine-readable or human-readable summary of:
- commands
- tools
- permissions
- sessions
- integrations

Useful for debugging, onboarding, and explaining the system to users.

### 2. Searchable tool inventory
A compact way to answer:
- what tools exist?
- which ones can write externally?
- which ones are safe/internal?
- which ones overlap?

Useful when a runtime grows beyond a small tool count.

### 3. Routing explanation layer
Instead of only choosing a path, explain briefly why a tool/skill/runtime path was chosen.

Useful for trust and debugging.

### 4. Permission-context summary
A way to summarize what is allowed, denied, approval-gated, or risky.

Useful for safety and reducing user confusion.

### 5. Surface map report
A repeatable report that answers:
- what does this thing really do?
- what is metadata only?
- what is executable?
- what overlaps with the host runtime?

Useful for evaluating repos, plugins, and experimental harnesses.

## Medium-value patterns

### Shim execution layer
A fake or mirrored command/tool layer can be useful for introspection, docs, or migration planning.

It is less useful for actual execution unless it is backed by real behavior.

### Parity audit
Helpful when porting from one runtime/language to another.

Useful only if the audit is tied to operational goals, not just inventory matching.

## Usually not worth stealing into OpenClaw

### Alternate turn loop
OpenClaw already owns the main interaction loop.

### Alternate session manager
Only useful if fully isolated as an ACP or helper runtime.

### Alternate approval model
OpenClaw already has security and approval semantics; duplicating them usually adds confusion.
