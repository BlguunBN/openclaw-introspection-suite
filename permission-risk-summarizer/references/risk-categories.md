# Risk Categories

Use this file when you need a consistent way to classify actions and surfaces.

## Categories

### Safe/internal
Usually includes:
- local reads
- local search
- status inspection
- non-destructive workspace inspection
- memory lookup without external sharing

These are typically safe because they do not change outside state.

### Approval-gated
Usually includes:
- file writes with meaningful impact
- destructive edits
- package installation
- long-running or elevated shell commands
- actions with uncertain consequences
- sending messages or content externally when not already explicitly requested

These are not necessarily dangerous, but they should involve user intent.

### External or risky
Usually includes:
- broad shell execution trust
- public or third-party messaging/posting
- remote execution surfaces
- broad file write/delete powers
- web actions that authenticate or mutate external state
- multi-user access to a personal-assistant runtime

These deserve explicit explanation even if they are intentional.

### Unclear
Use when:
- docs make claims that runtime evidence does not confirm
- policy is implied but not visible
- a plugin or harness adds behavior that is hard to verify

## Severity hints

Use plain language instead of fake precision.

- **low concern**: useful, mostly internal, low blast radius
- **needs care**: reasonable but should stay approval-gated
- **material risk**: can change outside state or bypass intended oversight
- **high concern**: broad trust, multi-user leakage risk, or difficult-to-audit external effects

## Common mistakes

### Everything-is-risky mode
Do not label all capabilities as dangerous. That makes the report useless.

### Everything-is-fine mode
Do not downplay broad exec trust, external messaging, or multi-user concerns.

### Confusing capability with policy
A tool existing is not the same as it being safe by default. Separate availability from default use policy.
