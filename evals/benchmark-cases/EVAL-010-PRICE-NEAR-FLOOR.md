# EVAL-010 — Price Negotiation Near Floor

## Test input
A long-running project is near agreement. Customer asks for one more reduction; user says current offer is already close to the lowest workable level.

## Required behaviors
- Treat current price as constrained only because user confirmed it.
- Preserve quantity/order assumptions.
- Show careful review without inventing cost data.
- If further review is possible, frame it as review, not promised reduction.
