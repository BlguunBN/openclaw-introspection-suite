# OpenClaw Improvement Patterns

Use this file when recommending improvements for OpenClaw setups.

## High-value improvement categories

### 1. Tighten broad trust first
Examples:
- reduce overly permissive exec settings
- clarify approval boundaries
- isolate shared-user or risky surfaces

Why it often wins:
- meaningful safety gain
- preserves long-term trust in the setup

### 2. Add explanation layers before adding more power
Examples:
- capability report
- permission-risk summary
- routing explanation

Why it often wins:
- helps the user understand what already exists
- reduces mis-use and confusion
- usually cheaper than adding new capabilities

### 3. Consolidate overlap
Examples:
- merge adjacent skills
- tighten triggers
- remove duplicate reporting paths

Why it often wins:
- lowers token waste
- reduces cognitive overhead
- improves predictability

### 4. Prefer helper boundaries over runtime fusion
Examples:
- wrap an external repo as a helper
- use ACP isolation instead of importing a second orchestrator

Why it often wins:
- simpler trust model
- easier debugging
- less duplication

### 5. Improve the default path
Examples:
- make the safest common action the easiest one
- make the cheapest useful workflow the obvious one

Why it often wins:
- behavior improves without needing constant user reminders

## Usually lower-value improvements

- adding another adjacent analysis skill without a clear new gap
- importing a parallel runtime for novelty
- building exhaustive manifests nobody will read
- polishing wording before fixing the real trust or workflow issue
