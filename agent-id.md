# AgentID Specification v0.1

## Purpose

Provide a verifiable, non-forgeable identity for AI agents operating in regulated or multi-party environments.

## Structure

```yaml
agent_id:
  identifier: "agent-{uuid}"
  public_key: "0x..."
  owner_reference: "kyc-provider-id"
  creation_timestamp: "ISO-8601"
  revocation_timestamp: "ISO-8601 | null"
  version: "0.1"
```

## Properties

- **Non-forgeable:** Bound to cryptographic key pair
- **Verifiable:** Any third party can validate signature and ownership
- **Bound:** Linked to a responsible legal entity via KYC provider
- **Revocable:** Owner or guardian can invalidate the identity

## Verification Steps

1. **Signature Check:** Verify that agent actions are signed with the corresponding private key
2. **Public Key Validation:** Confirm public key is registered and not revoked
3. **Owner Lookup:** Resolve owner reference through registered KYC provider
4. **Temporal Validity:** Ensure current time is within creation/revocation bounds

## Example

```json
{
  "agent_id": "agent-a41eafed",
  "public_key": "0x04a1b2c3...",
  "owner_reference": "kyc-acme-corp-8821",
  "creation_timestamp": "2026-04-13T12:00:00Z",
  "revocation_timestamp": null,
  "version": "0.1"
}
```
