# Manifest Sections

Use this file when deciding what to include and in what order.

## Core sections

### 1. Tools
Include:
- first-class tools
- major helper scripts only if they matter operationally
- whether they read, write, execute, message, fetch web data, or inspect memory

Good questions to answer:
- Which tools do real work?
- Which tools are risky?
- Which tools are redundant?

### 2. Commands
Include:
- user-facing commands
- subcommands with meaningful operational impact
- command groups that define runtime shape

Do not dump every command unless the user explicitly wants exhaustive output.

### 3. Skills
Include:
- skill names
- what they are for
- which ones are likely relevant to the user's task
- obvious overlap between skills

### 4. Sessions and runtime
Include:
- active session shape if known
- sub-agent/ACP availability if relevant
- heartbeat/runtime characteristics if relevant

### 5. Permissions and risk
Include:
- approval-gated actions
- external-write capability
- exec/web/file access considerations
- security warnings that change how the runtime should be used

### 6. Integrations
Include:
- messaging channels
- external APIs/services
- plugin surfaces
- remote runtimes only if materially relevant

## Prioritization

Use this order unless the user wants something else:
1. tools
2. permissions/risk
3. skills
4. sessions/runtime
5. commands
6. integrations

Reason: this is usually the fastest path to practical understanding.

## Compression rules

When the manifest gets too long:
- group similar tools together
- summarize low-value command noise
- list only the most relevant skills
- collapse obvious internal plumbing

Avoid exhaustive dumps unless the user clearly asked for one.
