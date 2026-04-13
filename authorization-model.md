# Authorization Model v0.1

## Purpose

Define explicit boundaries for what an agent is allowed to do, under what conditions, and with what limits.

## Core Concept: The Mandate

A Mandate is a machine-readable policy document attached to an AgentID. It specifies:

- Allowed actions
- Allowed assets or domains
- Quantitative limits
- Temporal constraints
- Escalation rules

## Mandate Structure

```yaml
mandate:
  mandate_id: "mandate-001"
  agent_id: "agent-a41eafed"
  version: "1.0.0"
  effective_from: "2026-04-13T00:00:00Z"
  effective_until: null
  
  constraints:
    allowed_actions: ["buy", "sell", "hold"]
    allowed_assets: ["BTC", "ETH"]
    max_order_size: 10000
    max_daily_loss: 1000
    max_position: 1.0
    trading_hours:
      start: "00:00"
      end: "23:59"
      timezone: "UTC"
    
  controls:
    kill_switch_enabled: true
    escalation_threshold: 0.8
    circuit_breakers:
      - level: "cb-1"
        trigger: "daily_loss > 50%"
        action: "pause_15min"
```

## Enforcement

Every agent action MUST be checked against its active Mandate before execution. Any violation results in:
- Rejection of the action
- Logging of the violation
- Potential suspension of the agent

## Properties

- **Explicit:** No implicit permissions
- **Versioned:** Changes are tracked and auditable
- **Time-bound:** Valid only within specified window
- **Attestable:** Signed by both agent and owner
