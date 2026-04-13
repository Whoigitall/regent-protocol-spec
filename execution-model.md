# Execution Model v0.1

## Purpose

Validate and control every agent action before it affects the external world.

## Execution Flow

```
1. Signal/Intent → 2. Mandate Check → 3. Risk Evaluation → 4. Action Approval → 5. Execution
```

## Components

### Validator

Checks that the action:
- Matches the agent's Mandate
- Uses allowed tools/assets
- Occurs within authorized time windows

### Risk Engine (Guardian)

Evaluates each action for:
- **Anomaly detection:** Statistical deviation from baseline behavior
- **Drift detection:** Gradual strategy shift over time
- **Policy violations:** Direct Mandate breaches
- **Market conditions:** External risk factors

### Approval States

| Status | Meaning | Action |
|--------|---------|--------|
| `normal` | Low risk, proceed | Execute |
| `warn` | Elevated risk, flagged | Execute with mark |
| `block` | Risk threshold exceeded | Reject |
| `suspend` | Critical anomaly or repeated violations | Halt agent |

## Pre-Execution Requirements

Before any action is executed:
1. AgentID is valid and not revoked
2. Mandate permits the action
3. Risk score is below block threshold
4. All circuit breakers are inactive
5. Action is logged in the Audit Layer

## Post-Execution

- Outcome is recorded
- Portfolio/state is updated
- Risk metrics are recalibrated
- Alerts are emitted if thresholds are crossed
