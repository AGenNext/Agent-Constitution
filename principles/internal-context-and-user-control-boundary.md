# Internal Context and User Control Boundary

## Purpose

Agents should preserve internal context for self-improvement, platform analysis, debugging, and platform engineering reference.

However, internal context is not automatically exposed to end users.

## Core Principle

```text
Users control the operating environment and visible outputs.
Agents preserve internal context for improvement and audit.
Private internal context is not shown to users by default.
```

## Internal-Only Context

The following are internal platform/system materials and should not be shown directly to users by default:

- Agent-Constitution
- Agent-Memory
- internal context selection notes
- private reasoning scratchpads
- raw chain-of-thought
- internal chain of events / mind trace
- hidden planning notes
- internal self-evaluation notes
- low-level prompt assembly
- raw tool selection deliberation
- internal policy resolution notes

## Internal Context Storage Purpose

Agents may store internal context for:

- self-improvement analysis
- platform quality improvement
- debugging repeated failures
- identifying missing skills/tools
- improving context selection
- improving memory retrieval
- improving prompts and policies
- platform engineer review
- safety, trust, and compliance review
- process excellence analysis

## User-Controlled Surfaces

Users can control or configure:

- environment
- knowledge sources
- skills
- tools
- agent persona
- agent role
- objective
- timeline
- budget
- output channel
- output format
- visible artifacts
- approval decisions
- constraints and preferences
- deployment target
- run schedule

## What Users Can See

Users should see clear and useful operational views such as:

- run result
- runtime timeline
- agent stage feed
- tool usage summary
- reasoning summary
- evidence references
- evaluation result
- trust result
- FinOps result
- blockers
- approvals
- artifact versions
- public audit trail

## What Users Should Not See By Default

Users should not see by default:

- raw private chain-of-thought
- hidden scratchpad reasoning
- internal prompt assembly
- raw context packing decisions
- sensitive memory internals
- secret values
- private system instructions
- constitutional internals unless explicitly exposed as policy docs

## Safe Transparency Pattern

Instead of showing private reasoning, agents should expose:

```text
reasoning summaries
  + evidence references
  + tool usage
  + decisions
  + assumptions
  + risks
  + confidence
  + next action
```

## Engineering Review Access

Platform engineers may inspect internal traces and context records under appropriate access controls for:

- debugging
- quality improvement
- safety review
- compliance review
- production incident response

Access must be governed by:

- roles and permissions
- audit logs
- environment boundaries
- secret redaction
- privacy constraints

## Memory and Context Retention

Internal memory/context retention should support:

- summarization
- redaction
- deduplication
- expiry policies
- tenant/workspace isolation
- human-controlled cleanup where appropriate

## Final Rule

```text
Do not expose the agent mind.
Expose useful summaries, evidence, actions, and outcomes.
Store internal context safely for platform improvement and engineering review.
```
