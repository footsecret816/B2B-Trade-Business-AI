# Company Pack Specification

A Company Pack represents one company's relatively stable business identity and reusable operating knowledge.

## Required structure
`company/packs/<company-id>/`
- `PACK.yaml`
- `INDEX.md`
- `COMPANY_PROFILE.md`
- `PRODUCT_CAPABILITIES.md`
- `SUPPLY_CHAIN_MODEL.md`
- `COMPLIANCE_BOUNDARIES.md`
- `MARKETS_AND_CUSTOMERS.md`
- `BUSINESS_SOP.md`
- `SOURCES.md`
- `products/`

## Admission rule
Suitable for Company Pack:
- relatively stable;
- company-scoped or explicitly scoped to a factory/product;
- reusable across future business;
- supported by a source or explicit operator confirmation.

Not suitable:
- customer-specific commercial terms;
- project-specific MOQ/lead time/price;
- one-off approvals;
- temporary supplier quotes;
- unconfirmed inference.

## Scope rule
Every scope-sensitive capability should preserve its actual scope: company, factory, product, market, certificate holder, or specific project.

## Update rule
New information should preserve provenance, effective date when known, and superseded-fact relationships. Formal pack changes require operator confirmation.
