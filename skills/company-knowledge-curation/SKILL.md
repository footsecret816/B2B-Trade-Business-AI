# company-knowledge-curation

## Role
Optional plug-in skill. Only load when the operator explicitly wants to build, normalize, review, migrate, or update company knowledge.

## Unique responsibility
Convert raw company materials or approved update candidates into a formal Company Pack.

## Inputs
- `company/inbox/` — raw PDF/PPT/Word/Excel/images/certificates/catalogues/web exports
- `company/pending/` — operator-approved `COMPANY_UPDATE_CANDIDATE` items
- incompatible/legacy Company Pack that needs migration

## Workflow
1. extract supported facts from source materials;
2. classify by topic and scope;
3. separate company-level, factory-level, product-level, project-level, and customer-level facts;
4. deduplicate and identify conflicts;
5. preserve source/provenance;
6. mark uncertain or scope-sensitive items `TO_CONFIRM`;
7. produce a review draft for the operator;
8. accept multi-round corrections and additions;
9. only after operator confirmation, write/update the formal Company Pack;
10. update version/source records and mark superseded facts when appropriate.

## Company knowledge admission rule
Suitable for Company Pack when the information is relatively stable, company-scoped, reusable across future business, and supported by a source or explicit operator confirmation.

Do not admit as long-term Company Knowledge:
- one customer's special price;
- one project's MOQ or delivery promise;
- one-off management approval;
- temporary supplier quote;
- unconfirmed inference;
- customer/project confidential data that belongs in Memory.

## Special caution
Certificates, testing capability, production capacity, factory capability, regulatory claims, and similar statements must preserve their actual scope. A factory/product-specific fact must not be generalized to the whole company without evidence.

## Boundary
This skill does not continuously monitor normal business conversations. Lightweight candidate detection belongs to the Core. It also does not need to process a fully compatible GitHub Company Pack unless migration/normalization is required.
