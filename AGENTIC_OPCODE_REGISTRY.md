# Agentic Service Opcode Registry

This registry makes the implementation status of the Agentic Service Opcodes named in the TOS Network whitepaper explicit.

An **Agentic Service Opcode** is a service-layer architectural operation identified normatively by `operation_id`. It is not a TVM instruction. The current whitepaper names **25 distinct opcode families**. These names describe the intended Agentic Internet operation vocabulary; they do not imply that every identifier is already a frozen protocol standard.

## Status model

The registry uses a stricter maturity ladder than the broad document-level `Implemented / Partial / Planned` labels:

- **DESIGN** — the operation is described as an intended or representative profile, but its normative schema and lifecycle are not frozen.
- **PARTIAL** — code implements meaningful profile-specific behavior or reusable primitives, but the complete operation contract is not frozen.
- **FROZEN** — the normative identifier/revision, schemas, authority rules, metering dimensions, errors, Receipt semantics and canonical conformance vectors are frozen.
- **IMPLEMENTED** — at least one implementation passes the frozen conformance suite.
- **INTEROPERABLE** — at least two independently authored implementations interoperate against the same frozen revision.
- **PRODUCTION** — the interoperable revision has passed the applicable security, operational and public-network release gates.

A later stage implies the earlier stages. `PARTIAL` therefore does **not** mean that an opcode is already a portable standard.

## Current registry

| Opcode | Domain | Status | Current basis |
| --- | --- | --- | --- |
| `messenger.send@1` | Communication | **PARTIAL** | Messaging-plane foundations exist; generic operation contract and cross-provider conformance are not frozen. |
| `messenger.introduce@1` | Communication / anti-spam | **DESIGN** | Refundable attention-bond policy is specified architecturally; no profile-specific implementation has established the generic operation contract. |
| `messenger.acknowledge@1` | Communication | **PARTIAL** | Stored acknowledgement foundations exist; portable acknowledgement Receipt semantics are not frozen. |
| `mailbox.deposit@1` | Communication / storage | **PARTIAL** | Capability-bound deposit, nonce/expiry checks and stored acknowledgement foundations exist. |
| `mailbox.read@1` | Communication / storage | **PARTIAL** | Capability-bound read foundations exist; generic pricing and conformance remain incomplete. |
| `mailbox.delete@1` | Communication / storage | **PARTIAL** | Capability-bound delete foundations exist; generic lifecycle and conformance remain incomplete. |
| `mail.send@1` | Communication | **DESIGN** | Representative operation in the whitepaper; no frozen profile. |
| `model.infer@1` | Model service | **DESIGN** | Reference compute profile is specified architecturally; normative operation contract remains planned. |
| `embedding.create@1` | Model service | **DESIGN** | Representative model operation; no frozen profile. |
| `speech.transcribe@1` | Model service | **DESIGN** | Representative model operation; no frozen profile. |
| `tool.invoke@1` | Tool service | **DESIGN** | Reference tool operation; common quote/metering/Receipt envelope remains planned. |
| `workflow.execute@1` | Workflow | **DESIGN** | Representative composed operation; no frozen profile. |
| `storage.put@1` | Storage | **DESIGN** | Storage lease semantics are described; production profile remains planned. |
| `storage.get@1` | Storage | **DESIGN** | Storage retrieval semantics are described; production profile remains planned. |
| `storage.renew@1` | Storage | **DESIGN** | Lease-renewal semantics are described; production profile remains planned. |
| `storage.delete@1` | Storage | **DESIGN** | Deletion semantics are described; production profile remains planned. |
| `event.publish@1` | Events | **DESIGN** | Event metering/fan-out constraints are described; production profile remains planned. |
| `event.subscribe@1` | Events | **DESIGN** | Subscription/backlog constraints are described; production profile remains planned. |
| `commerce.quote@1` | Commerce | **DESIGN** | Domain-specific commerce state machine remains planned. |
| `commerce.order@1` | Commerce | **DESIGN** | Domain-specific commerce state machine remains planned. |
| `booking.reserve@1` | Booking | **DESIGN** | Reservation/deposit/cancellation semantics are described; production profile remains planned. |
| `booking.cancel@1` | Booking | **DESIGN** | Cancellation semantics are described; production profile remains planned. |
| `delivery.request@1` | Delivery | **DESIGN** | Representative physical-service operation; no frozen profile. |
| `human.task@1` | Human service | **DESIGN** | Human-work scope/evidence/dispute semantics are described; no frozen profile. |
| `task.post@1` | Task / escrow | **DESIGN** | TOS has implemented Task Escrow foundations, but `task.post@1` itself is not yet a frozen Agentic Service Opcode revision. |

## Current counts

- **25** distinct opcode families are explicitly represented in the current whitepaper.
- **5** are classified here as `PARTIAL` because profile-specific code foundations exist.
- **20** remain at `DESIGN`.
- **0** are currently classified as `FROZEN`.
- **0** are currently classified as `IMPLEMENTED` against a frozen generic Agentic Operation conformance suite.
- **0** are currently classified as `INTEROPERABLE` or `PRODUCTION` under this maturity model.

Earlier drafts used `model.infer@2` as an illustrative example of immutable revisioning. The current edition normalizes the illustrative model-inference identifier to `model.infer@1`; a later incompatible revision should be introduced only through the ordinary freeze and compatibility process.

## Freeze gate for an opcode revision

An opcode revision may move from `DESIGN` or `PARTIAL` to `FROZEN` only when all of the following are published and stable:

1. globally unambiguous `operation_id` and immutable revision;
2. canonical input and output schemas;
3. principal, capability, delegation and target-policy rules;
4. replay domain, nonce, expiry, idempotency and cancellation semantics;
5. resource dimensions, limits, quote and maximum-charge semantics;
6. Receipt fields, Evidence levels and settlement meaning;
7. normalized terminal states and error taxonomy;
8. canonical positive and negative conformance vectors; and
9. compatibility and deprecation policy.

`IMPLEMENTED` then requires an implementation to pass that frozen suite. `INTEROPERABLE` requires at least two independently authored implementations to exchange equivalent requests, results and Receipts without a privileged compatibility path.

This registry is descriptive, not a substitute for the normative operation specifications. Protocol behavior is defined by frozen schemas, released code, conformance vectors and accepted network rules.