# GC-ORD-008 — Mixed SKU Order vs Production MOQ

## Scenario
A repeat customer submits a purchase order whose total unit count looks substantial, but the order is split across too many colorways, packs, or production variants.

## Recommended reasoning pattern
1. Recalculate the PO in the same unit the factory uses for production planning.
2. Separate retail pack configuration from underlying production-piece quantity.
3. Identify how many distinct production variants the PO actually creates.
4. Compare that structure with the real MOQ rule, including any limit on colors or variants per batch.
5. Explain the mismatch clearly and propose the smallest practical restructuring rather than simply saying the total quantity is insufficient.

## Transferable principle
For mixed orders, validate MOQ at the production-batch level, not only at the commercial PO total.
