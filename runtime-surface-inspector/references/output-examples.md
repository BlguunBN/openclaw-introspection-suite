# Output Examples

## Example 1 — Short fit check

### Verdict
Good inspiration source, weak direct integration base. Best used as a parts bin for manifests and capability mapping, not as a second runtime inside OpenClaw.

### Surface map
- commands: rich CLI surface with summary and inspection commands
- tools: registry/inventory style, partly metadata-driven
- sessions/state: present, but oriented around its own runtime
- permissions: some filtering concepts
- memory: limited or runtime-specific
- routing/bootstrap: strong emphasis on internal orchestration
- external integrations: depends on repo

### OpenClaw fit
- native-fit: manifest/reporting ideas
- adaptable: tool inventory, permission summaries
- duplicate-runtime: turn loop, session orchestration, bootstrap
- research-only: parity claims without execution depth

### Best extraction opportunities
- capability manifest
- searchable tool inventory
- routing explanation layer

### Recommendation
Port only the reporting/introspection slice.

---

## Example 2 — OpenClaw-focused comparison

### Verdict
This repo overlaps heavily with OpenClaw's runtime responsibilities, so direct integration would create duplicate orchestration. The valuable part is its inspection and inventory mindset, which can be repurposed into OpenClaw-friendly reporting tools.

### Surface map
- commands: entrypoint-centered CLI dispatch
- tools: lookup/filter/index pattern
- sessions/state: maintained inside its own runtime model
- permissions: lightweight tool gating
- memory: not a strong differentiator
- routing/bootstrap: central to the project
- external integrations: secondary

### OpenClaw fit
- native-fit:
  - capability summaries
  - command/tool catalogs
- adaptable:
  - permission-context reporting
  - architecture inspection helpers
- duplicate-runtime:
  - bootstrap logic
  - turn loop
  - local runtime session ownership
- research-only:
  - snapshot parity without equivalent execution depth

### Best extraction opportunities
- a `tool-manifest` report for OpenClaw
- a skill/tool overlap explainer
- a lightweight routing summary command
- a permission-risk report

### Recommendation
Borrow patterns; do not import the runtime core.

---

## Example 3 — Repo audit framing

Use this tone when the user wants blunt practical guidance:

"Treat this as architecture material, not a product. The best bits are the inventory and introspection ideas. The moment it starts trying to own the turn loop, session model, or tool execution semantics, it stops fitting OpenClaw cleanly."