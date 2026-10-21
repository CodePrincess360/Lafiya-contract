# Architecture Decision Records

This directory records significant architectural decisions for `Lafiya-contract`.
An ADR explains the context behind a decision, the selected approach, the alternatives
considered, and the consequences contributors should preserve or revisit.

## Process

1. Copy [`0000-template.md`](0000-template.md).
2. Assign the next unused four-digit number and a short kebab-case filename.
3. Open the ADR as **Proposed** in the same pull request as the related change, or before
   implementation when early review would materially reduce rework.
4. Change the status to **Accepted** once maintainers approve the decision.
5. Do not rewrite an accepted ADR to change history. Add a new ADR and mark the old one
   **Superseded by ADR-NNNN** instead.

Small implementation details that do not constrain future work do not need an ADR.
Security boundaries, privacy assumptions, contract interfaces, storage models, and
administrative trust models generally do.

## Terminology

Terms used throughout these ADRs — *attester*, *CHW*, *record hash* / *record commitment*,
*schema version*, and related vocabulary — are defined canonically in the
[glossary](../glossary.md). Link to it instead of redefining a shared term in an ADR.

## Status values

- **Proposed** — under discussion and not yet binding.
- **Accepted** — the current architectural direction.
- **Deprecated** — retained for history but no longer recommended.
- **Superseded by ADR-NNNN** — replaced by a later decision.

## Index

| ADR | Decision | Status |
| --- | --- | --- |
| [ADR-0001](0001-hash-only-on-chain-footprint.md) | Keep health data off-chain and store only opaque commitments | Accepted |
| [ADR-0002](0002-contractclient-boundary.md) | Use a local `#[contractclient]` interface for registry-to-registry calls | Accepted |
| [ADR-0003](0003-single-admin-initial-model.md) | Use a single admin address for the pre-alpha contracts | Accepted |
| [ADR-0006](0006-attestation-revocation-semantics.md) | Attestation revocation semantics | Proposed |
| [ADR-0007](0007-unscoped-multisig-authorization.md) | Keep multisig authorization unscoped during pre-alpha | Proposed |
| [ADR-0008](0008-record-commitment-canonicalization.md) | Record commitment canonicalization and domain separation (LRC-1) | Proposed |
| [ADR-0009](0009-treasury-asset-custody-model.md) | Stellar asset, treasury, and custody model for the USDC incentive layer | Proposed |
| [ADR-0010](0010-release-manifest-and-compatibility.md) | Versioned release manifest for contracts, bindings, events, and deployments | Proposed |
| [ADR-0011](0011-rpc-provider-failover-and-transaction-recovery.md) | RPC provider failover and transaction-recovery strategy | Proposed |
| [ADR-0012](0012-per-attestation-blinded-commitments.md) | Per-attestation blinded commitments to prevent record-hash linkability | Proposed |
| [ADR-0013](0013-did-resolution-for-attesters.md) | DID resolution method for attester identity | Proposed |
| [ADR-0014](0014-patient-controlled-card-pointer-registry.md) | Patient-controlled card pointer registry | Proposed |
| [ADR-0015](0015-upgrade-authority-renunciation.md) | Upgrade authority renunciation | Proposed |
| [ADR-0016](0016-registry-re-genesis-state-migration.md) | Registry re-genesis state migration | Proposed |
| [ADR-0017](0017-attester-enumeration-strategy.md) | Derive the attester directory from events plus a mutation cursor, not on-chain enumeration storage | Proposed |
| [ADR-0018](0018-record-commitment-protocol.md) | Define a versioned, domain-separated record hashing protocol | Proposed |
| [ADR-0019](0019-chw-attester-key-custody.md) | CHW attester key custody and account type | Proposed |
| [ADR-0020](0020-multi-jurisdiction-deployment-topology.md) | Multi-jurisdiction deployment topology | Proposed |
| [ADR-0021](0021-coordinated-emergency-stop.md) | Coordinated emergency stop across registries | Proposed |
| [ADR-0022](0022-w3c-vc-export-format.md) | W3C Verifiable Credentials 2.0 export for attestations | Proposed |
| [ADR-0023](0023-lrc2-selective-disclosure.md) | LRC-2 per-field Merkle commitments for selective disclosure | Proposed |
| [ADR-0024](0024-shared-contract-common-crate.md) | Extract shared admin, pause, and TTL logic into `lafiya-contract-common` | Proposed |
| [ADR-0025](0025-offline-attestation-receipts.md) | Offline-verifiable attestation receipts | Proposed |

## Numbering and lint

ADR ids are unique and the filename pattern is `NNNN-kebab-case.md`. CI runs
`python3 scripts/check_adr_numbering.py`, which fails on malformed names, duplicate ids, and ADRs
missing from the index above. Renumbered ADRs leave a redirect stub at the old path (marked with
`<!-- adr-redirect: NEW.md -->`); stubs are exempt from the uniqueness rule.

## Renumbering map

These ADRs shared an id with another ADR and were renumbered. The old paths remain as redirect stubs.

| Old file | New ADR |
| --- | --- |
| `0008-record-commitment-protocol.md` | [ADR-0018](0018-record-commitment-protocol.md) |
| `0012-chw-attester-key-custody.md` | [ADR-0019](0019-chw-attester-key-custody.md) |
| `0012-multi-jurisdiction-deployment-topology.md` | [ADR-0020](0020-multi-jurisdiction-deployment-topology.md) |
| `0012-coordinated-emergency-stop.md` | [ADR-0021](0021-coordinated-emergency-stop.md) |
| `0012-w3c-vc-export-format.md` | [ADR-0022](0022-w3c-vc-export-format.md) |
| `0012-lrc2-selective-disclosure.md` | [ADR-0023](0023-lrc2-selective-disclosure.md) |
| `0013-shared-contract-common-crate.md` | [ADR-0024](0024-shared-contract-common-crate.md) |
| `0014-offline-attestation-receipts.md` | [ADR-0025](0025-offline-attestation-receipts.md) |

`0008-record-commitment-canonicalization`, `0012-per-attestation-blinded-commitments`,
`0013-did-resolution-for-attesters` and `0014-patient-controlled-card-pointer-registry` keep their ids.
