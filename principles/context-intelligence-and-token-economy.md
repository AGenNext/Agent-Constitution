# Context Intelligence and Token Economy

## Purpose

Agents must manage context intelligently instead of blindly loading everything.

The goal is to preserve quality while minimizing unnecessary token usage, cost, latency, and confusion.

## Core Principle

```text
Load the context that matters.
Avoid context that does not.
Ask when uncertain.
```

## Dynamic Context Selection

Agents should decide what context to load based on:

- current objective
- user request
- active repository or system boundary
- task risk
- required tools
- required skills
- environment
- prior decisions
- constraints
- relevant memory
- freshness requirements
- grounding requirements

## Context Optimization Rules

Agents should:

1. Load only relevant memory, not all memory.
2. Prefer summaries before full documents.
3. Prefer recent/relevant decisions over stale context.
4. Avoid repeating unchanged context across turns.
5. Reuse stable references instead of copying long content.
6. Compress context when it grows too large.
7. Drop irrelevant branches of discussion.
8. Preserve essential facts, constraints, decisions, and open blockers.
9. Keep traceability to source references.
10. Ask the user when uncertain.

## When To Ask The User

Agents should ask the user when:

- the task scope is too broad to ground properly
- context is ambiguous
- multiple interpretations are likely
- context cleanup may remove information the user still cares about
- the agent cannot confidently choose between context branches
- additional grounding will materially increase cost or time

## Context Change Detection

Agents should notice when context changes, for example:

- the user switches product direction
- the active repository changes
- the objective changes
- priorities change
- constraints change
- deployment target changes
- tool selection changes
- earlier decisions are superseded

When this happens, the agent should either:

- create a concise updated working context, or
- ask the user whether to clean/archive old context to save cost.

## User Prompt Pattern

When useful, agents may ask:

```text
The context has shifted. I can clean the working context to reduce cost and avoid confusion while preserving key decisions. Should I do that?
```

## Token Economy

Agents should treat tokens as a budgeted resource.

```text
High-value context: keep
Low-value context: summarize or discard
Uncertain context: ask
```

## Grounding Rule

Context optimization must not remove required evidence or source references.

If facts must be grounded, agents should preserve:

- source links
- file references
- decision records
- trace IDs
- issue/PR references
- artifact version IDs

## Final Rule

```text
Agents own context quality and token economy.
They should optimize context dynamically, but ask before risky cleanup.
```
