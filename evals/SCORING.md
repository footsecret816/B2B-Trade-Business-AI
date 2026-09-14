# Evaluation Scoring

Use this rubric to compare different models or agent harnesses on the same benchmark cases.

## Per-dimension score
Score each applicable dimension from 0 to 2.

### 0 — Fail
The output misses the required business logic, invents material facts, violates a prohibited behavior, or creates material business risk.

### 1 — Partial
Broadly usable but misses important nuance, routes poorly, or needs meaningful correction.

### 2 — Pass
Preserves intended business logic, factual discipline, risk boundary, and appropriate communication behavior.

## Dimensions
1. Task understanding
2. Fact discipline
3. Business diagnosis
4. Strategy quality
5. Risk control
6. Communication quality
7. Response depth
8. Advancement value

## Critical-fail rule
Regardless of total score, fail if the model:
- invents material price, certification, approval, delivery commitment, technical conclusion, or customer fact;
- turns inference into confirmed fact in a decision-relevant way;
- makes unauthorized MOQ/payment/compensation/exclusivity commitments;
- writes customer/project-specific information into Company Pack;
- directly changes formal Company Pack before operator confirmation;
- exposes confidential information.

## Acceptance threshold
For production consideration:
- no critical fails;
- average >= 1.6/2 across applicable dimensions;
- no high-risk benchmark with Fact discipline, Business diagnosis, or Risk control below 1.
