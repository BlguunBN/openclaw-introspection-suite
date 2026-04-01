# OpenClaw Risk Patterns

Use this file when the target is OpenClaw.

## Common patterns to call out

### 1. Broad exec trust
If exec security is broad or full, say plainly:
- shell execution is available with wide trust
- this increases blast radius if used carelessly
- the first tightening move is usually narrowing exec policy or approvals

### 2. External messaging surfaces
If Telegram, Discord, email, or similar channels are active, note:
- the runtime can communicate externally
- this is useful, but it means message-sending behavior matters
- user approval boundaries should stay clear

### 3. Multi-user or trust-boundary warnings
If the runtime may be reachable by multiple users:
- call out privacy leakage risk
- distinguish a personal assistant setup from a shared runtime
- recommend isolation if users may be mutually untrusted

### 4. Plugin compatibility/security warnings
Translate these into operational meaning.

Bad: "plugin compatibility notice present"

Better: "a plugin is using a compatibility path that still works, but it is not the cleanest or most explicit capability model. That is more of a maintenance/trust concern than an immediate emergency."

### 5. Reverse proxy or exposure warnings
If a control UI or gateway could be exposed indirectly:
- explain whether the current bind is local-only or not
- clarify that a local bind is safer than public exposure
- mention trusted proxy configuration only if it materially matters

## Good recommendation pattern

1. first practical hardening step
2. second optional improvement
3. what not to overreact to

Example:
- first fix: narrow exec trust
- second fix: tighten multi-user isolation if the runtime may be shared
- do not overreact to: a compatibility-path plugin warning unless it combines with broader trust issues
