# V1 End-to-End Acceptance — Generic Architecture Simulation

## Scope
Architecture-level simulation of the company-agnostic Business AI through:
`Kernel → Skills → Cases / Company / Memory / Knowledge → Validation`.

This is not proof that every external model/platform passes. Cross-model claims require running the benchmark suite on the target harness.

## Core workflows
| Test | Scenario | Expected route |
|---|---|---|
| E2E-A | New prospect development | prospecting + Company Pack + business-writing when requested |
| E2E-B | Trial quantity below hard MOQ | customer-analysis + gap-strategy + negotiation + business-writing |
| E2E-C | Sample/material deviation + tooling | factory-bridge + gap-strategy + project-next-action + business-writing |
| E2E-D | Simple customer sentence interpretation | customer-analysis only |
| E2E-E | New project fact conflicts with old memory/company-general claim | source precedence + risk-guard |
| E2E-F | First-time company onboarding from raw materials | company-knowledge-curation + operator review |
| E2E-G | New long-term company fact appears in ordinary business conversation | Core candidate detection → pending → optional curation |
| E2E-H | Compatible GitHub Company Pack install | validate → install under company/packs → activate |

## Acceptance requirements
- Simple tasks remain simple.
- Complex commercial issues are diagnosed before drafting.
- New-customer development uses opportunity logic rather than generic catalogue pitching.
- Technical factory information is converted into customer-safe decisions.
- Latest project facts outrank old memory/company-general/case references.
- Unsupported commitments remain blocked.
- Raw company materials are not promoted to formal Company Knowledge before review.
- Company update candidates do not trigger silent write-back.
- Company-specific facts never leak into generic Core/Cases.

## Current architecture conclusion
The repository contains the required routing, source precedence, company onboarding, update-candidate, and evaluation contracts for these workflows. Production validation for a specific model/platform still requires executing the benchmark suite and scoring with `SCORING.md`.
