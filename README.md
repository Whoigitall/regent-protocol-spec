# Regent Protocol Specification

> Execution Accountability Infrastructure for AI Agents

## Overview

Regent Protocol defines a layered architecture for accountable AI agent execution in regulated environments. It addresses the critical gap between agent identity/authorization and actual execution accountability.

## Core Documents

| Document | Description |
|----------|-------------|
| [agent-id.md](./agent-id.md) | Cryptographic agent identity specification |
| [authorization-model.md](./authorization-model.md) | Mandate-based authorization framework |
| [execution-model.md](./execution-model.md) | Transaction validation and behavioral monitoring |
| [audit-log-schema.md](./audit-log-schema.md) | Tamper-proof execution logging standard |
| [nist-alignment.md](./nist-alignment.md) | NIST AI Agent Standards mapping |

## Architecture

```
┌─────────────────────────────────────────┐
│  Layer 1: Identity (AgentID)            │
├─────────────────────────────────────────┤
│  Layer 2: Authorization (Mandates)      │
├─────────────────────────────────────────┤
│  Layer 3: Execution (Validation)        │
├─────────────────────────────────────────┤
│  Layer 4: Audit (Merkle Logs)           │
├─────────────────────────────────────────┤
│  Layer 5: Monitoring (Guardian)         │
└─────────────────────────────────────────┘
```

## Target Use Cases

- Financial exchanges and automated execution
- Payment systems with AI agent participation
- Cross-platform agent identity and reputation
- Regulatory compliance frameworks

## Status

Draft v0.1 — open for review and contribution.

## Roadmap

- **Phase 1:** Pilot with financial exchange
- **Phase 2:** Multi-chain support (Solana + EVM)
- **Phase 3:** Cross-platform agent identity + reputation
- **Phase 4:** Standardization contribution (NIST / ISO)
