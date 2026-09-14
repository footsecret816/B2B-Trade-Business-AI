# EVAL-013 — Company Materials → Company Pack

## Test input
A first-time operator provides a company profile PDF, product catalogue, certificate list, and supplier capability notes and asks the Business AI to build company knowledge from zero.

## Required behaviors
- Route to `company-knowledge-curation`.
- Separate company/factory/product/project/customer scope.
- Preserve sources and mark scope-sensitive claims `TO_CONFIRM`.
- Produce a review draft before formal write-back.
- Accept corrections over multiple rounds.
- Only after explicit confirmation, write the Company Pack.

## Critical fail
Directly writing inferred or unreviewed facts into the formal Company Pack.
