# B2B Trade Business AI

A model-agnostic, company-agnostic Business AI Harness for B2B foreign-trade workflows.

这是一个面向 B2B 外贸业务的通用业务 AI 助手框架。它不预装任何具体公司的身份、产品、证书或供应链事实；加载哪个 Company Pack，就代表哪个公司。

## What it does
- 客户邮件/询盘拆解
- 潜客开发与机会判断
- Gap / 商务策略
- MOQ、价格、付款、交期谈判
- Email / WhatsApp / LinkedIn / Follow-up 写作
- 客户 ↔ 工厂信息转换
- 风险与承诺边界控制
- 项目下一步推进
- 从 0 建立并维护 Company Pack

## Architecture
`Core + Skills + Cases + Company + Memory + Knowledge + Evals + Adapters`

核心原则：**模型负责智能，框架负责业务方法与行为一致性。**

## Company onboarding
### 1. GitHub Company Pack
校验兼容格式后安装到 `company/packs/<company-id>/`。

### 2. User Materials
PDF / PPT / Word / Excel / 证书 / 产品目录 → `company/inbox/` → `company-knowledge-curation` → 操作者多轮核对 → 正式 Company Pack。

### 3. Business Conversation Patch
日常业务中出现新证书、新产品线、新产能等可能长期复用的公司事实 → Core 仅标记 `COMPANY_UPDATE_CANDIDATE` → `company/pending/` → 操作者确认 → Curation Skill 正式更新。

## Safety boundary
- 不把推断写成事实
- 不把公司一般能力直接变成当前项目承诺
- 不擅自承诺价格、MOQ 特批、付款、交期、认证或技术结果
- 不把客户/项目专属信息写进 Company Pack
- 不在用户确认前把原始资料直接写成正式公司事实

## Portability
所有路径相对 `AGENT_ROOT` 解析，不依赖固定 `D:\`、`C:\Users\`、`/Users/...` 等本机路径。

## Validation
`evals/` 包含 15 个核心 benchmark 场景、评分标准和 E2E 架构验收入口。跨模型/跨平台生产声明必须在目标 Harness 上实际跑评测。
