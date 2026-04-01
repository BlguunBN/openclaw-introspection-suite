# Output Examples

## Example 1 — OpenClaw risk summary

### Risk summary
Your setup is usable, but not especially hardened. The biggest real issue is broad shell-exec trust; everything else is secondary compared with that.

### Safe/internal
- local file reads and inspection
- runtime status checks
- memory lookup
- internal workspace edits when explicitly requested

### Approval-gated
- meaningful file writes
- package installs
- elevated or uncertain shell commands
- outbound actions not already requested by the user

### External or risky
- shell exec with broad trust
- Telegram as an external messaging surface
- multi-user warning if the runtime is reachable by more than one user

### Trust-boundary notes
- local gateway binding is safer than public exposure
- plugin compatibility notice is more of a maintenance concern than a panic issue

### Best next hardening step
Narrow exec trust first. That gives you the biggest safety improvement without reducing the usefulness of the setup too much.

---

## Example 2 — Repo/plugin risk framing

### Risk summary
This repo mostly describes a runtime rather than safely constraining one. The main risk is not that it is instantly dangerous; it is that it may introduce overlapping execution paths and fuzzy approval boundaries.

### Safe/internal
- metadata inspection
- manifest generation

### Approval-gated
- any imported execution path
- any integration that lets the repo send messages, run commands, or mutate files outside a narrow boundary

### External or risky
- alternate orchestrators
- broad shell hooks
- remote runtime surfaces

### Trust-boundary notes
- if the host runtime already has approvals, importing a second approval model often makes things less clear, not more safe

### Best next hardening step
Keep the repo behind a helper boundary instead of letting it own orchestration.
