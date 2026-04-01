# Output Examples

## Example 1 — OpenClaw next-step plan

### Best next move
Tighten exec trust before adding more capability. It gives the biggest safety improvement per unit of effort and reduces the chance that the rest of the setup becomes harder to trust.

### Do now
- narrow exec trust or approval boundaries
- keep the new introspection skills, since they improve clarity without much runtime overhead

### Do next
- add one default capability/risk report workflow so the setup is easier to inspect on demand
- remove or avoid overlapping analysis surfaces if they start to blur together

### Nice to have
- prettier packaging or naming polish
- additional examples if real usage shows confusion

### Not worth it right now
- another adjacent introspection skill with no new decision-making value

### Tradeoffs
- safety vs usefulness: slightly tighter exec is worth the friction
- effort vs payoff: trust tightening beats cosmetic improvements
- token cost vs clarity: explanation skills are justified because they reduce repeated confusion

---

## Example 2 — Repo/tooling action plan

### Best next move
Keep the external runtime isolated and extract only the reporting ideas you actually need. That preserves OpenClaw as the runtime of record while still letting you borrow useful patterns.

### Do now
- document the 1-3 ideas worth stealing
- reject runtime-fusion ideas

### Do next
- wrap any useful helper behind a narrow boundary

### Nice to have
- revisit if the external project matures operationally

### Not worth it right now
- importing a second orchestrator
