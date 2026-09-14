# Platform Adapter Contract

## Purpose
A Platform Adapter connects the canonical Business AI Core to a specific agent platform without changing the business methodology.

`Business Core != Company Pack != Customer Memory != Platform Adapter != Model != Tools`

## Root portability
Resolve logical `AGENT_ROOT` / `REPO_ROOT` automatically:
1. platform repository/workspace/project root;
2. upward discovery until `AGENTS.md`, `core/`, `skills/` are found;
3. package/plugin/import root;
4. remote repository root exposed by the platform;
5. manual fallback only if all automatic methods fail.

Never hard-code or persist machine-specific absolute paths.

## Canonical sources
- `<AGENT_ROOT>/core/MODEL_AGNOSTIC_RUNTIME.md`
- `<AGENT_ROOT>/core/BUSINESS_KERNEL.md`
- `<AGENT_ROOT>/skills/`
- `<AGENT_ROOT>/cases/`
- `<AGENT_ROOT>/company/`
- `<AGENT_ROOT>/memory/`
- `<AGENT_ROOT>/knowledge/`
- `<AGENT_ROOT>/schemas/`
- `<AGENT_ROOT>/evals/`

## Adapter responsibilities
1. boot entry;
2. root resolution;
3. context map;
4. skill packaging/discovery;
5. tool map;
6. memory bridge;
7. permission boundary;
8. degradation behavior;
9. evaluation entry.

## Prohibitions
Adapters must not fork the Business Kernel, duplicate negotiation/writing/risk logic, embed real customer data, weaken fact discipline, or claim tools that do not exist.

## Context-loading rule
Keep always-on instructions short. Load skills, product knowledge, cases, company files and customer memory only when relevant.

## Capability degradation
When a capability is unavailable, state the limitation when material, complete the reliable portion, mark missing evidence `TO_CONFIRM`, and never fabricate tool execution.

## Readiness levels
- A0 Generic
- A1 Booted
- A2 Skills mapped
- A3 Tools & memory mapped
- A4 Evaluated

Only A4 should be described as production-validated for a target platform/model.
