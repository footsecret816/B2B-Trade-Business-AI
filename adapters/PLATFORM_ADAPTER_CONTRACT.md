# Platform Adapter Contract

A Platform Adapter connects this Business AI Core to a specific agent platform without changing business methodology.

## Root resolution
Resolve logical `AGENT_ROOT` automatically:
1. platform-provided repository/workspace/project root;
2. upward discovery for `AGENTS.md + core/ + skills/`;
3. plugin/package/import root;
4. remote repository context;
5. manual selection only as last fallback.

Never hard-code machine-specific absolute paths.

## Adapter responsibilities
- boot entry
- root resolution
- context mapping
- skill packaging
- tool mapping
- memory bridge
- permission boundary
- degradation behavior
- eval entry

## Prohibitions
Adapters must not duplicate or fork Business Core logic, embed real customer histories, promote Company Pack facts into project facts, or claim unavailable tools/integrations.

## Company workspace
Adapters must map `<AGENT_ROOT>/company/` consistently. Local company data paths are runtime state, not reusable business knowledge.
