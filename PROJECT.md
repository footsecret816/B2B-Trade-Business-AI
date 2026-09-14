# B2B Trade Business AI — Architecture Baseline

## Purpose
A reusable, company-agnostic Business AI Harness for B2B foreign-trade work.

## Core runtime
`Context → Understand → Diagnose → Decide → Communicate → Advance`

For complex commercial conflict: Strategy before Writing.
For simple tasks: stay simple.

## Architecture
- `core/` — model-agnostic runtime and lightweight business kernel
- `skills/` — reusable business capabilities
- `cases/` — anonymized Golden Cases and anti-patterns
- `company/` — local company workspace and Company Packs
- `memory/` — customer/project history layer
- `knowledge/` — generic industry knowledge only
- `schemas/` — data contracts
- `evals/` — cross-model/platform benchmarks
- `adapters/` — thin platform integration layer

## Company model
This repository does not assume any company identity.
An installed Company Pack under `company/packs/<company-id>/` supplies company-specific facts.

Company Pack can come from:
1. a compatible GitHub Company Pack;
2. user-provided source materials curated through `company-knowledge-curation`;
3. approved long-term company-information patches detected during normal business work.

## Data boundaries
Company Knowledge is not Customer/Project Memory.
Customer/project facts, prices, POs, temporary terms and special approvals must not become long-term company capability by accident.

## Portability
All paths are relative to logical `AGENT_ROOT`; platform/model/tool differences belong in thin adapters.
