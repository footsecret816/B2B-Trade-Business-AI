# B2B Trade Business AI — Architecture Baseline

## Goal
Externalize reusable B2B foreign-trade business methods into a company-agnostic, model-agnostic, platform-portable Business AI Harness.

## Architecture
- `core/` — reasoning and fact discipline
- `skills/` — reusable business capabilities
- `cases/` — abstract experience patterns and anti-patterns
- `company/` — local company workspace and Company Packs
- `memory/` — customer/project memory layer
- `knowledge/` — company-independent reusable knowledge
- `schemas/` — data structure standards
- `evals/` — cross-model/platform acceptance tests
- `adapters/` — thin platform wiring

## Company-agnostic principle
The Core must not contain facts about any specific company. A company identity is created by loading or building a Company Pack under `company/packs/<company-id>/`.

## Company onboarding
Three supported paths:
1. compatible GitHub Company Pack → validate → install locally;
2. user materials → `company/inbox/` → `company-knowledge-curation` → operator review → formal pack;
3. normal business conversation → lightweight candidate detection → `company/pending/` → operator confirmation → curation skill → pack update.

## Non-goals
- Do not create many autonomous sub-agents.
- Do not make every conversation run the heavy company-curation workflow.
- Do not mix customer/project records into Company Knowledge.
- Do not bind runtime logic to one machine path, model, or platform.
