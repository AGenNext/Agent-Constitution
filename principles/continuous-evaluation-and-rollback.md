# Continuous Evaluation and Rollback

## Purpose

Agent Platform is responsible for continuously improving every agent's evaluation score, benchmark score, reliability, cost performance, and production readiness.

If an agent does not improve over time, or if it regresses below required thresholds, the platform must roll back, demote, quarantine, or replace that agent version.

## Core Principle

```text
Every agent must improve, or be rolled back.
```

## Platform Responsibility

Agent Platform must measure every agent across:

- objective completion rate
- evaluation score
- benchmark score
- trust score
- cost efficiency
- latency
- tool reliability
- human approval rate
- rework rate
- blocker frequency
- timeout frequency
- regression rate
- production incident contribution

## Required Signals

The platform should collect signals from:

```text
Agent-Eval
  → quality and rubric scores

Agent-Bench
  → benchmark performance and regression tests

Agent-Trust
  → evidence, provenance, and confidence

Agent-FinOps
  → cost and budget performance

Agent-Traces
  → execution traces, failures, blockers, timeouts

Agent-Maturity
  → readiness and lifecycle stage

Agent-Memory
  → improvement history and lessons learned
```

## Agent Versioning

Every agent should have:

```yaml
agent_id: string
agent_version: string
blueprint_version: string
memory_version: string
skill_versions: []
tool_versions: []
eval_score: number
bench_score: number
trust_score: number
cost_score: number
maturity_level: string
status: active | canary | probation | rolled_back | quarantined | retired
```

## Improvement Policy

Agents should be expected to improve over rolling windows.

Example windows:

- last 10 runs
- last 50 runs
- last 7 days
- last 30 days

Improvement means one or more of:

- higher eval scores
- higher benchmark scores
- lower rework rate
- lower failure rate
- lower timeout rate
- lower cost for same quality
- higher human approval rate
- fewer blocker escalations
- better latency

## Regression Policy

Trigger rollback or quarantine when:

- eval score drops below threshold
- benchmark score regresses beyond tolerance
- trust score drops below threshold
- cost exceeds budget repeatedly
- incident contribution exceeds threshold
- human rejection rate rises
- blocker/timeouts increase materially
- tool misuse or unsafe behavior appears
- agent repeatedly fails the same objective class

## Rollback Actions

Possible actions:

```text
warn
  → probation
  → canary previous version
  → rollback
  → quarantine
  → retrain/reconfigure
  → retire
```

## Rollback Event Types

Agent-Traces should record:

- `agent.performance.measured`
- `agent.performance.regressed`
- `agent.performance.improved`
- `agent.rollback.recommended`
- `agent.rollback.started`
- `agent.rollback.completed`
- `agent.quarantined`
- `agent.retired`

## Human Oversight

High-impact rollbacks should require human approval unless the agent is unsafe or causing production incidents.

Recommended policy:

```text
low-risk rollback
  → automatic allowed

high-risk rollback
  → human approval required

safety/production incident
  → immediate quarantine allowed, human review follows
```

## Self-Improvement Loop

```text
run objective
  → trace behavior
  → evaluate result
  → benchmark regression
  → trust-check evidence
  → cost-check performance
  → compare to prior windows
  → update agent memory
  → promote if improved
  → rollback/quarantine if regressed
```

## Final Rule

```text
No agent remains active indefinitely without measurable improvement or stable excellence.
Regression requires rollback, quarantine, or corrective action.
```
