# Output Examples

## Example 1 — Practical capability report

### Manifest summary
Your setup already has the core OpenClaw surfaces you need: file tools, shell execution, web fetch/search, memory lookup, session orchestration, and Telegram routing. The bottleneck is not missing capability; it's choosing the cheapest safe path for each task.

### Capability table
- tools:
  - file read/write/edit
  - shell exec and process management
  - web search/fetch
  - memory search/get
  - session spawn/send/status
- commands:
  - status and gateway management are the most operationally relevant
- skills:
  - architecture and skill-building helpers available
- sessions/runtime:
  - direct main session active
  - sub-agents available when work gets long
- permissions/risk:
  - exec policy and external actions need the most care
- integrations:
  - Telegram active

### Evidence quality
- executable: runtime status and tool availability
- declarative: skill frontmatter and workspace files
- narrative: docs and guidance files

### Notable overlaps or gaps
- overlap: multiple ways to inspect/runtime-audit things
- gap: no compact capability report by default

### Recommendation
Use this manifest style as the default explanation layer before adding more skills.

---

## Example 2 — Repo manifest

### Manifest summary
This repo exposes a strong inventory surface but a weaker execution surface. It is better at describing a runtime than at replacing one.

### Capability table
- tools:
  - registry/index pattern
- commands:
  - summary, manifest, route, inspection-style commands
- skills:
  - none or not relevant
- sessions/runtime:
  - maintains its own runtime model
- permissions/risk:
  - lightweight filtering only
- integrations:
  - minimal

### Evidence quality
- executable: limited
- declarative: strong
- narrative: strong README claims

### Notable overlaps or gaps
- overlap: manifest/reporting
- gap: production-grade runtime equivalence

### Recommendation
Borrow its manifest ideas; do not treat it as a drop-in runtime.
