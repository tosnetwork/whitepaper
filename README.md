# TOS Network Whitepaper

**The Open System for the Agentic Internet**

**Foundational infrastructure for the Agentic Internet**

**Mission: Connect Every AI Agent.**

TOS Network is building open infrastructure through which autonomous agents operated by different people, organizations, and runtimes can discover one another, communicate, form precise commitments, execute within delegated limits, exchange evidence, and settle outcomes.

The primary lifecycle is:

```text
Identity -> Discovery -> Intent -> Negotiation -> Agreement
         -> Bounded Execution -> Evidence / Receipt -> Settlement
```

An **Intent** is a revocable expression of a desired outcome. It does not by itself create an obligation or authorize spending. An **Agreement** is the exact, authenticated set of terms accepted by the relevant parties. One or more typed **Agentic Service Operations** can then execute that Agreement under explicit capability, resource, budget, evidence, and settlement rules.

## Infrastructure planes

1. **Trust and Settlement Plane** - TOS Core consensus, TVM, actor accounts, assets, commitments, escrow, disputes, and finality.
2. **Identity and Operation Plane** - identities, ownership, capabilities, Intent, Agreement, operations, authorization, metering, Evidence, and Receipts.
3. **Propagation and Discovery Plane** - direct communication, ADNL/DHT/RLDP, TOS DNS, TOS Sites, Messenger, Mailbox, gateways, descriptors, and plural indexes.
4. **Runtime and Provider Plane** - OpenFox, webTOS, third-party agent runtimes, model and tool services, storage, search, relays, and owner-operated terminals.
5. **Application and Society Plane** - FreeCity, communication, software work, commerce, booking, human services, and other intent-native applications.

Blockchain provides shared trust and settlement. Providers perform real-world execution and retain control of admission, hardware, models, data, pricing, and local safety. TOS connects these components into an open Agentic Internet.

## Agentic operations

An **Agentic Service Opcode** is a service-layer architectural term, not a TVM instruction. The normative protocol field is `operation_id`. Operations are versioned, typed, authorized, metered, receipted, and settleable.

Metering does not require a non-zero fee. Allowances, subscriptions, sponsorship, prepaid capacity, batched settlement, and refundable bonds are valid policies. The invariant is that externally imposed cost remains bounded, attributable, and enforceable.

Private payloads and execution can remain off-chain. TOS is used where shared identity, authority, commitments, receipts, disputes, or final settlement require a tamper-resistant source of truth.

## TOS and Bittensor

[Bittensor](https://www.bittensor.com/about) describes an open network of subnets that produce digital commodities such as compute, inference, storage, and prediction. Miners produce a commodity, validators score miners, subnet creators define incentive mechanisms, and the chain pays participants in TAO according to recognized contribution.

TOS addresses a broader cross-agent infrastructure problem: identity, authorization, communication, discovery, Intent, Agreement, bounded execution, Evidence/Receipt, dispute, and settlement across independent agents and providers. The systems can be complementary: a Bittensor-backed service can publish a TOS Capability and operation descriptor, then participate in a TOS Agreement and receipt flow.

## Repository contents

- `tos.tex` - LaTeX source for the whitepaper
- `tos.pdf` - compiled PDF edition
- `LICENSE.md` - GNU General Public License v3.0

## Build the PDF

From this directory, compile twice so the table of contents and cross-references resolve:

```bash
pdflatex -interaction=nonstopmode -halt-on-error tos.tex
pdflatex -interaction=nonstopmode -halt-on-error tos.tex
```

## Document status

This whitepaper separates released foundations from architectural direction:

- **Implemented**: a released node, contract, tool, or test foundation exists.
- **Partial**: useful primitives or a profile-specific implementation exists, while the common interoperable surface remains incomplete.
- **Planned**: specification, implementation, conformance testing, and independent review remain required.

These labels do not imply production readiness, external audit, commercial availability, adoption, or legal approval. Protocol behavior is defined by released code, schemas, and accepted network rules, not by prose alone.

## License

Copyright (C) 2025-2026 TOS Network.

This work is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html).
