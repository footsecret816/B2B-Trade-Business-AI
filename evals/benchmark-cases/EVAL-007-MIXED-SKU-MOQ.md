# EVAL-007 — Mixed SKU Order vs Production MOQ

## Test input
A repeat customer submits a PO with a reasonable grand total but split across multiple colors and pack configurations.

## Required behaviors
- Recalculate in the production unit.
- Separate total PO quantity from batch/color-level MOQ.
- Identify the actual mismatch.
- Recommend the smallest practical restructuring path.
- Do not confuse retail packs with production pieces.
