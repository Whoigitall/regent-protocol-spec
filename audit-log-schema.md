# Audit Log Schema v0.1

## Purpose

Provide a tamper-proof, reconstructible record of every significant agent action.

## Log Layers

| Layer | Records | Example Fields |
|-------|---------|----------------|
| Identity | Who acted | `agent_id`, `session_id`, `public_key` |
| Input | On what basis | `source_id`, `content_hash`, `timestamp` |
| Deliberation | Why decided | `confidence_score`, `rationale`, `options` |
| Action | What attempted | `action_type`, `symbol`, `quantity`, `price` |
| Risk | How evaluated | `risk_score`, `guardian_status`, `threshold` |
| Outcome | What resulted | `pnl_delta`, `fees`, `execution_status` |
| Governance | Overrides/events | `event_type`, `previous_state`, `new_state` |

## Integrity Model

Each log entry includes:
- `event_id` — unique identifier
- `timestamp` — ISO-8601
- `event_signature` — SHA-256 hash of entry content
- `chain_hash` — hash linking to previous entry (append-only)

## Merkle Batching

For scalable verification, log entries are batched into Merkle trees:
- Periodic batching (e.g., every 1000 events or 1 hour)
- Merkle root is anchored on-chain or in a trusted timestamp service
- Any individual entry can be proven inclusion with a Merkle path

## Example Entry (Action Layer)

```json
{
  "event_id": "evt-20260413-000001",
  "timestamp": "2026-04-13T12:00:00Z",
  "agent_id": "agent-a41eafed",
  "session_id": "session-06522209",
  "action_type": "buy",
  "asset": "BTC",
  "quantity": 0.0146,
  "price": 68312.06,
  "execution_status": "filled",
  "event_signature": "sha256:...",
  "chain_hash": "sha256:..."
}
```

## Deterministic Replay

Given the same:
- Inputs
- Agent configuration
- Random seeds

The entire execution trace MUST be reproducible byte-for-byte.

## Storage

- Primary: append-only local/remote log store
- Verification: Merkle root anchors
- Retention: configurable (minimum 7 years for regulated use)
