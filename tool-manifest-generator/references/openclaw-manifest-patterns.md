# OpenClaw Manifest Patterns

Use this file when the target is OpenClaw or an OpenClaw workspace.

## Recommended manifest angles

### 1. Practical capability report
Best when the user asks:
- what can my setup do?
- what tools do I have?
- how should I use this efficiently?

Focus on:
- available tools
- approval boundaries
- active channels
- current session/runtime shape
- skills likely to matter

### 2. Risk-aware manifest
Best when the user asks:
- what is dangerous here?
- what can auto-execute?
- what requires approval?

Focus on:
- exec level
- external messaging capability
- file write scope
- web access
- plugin warnings
- multi-user/trust-boundary warnings

### 3. Builder manifest
Best when the user asks:
- how do I extend this?
- what should I add next?
- how do skills/tools fit together?

Focus on:
- current skills
- missing skills
- tool overlap
- where helper scripts or ACP sessions make sense

## Recommended language

Prefer:
- "available now"
- "approval-gated"
- "safe/internal"
- "external or risky"
- "likely useful"
- "probably duplicate"

Avoid vague labels like:
- "powerful"
- "comprehensive"
- "advanced"

## Good output pattern

### Manifest summary
Two or three sentences max.

### What you can do now
- internal reads/search/status
- code/file edits
- external web research
- messaging/session orchestration
- ACP/sub-agent workflows

### What needs care
- exec with broad trust
- external actions
- overlapping or duplicate skills
- anything that increases token waste

### Best next move
One concrete recommendation.
