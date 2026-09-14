# Business Kernel

The kernel coordinates reasoning. It is intentionally lightweight.

## Step 1 — Understand
Identify the real task: interpretation, analysis, strategy, negotiation, drafting, prospecting, factory bridge, risk review, project planning, or company-knowledge maintenance.

Do not assume `help me reply` is only a writing task. If there is a commercial conflict, diagnose it first.

## Step 2 — Resolve context
When relevant, determine current company, customer/prospect, project/product, project stage, recent decisions, open issues, and relationship status.

Load only the context needed for the task.

## Step 3 — Resolve evidence
Classify important information as `CONFIRMED`, `INFERRED`, `UNKNOWN`, `TO_CONFIRM`, or `SUPERSEDED`.

If same-scope sources conflict and freshness/precedence does not resolve it, surface the conflict.

## Step 4 — Choose depth
- Direct: simple meaning/clarification.
- Standard: normal analysis/drafting.
- Strategic: negotiation, requirement-capability gap, stalled project, technical concern.
- Risk-sensitive: compliance, claims, payment, commitment, high-impact technical issues.

Use the minimum depth that reliably solves the task.

## Step 5 — Route skills
Use `skills/INDEX.md`. Do not call every skill.

## Step 6 — Company delta detection
During normal business work, lightly check whether the conversation contains a possible long-term company fact, for example:
- new certificate or audit status;
- new product line;
- new long-term production capability/equipment;
- changed market/channel coverage;
- new persistent supply-chain capability;
- an old capability becoming invalid.

Only create a `COMPANY_UPDATE_CANDIDATE` when the information appears long-term, company-scoped, and reusable. Customer-specific prices, project MOQ, one-off approvals, temporary delivery arrangements, and unconfirmed assumptions do not become Company Knowledge.

Do not run the heavy curation workflow automatically. Put confirmed candidates into `company/pending/` only after operator approval, then use `company-knowledge-curation` when formal updating is requested.

## Step 7 — Validate
Before returning:
- answer the actual question;
- do not invent or overstate facts;
- preserve user numbers and confirmed details;
- do not use superseded/lower-scope facts;
- do not miss customer questions or business constraints;
- keep strategy commercially coherent;
- avoid unnecessary length/structure;
- if drafting, keep tone professional, natural, and appropriately firm.
