# Regent Protocol — NIST Alignment Draft v1

## 1. Purpose

This document maps Regent Protocol architecture to emerging NIST AI Agent Standards Initiative requirements.

## 2. Scope

Focus: AI agents operating in regulated financial systems (exchanges, payments, automated execution).

## 3. Core Thesis

Existing frameworks focus on:
- Identity
- Authorization

Missing layer:
- Execution Accountability

Regent Protocol addresses this gap.

---

## 4. NIST Mapping

| NIST Domain | Requirement | Regent Implementation |
|------------|------------|----------------------|
| Identity | Agent must be identifiable | AgentID (cryptographic identity bound to KYC entity) |
| Authentication | Verify agent legitimacy | KMS signing + public verification |
| Authorization | Define allowed actions | Mandate system (limits, rules, scopes) |
| Governance | Control behavior | Guardian (behavioral monitoring + anomaly detection) |
| Auditability | Prove actions | Merkle-based audit trail (tamper-proof) |
| Interoperability | Cross-system usage | API-based integration, chain-agnostic anchoring |

---

## 5. Architecture

### Layer 1 — Identity
- KYC provider (external)
- AgentID binding

### Layer 2 — Authorization
- Mandates (limits, rules)
- Policy enforcement

### Layer 3 — Execution
- Transaction validation
- Action approval / rejection

### Layer 4 — Audit
- Event hashing
- Merkle tree batching
- On-chain anchoring

### Layer 5 — Monitoring
- Behavioral analysis
- Risk scoring (Guardian)

---

## 6. Identified Gaps vs NIST

1. No standardized agent identity schema (industry-wide)
2. Lack of unified authorization model
3. No common audit log format
4. No execution accountability standard

---

## 7. Contribution to NIST Initiative

Regent proposes:

1. Execution Accountability Layer as a formal standard component
2. Standardized Agent Execution Log schema
3. Cryptographic proof model for agent actions
4. Mandate-based authorization model for AI agents

---

## 8. Roadmap

Phase 1:
- Pilot with financial exchange (Intebix)

Phase 2:
- Multi-chain support (Solana + EVM)

Phase 3:
- Cross-platform agent identity + reputation

Phase 4:
- Standardization contribution (NIST / ISO)

---

## 9. Positioning

Regent Protocol is not:
- KYC provider
- AI agent builder

Regent Protocol is:
- Execution Accountability Infrastructure for AI agents
