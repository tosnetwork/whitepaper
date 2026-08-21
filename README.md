# TOS Network Whitepaper

**The Open System for the Agentic Internet**

TOS Network proposes a common operation, authorization, metering, receipt, and settlement layer for the Agentic Internet. It enables independently operated agents and service providers to invoke one another through typed, bounded, economically accountable operations.

The core abstraction is the **Agentic Service Operation**: a versioned action with an explicit input/output contract, capability scope, resource envelope, budget, metering rules, receipt semantics, and settlement policy. Examples include messaging, encrypted mailbox delivery, model or tool invocation, storage, event publication, commerce, booking, and physical-edge services.

> Web2 gave machines APIs. TOS gives agents economic opcodes.

## Contents

- `tos.tex` — LaTeX source for the whitepaper
- `tos.pdf` — compiled PDF edition

## Key ideas

- **Agentic Service Opcode** is a service-layer concept, not a TVM instruction opcode. The normative protocol field is `operation_id`.
- Operations are **typed, authorized, metered, receipted, and settleable**.
- Metering does not require a non-zero per-call fee. Allowances, subscriptions, sponsorship, prepaid capacity, and refundable bonds are valid policy choices.
- Resource use and externally imposed cost must remain bounded, attributable, and enforceable.
- Private application payloads and execution can remain off-chain; TOS is used where shared authority, commitments, receipts, disputes, or settlement require a tamper-resistant source of truth.
- The paper distinguishes released TOS Core foundations from partial and planned Agentic Operation Protocol product layers.

## Build the PDF

From this directory, compile the source with a LaTeX distribution that provides `pdflatex`:

```bash
pdflatex tos.tex
pdflatex tos.tex
```

The second pass resolves the table of contents and cross-references. The generated `tos.pdf` is the rendered whitepaper.

## Document status

This whitepaper contains both implemented foundations and architectural direction:

- **Implemented**: released node, contract, tooling, or test foundation exists.
- **Partial**: useful primitives or a profile-specific implementation exists, while the generic interoperable surface remains incomplete.
- **Planned**: specification, implementation, conformance testing, and independent review are still required.

Protocol behavior is ultimately defined by released code, schemas, and accepted network rules—not by prose alone.

## License

Copyright © 2025–2026 TOS Network.

This work is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html).
