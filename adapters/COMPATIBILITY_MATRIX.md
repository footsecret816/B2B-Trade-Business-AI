# Compatibility Matrix

This matrix records architectural readiness, not marketing claims.

| Platform | Adapter state | Notes |
|---|---|---|
| Generic prompt/harness | A1 baseline | Canonical fallback for platforms without native adapter format |
| Codex | A1/A2 baseline | Boot entry and canonical skill routing available; production validation still requires eval run |
| Accio Work | A0 mapping | Architecture can map to workspace/skills/tools; dedicated adapter should be created when actively deployed |
| Claude agent environments | A0 mapping | Use thin adapter; do not duplicate business logic |
| DeepSeek Harness | A0 mapping | Use thin adapter; benchmark before production claim |
| WorkBuddy / similar | A0 mapping | Add only when selected for real deployment |

## Rule
Installation compatibility is not business-quality validation. Run Evals on the actual target model/harness before calling it production-ready.
