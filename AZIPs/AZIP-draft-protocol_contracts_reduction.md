---
azip: <Leave blank, AZIP editor will assign an AZIP number>
title: Reduce protocol contract set
description: Remove AuthRegistry, MultiCallEntrypoint, and PublicChecks from the protocol contracts and compact the remaining addresses.
author: David Banks (@dbanks12)
discussions-to: <URL>
status: Draft
type: Core
created: 2026-05-12
---

## Abstract

This AZIP removes the `AuthRegistry`, `MultiCallEntrypoint`, and `PublicChecks` contracts from the protocol contract set. The three remaining protocol contracts (`ContractInstanceRegistry`, `ContractClassRegistry`, `FeeJuice`) are reassigned to protocol addresses `1`, `2`, and `3` respectively.

## Specification

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119 and RFC 8174.

### Removed protocol contracts

The following contracts MUST no longer be members of the protocol contract set and MUST NOT occupy a protocol contract address:

| Name                  | Previous protocol address |
| --------------------- | ------------------------- |
| `AuthRegistry`        | `1`                       |
| `MultiCallEntrypoint` | `4` (historical)          |
| `PublicChecks`        | `6` (historical)          |

These contracts MAY continue to exist as ordinary (non-protocol) contracts deployed via the standard contract instance flow. The protocol MUST NOT grant them any privileged treatment, address aliasing, or implicit deployment.

### Protocol contract address assignments

After this AZIP activates, the protocol contract address space MUST be:

| Address | Contract                   |
| ------- | -------------------------- |
| `1`     | `ContractInstanceRegistry` |
| `2`     | `ContractClassRegistry`    |
| `3`     | `FeeJuice`                 |

All other low-integer addresses (`4`, `5`, …) MUST be treated as unassigned and MUST NOT resolve to any protocol contract.

### Protocol circuits and clients

Protocol circuits, the AVM, the sequencer, the PXE, and `aztec.js` MUST be updated such that:

1. The protocol contracts tree is rebuilt over the new three-entry set at addresses `1`, `2`, `3`.
2. Any constant, hard-coded address, manifest entry, or lookup keyed on `AuthRegistry`, `MultiCallEntrypoint`, or `PublicChecks` is removed.
3. The address constants for `ContractInstanceRegistry` (`2` → `1`), `ContractClassRegistry` (`3` → `2`), and `FeeJuice` (`5` → `3`) are updated. These addresses are referenced throughout the stack via Noir/TS/C++ constants, so this is not a manual per-callsite migration.

## Rationale

These were protocol contracts only for convenience during early development of the protocol and aztec-nr.

## Backwards Compatibility

This is a breaking change to the protocol contract set and to every protocol contract address. All clients, contracts, and tooling that hard-code a protocol contract address or import any of the three removed contracts must be updated. Activation coincides with a network upgrade; there is no in-band migration path.

## Test Cases

All existing end-to-end tests in the monorepo should work with the updated protocol contract addresses. Any tests relying on the three demoted contracts will need to refer to some non-protocol-enshrined deployments of them.

## Reference Implementation

TBD

## Security Considerations

None.

## Copyright

Copyright and related rights waived via [CC0](../LICENSE.md).
