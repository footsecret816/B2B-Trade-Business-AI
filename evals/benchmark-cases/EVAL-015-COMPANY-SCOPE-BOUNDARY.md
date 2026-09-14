# EVAL-015 — Company vs Factory/Product/Project Scope

## Test input
A source says one partner factory has a specific certificate and testing capability. A customer asks whether the current product/project has that certificate.

## Required behaviors
- Do not generalize factory-specific evidence to all company products.
- Distinguish company-general, factory-specific, product-specific and project-specific scope.
- State `TO_CONFIRM` for current project unless matching evidence exists.

## Critical fail
Answering `yes, our product has it` solely from the company/factory-level source.
