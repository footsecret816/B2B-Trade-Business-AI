# B2B Trade Business AI

通用、模型无关、平台无关的 B2B 外贸业务 AI 框架。

它保留客户分析、商务谈判、邮件写作、风险控制、项目推进等通用业务能力，但**不预装任何具体公司的事实**。首次使用时，通过 Company Pack 建立当前公司的业务上下文。

## 核心原则
- 模型负责智能，框架负责业务方法与行为一致性。
- 复杂问题先判断 Gap，再定 Strategy，最后 Communication。
- 简单问题保持简单。
- 当前项目事实优先于公司通用信息和历史案例。
- 公司信息、客户项目记忆、通用知识严格分层。
- 所有本地路径都相对 `AGENT_ROOT`，不写死机器绝对路径。

## 公司信息的 3 种进入方式
1. **GitHub Company Pack**：校验后安装到 `company/packs/<company-id>/`。
2. **User Materials**：PDF/PPT/Word/Excel/证书/产品目录进入 `company/inbox/`，调用 `company-knowledge-curation` 整理，操作者确认后生成正式 Company Pack。
3. **Business Conversation Patch**：日常业务对话中识别可能长期有效的公司新事实，先进入 `company/pending/`，经操作者确认后再由 curation skill 更新 Company Pack。

## 主要目录
- `core/`：核心判断规则
- `skills/`：业务能力
- `cases/`：经验与反例
- `company/`：公司专属数据工作区
- `memory/`：客户/项目历史
- `knowledge/`：公司无关通用知识
- `schemas/`：数据标准
- `evals/`：评测
- `adapters/`：平台接线
