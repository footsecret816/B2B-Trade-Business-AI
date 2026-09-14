# Company Workspace

`company/` is the canonical local workspace for company-specific information.

## Directories
- `inbox/` — raw materials not yet curated
- `pending/` — approved update candidates waiting for formal review
- `template/` — blank Company Pack structure
- `packs/<company-id>/` — confirmed formal Company Packs
- `ACTIVE_COMPANY.yaml` — local runtime pointer to the company currently represented

## Intake paths
1. GitHub Company Pack → validate → install into `packs/<company-id>/`.
2. User materials → `inbox/` → `company-knowledge-curation` → operator review → formal pack.
3. Business conversation patch → Core detects candidate → operator approves → `pending/` → curation skill → pack update.

## Safety
Real company data in `inbox/`, `pending/`, `packs/`, and `ACTIVE_COMPANY.yaml` is ignored by Git by default. The reusable repository stores only standards/templates.
