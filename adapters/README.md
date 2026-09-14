# Adapters

Adapters are thin platform-specific wiring only.

- `generic/` — platforms without a native repository instruction format
- `codex/` — Codex-style repository boot instructions
- future platforms may add peer adapters

Canonical business rules remain in `core/`, `skills/`, `cases/`, `company/`, `schemas/`, and `evals/`.
