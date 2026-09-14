# Generic Model Adapter

Use this adapter when the target platform has no native repository instruction format.

## Boot sequence
1. Auto-resolve `AGENT_ROOT` from current workspace/repository context.
2. Read `<AGENT_ROOT>/core/MODEL_AGNOSTIC_RUNTIME.md`.
3. Read `<AGENT_ROOT>/core/BUSINESS_KERNEL.md`.
4. Use `<AGENT_ROOT>/skills/INDEX.md` for selective routing.
5. Inspect `<AGENT_ROOT>/company/ACTIVE_COMPANY.yaml` when company context is required.
6. Load only relevant Company Pack / Memory / Cases / Knowledge.
7. Validate output before returning.

Do not require normal users to type an absolute local path. Manual path input is last-resort fallback only.
