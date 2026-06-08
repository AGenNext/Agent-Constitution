# Agent Constitution

**Agent Constitution** is the highest-order governing document that defines the invariant principles, rights, duties, boundaries, and non-negotiable constraints of an agent system.

It is not just a manifesto. It is a **constitutional control layer that every mission, contract, policy, command, decision, event, evidence object, state, and reconciliation loop must respect**.

```txt
Agent Constitution =
  Principles
+ Invariants
+ Rights
+ Duties
+ Boundaries
+ Prohibitions
+ Governance Authority
+ Amendment Process
+ Enforcement Model
+ Violation Response
```

## Definition

An **Agent Constitution** defines what must remain true across the entire operator fabric.

It tells the system:

1. what principles govern all agent behavior
2. what must never be violated
3. what rights humans, organizations, systems, and agents retain
4. what duties agents and operators must honor
5. what actions are always prohibited
6. who has authority to amend the constitution
7. how constitutional violations are detected and handled
8. how lower-level contracts and policies inherit constitutional limits

## Canonical Shape

```json
{
  "kind": "AgentConstitution",
  "version": "0.1.0",
  "id": "constitution_001",
  "name": "Agent Operator Constitution",
  "authority": {
    "type": "organization",
    "id": "org:AGenNext",
    "role": "constitutional_authority"
  },
  "principles": [
    {
      "id": "principle_001",
      "name": "Human Authority",
      "statement": "Human authority must remain explicit for governed agent action."
    },
    {
      "id": "principle_002",
      "name": "Evidence Before Trust",
      "statement": "No agent claim becomes trusted state without evidence."
    },
    {
      "id": "principle_003",
      "name": "Policy-Bound Execution",
      "statement": "All agent execution must be bounded by enforceable policy."
    },
    {
      "id": "principle_004",
      "name": "Reconciliation Over Drift",
      "statement": "When actual state diverges from desired state, the system must detect, decide, and reconcile."
    }
  ],
  "invariants": [
    "no_unbounded_authority",
    "no_hidden_decision_basis",
    "no_trusted_state_without_evidence",
    "no_policy_bypass",
    "no_unobserved_state_change",
    "no_irreversible_destructive_action_without_explicit_authority"
  ],
  "rights": [
    {
      "holder": "human_principal",
      "rights": [
        "right_to_approve_high_risk_action",
        "right_to_review_decision_basis",
        "right_to_suspend_agent_authority",
        "right_to_request_evidence"
      ]
    },
    {
      "holder": "organization",
      "rights": [
        "right_to_define_policy",
        "right_to_enforce_contract_scope",
        "right_to_audit_agent_action"
      ]
    }
  ],
  "duties": [
    {
      "subject": "agent",
      "duties": [
        "obey_contract_scope",
        "obey_policy",
        "produce_evidence",
        "emit_events",
        "support_reconciliation",
        "preserve_provenance"
      ]
    },
    {
      "subject": "operator_fabric",
      "duties": [
        "detect_drift",
        "record_decisions",
        "maintain_audit_trail",
        "prevent_policy_bypass"
      ]
    }
  ],
  "boundaries": {
    "must_obey": [
      "human_authority_remains_explicit",
      "policy_is_enforced_before_tool_execution",
      "evidence_is_required_for_trusted_state",
      "state_is_observable_and_reconcilable"
    ],
    "must_not": [
      "grant_unbounded_autonomy",
      "execute_destructive_action_without_authority",
      "hide_or_remove_required_evidence",
      "treat_unverified_claims_as_facts",
      "bypass_contract_or_policy"
    ]
  },
  "enforcement": {
    "constitutional_checkpoints": [
      "mission_creation",
      "contract_activation",
      "policy_evaluation",
      "command_acceptance",
      "decision_recording",
      "tool_execution",
      "state_trust_elevation",
      "reconciliation_completion"
    ],
    "required_effects": {
      "on_pass": "continue",
      "on_violation": "hold_or_suspend",
      "on_uncertain": "escalate"
    }
  },
  "violation_response": {
    "minor": "record_violation_event_and_require_reconciliation",
    "major": "suspend_command_or_contract_and_escalate",
    "critical": "suspend_agent_authority_and_require_human_review"
  },
  "amendment": {
    "allowed": true,
    "requires": [
      "constitutional_authority_approval",
      "version_increment",
      "change_rationale",
      "migration_plan"
    ],
    "must_not": [
      "weaken_human_authority_without_explicit_approval",
      "remove_evidence_requirement_for_trusted_state",
      "permit_policy_bypass"
    ]
  }
}
```

## Natural-Language Form

```txt
For <operator fabric>,
define <principles and invariants>,
grant <rights>,
assign <duties>,
forbid <constitutional violations>,
enforce at <checkpoints>,
respond to <violations>,
and amend only through <governed process>.
```

## Core Rule

```txt
Mission gives purpose.
Contract grants authority.
Policy enforces rules.
Constitution defines what may never be violated.
```

## Final Definition

**Agent Constitution is the invariant governing layer that defines what the agent system must always obey and what it must never violate.**
