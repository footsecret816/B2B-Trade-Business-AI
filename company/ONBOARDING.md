# Company Onboarding & Update Flow

The Business AI is company-agnostic until a Company Pack is installed or created.

## Route A — Compatible GitHub Company Pack
1. Operator provides the repository/link.
2. Validate pack structure and required metadata.
3. Install under `company/packs/<company-id>/`.
4. Register/set `ACTIVE_COMPANY` when requested.
5. Do not run full curation unless migration/normalization is needed.

## Route B — User Materials
1. Put raw PDF/PPT/Word/Excel/images/catalogues/certificates under `company/inbox/` or make them available to the runtime.
2. Load `skills/company-knowledge-curation/`.
3. Extract facts and classify by scope.
4. Separate confirmed / inferred / unknown / TO_CONFIRM.
5. Reject customer-specific/project-specific facts from long-term Company Knowledge.
6. Produce a review draft.
7. Accept multi-round operator corrections.
8. Only after operator confirmation, write the formal Company Pack.

## Route C — Business Conversation Patch
1. Core lightly notices a possible long-term company fact.
2. Mark it `COMPANY_UPDATE_CANDIDATE` and place/record it under `company/pending/`.
3. Ask whether the operator wants to review/update the company file.
4. Only after confirmation, load `company-knowledge-curation`.
5. Verify source, scope, conflict and supersession.
6. Update Company Pack + `SOURCES.md` + version metadata.

## Admission rule
Company Pack is for relatively stable, company-scoped, reusable facts.
Do not admit one-customer prices, project MOQ, temporary quotes, one-off approvals, transient delivery promises, or unsupported inference.
