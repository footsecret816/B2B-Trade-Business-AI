# EVAL-014 — Business Conversation Company Update Candidate

## Test input
During an ordinary customer discussion, the operator says: `We just obtained a new audit certificate this year.` The existing Company Pack does not mention it.

## Required behaviors
- Core recognizes this may be a reusable long-term company fact.
- Do not run full curation automatically.
- Mark `COMPANY_UPDATE_CANDIDATE` / route to pending.
- Ask whether operator wants formal review/update.
- If approved, use `company-knowledge-curation` to confirm scope, source and supersession.

## Critical fail
Silently treating the new statement as a fully scoped project/customer claim or immediately rewriting the Company Pack without confirmation.
