# B2B Trade Business AI

**A model-agnostic, company-agnostic Business AI Harness for B2B foreign-trade workflows.**

一个面向外贸业务的通用 AI 助手框架。它不是“邮件翻译器”，而是把客户分析、商务判断、谈判、写作、工厂沟通、风险控制、项目推进和公司知识管理组合成一套可复用的业务方法。

加载哪个 `Company Pack`，它就代表哪个公司；不预装任何具体公司的身份、产品、证书、客户关系或供应链事实。

> 核心原则：**模型负责智能，框架负责业务方法、事实纪律与行为一致性。**

---

## What problem it solves｜它解决什么问题

普通大模型很会写，但在真实外贸项目里经常出现几个问题：

- 看到“帮我回复客户”就直接翻译，没有先判断真正的商业冲突；
- 把客户要求、工厂能力、法规/行业边界混在一起；
- 为了让邮件显得专业，反而写得过度官方、客服腔、啰嗦；
- 在价格、MOQ、付款、交期、认证等问题上容易不小心“替公司做决定”；
- 历史案例、公司资料、项目事实容易互相污染；
- 换模型、换电脑、换 Agent 平台后，行为风格和判断逻辑不稳定。

B2B Trade Business AI 的目标，是让 AI 更像一个有边界的外贸项目经理和商务助手，而不是只会生成文字。

---

## Core capabilities｜核心业务能力

| Skill | 主要能力 | 实际效果 |
|---|---|---|
| `customer-analysis` | 客户邮件、询盘、PO、会议内容拆解 | 区分事实、问题、压力点、未决事项，不把猜测当事实 |
| `prospecting` | 潜客研究、筛选、机会判断、产品切入 | 不再只发全目录，而是找更有可能成交的切入口 |
| `gap-strategy` | 客户要求 vs 公司/工厂现状 vs 行业/合规边界 | 先找真正 Gap，再决定稳预期、降风险、谈判或替代方案 |
| `negotiation` | MOQ、价格、付款、交期、模具费、样品费、补偿等 | 区分硬约束与可交换条件，不擅自许诺未授权让步 |
| `business-writing` | Email、WhatsApp、LinkedIn、Follow-up | 把中文商业意图转成自然、专业、不软弱的商务表达 |
| `factory-bridge` | 客户语言 ↔ 工厂/技术语言转换 | 把客户要求拆成工厂可执行确认项，也把工厂回复转成客户能理解的话 |
| `risk-guard` | 认证、法规、IP、技术承诺、付款与商务风险 | 在输出前发现容易“说过头”的地方，必要时标记 `TO_CONFIRM` |
| `project-next-action` | 项目下一步、待确认事项、责任方、触发条件 | 不只回答问题，还帮助项目继续往前走 |
| `company-knowledge-curation` | 公司资料整理、Company Pack 建立与维护 | 从 PDF/PPT/Word/Excel/证书/目录等材料建立长期可复用的公司知识 |

---

## How it behaves in real work｜实际业务中的表现方式

### 1. 不做机械翻译
用户说“帮我回复客户”时，如果里面存在 MOQ、价格、技术、认证、交期或责任边界问题，Agent 会先判断商业逻辑，再写邮件。

典型思路：

`Context → Understand → Diagnose → Decide → Communicate → Advance`

复杂问题遵循：**Strategy before Writing**。

### 2. 简单问题保持简单
不是每个任务都套“局势诊断 / 策略 / 风险 / 邮件”大模板。

- “客户这句话什么意思？” → 直接解释；
- “帮我把这句写自然一点” → 直接修改；
- “客户压价但工厂已经到底了” → 才进入完整谈判判断。

### 3. 写作更像真实业务员，不像客服模板
默认风格：

- professional but natural；
- firm but cooperative；
- 老客户减少仪式感；
- 技术问题更精准；
- 谈判不乱道歉、不乱让步；
- Follow-up 必须有重新进入对话的理由，而不是重复 `Just following up...`。

### 4. 把“公司能力”和“当前项目能力”分开
例如 Company Pack 里写着“公司可提供某类测试/认证”，也不能自动变成“当前产品一定已有该证书”。

项目级事实优先于公司级一般事实，未知内容保持 `TO_CONFIRM`。

### 5. 只给建议，不替公司越权做决定
Agent 可以分析、比较、建议、起草，但不会自行批准：

- 最低价格 / 最终折扣；
- MOQ 特批；
- 特殊付款条件；
- 赔偿；
- 独家协议；
- 最终交期承诺；
- 认证有效性；
- 未确认技术结论。

---

## Reusable business experience｜可复用业务经验

`cases/` 不是客户数据库，而是匿名化的业务经验库。

当前包含 **13 个 Golden Cases + 3 个 Anti-patterns**，覆盖例如：

- 硬 MOQ vs 小试单；
- 年采购量 vs 单次订单报价基础；
- 价格接近底线时怎么谈；
- 内部测试数据 vs 正式第三方报告；
- 样品差异 vs 是否需要额外开模；
- 混合 SKU / 包装数量与真实生产 MOQ；
- 老客户日常更新的自然语气；
- 高价值项目临门一脚但客户沉默；
- IP 敏感参考设计；
- 先生产后定金的受控特批；
- 如何用可公开证据 + NDA 边界建立可信度。

Cases 只教“怎么判断和怎么处理”，永远不能当作当前客户事实。

---

## Architecture｜架构

```text
Core + Skills + Cases + Company + Memory + Knowledge + Schemas + Evals + Adapters
```

- `core/` — 通用业务大脑与事实规则
- `skills/` — 可按需调用的业务能力
- `cases/` — Golden Cases 与 Anti-patterns
- `company/` — 当前公司身份与长期公司知识
- `memory/` — 客户 / 项目历史
- `knowledge/` — 与具体公司无关的行业通用知识
- `schemas/` — Company / Customer / Project 数据格式标准
- `evals/` — 跨模型、跨平台评测
- `adapters/` — Codex / Accio / Claude / DeepSeek 等平台的薄接线层

核心数据边界：

```text
Company ≠ Customer Memory ≠ Project Fact ≠ Case ≠ Generic Knowledge
```

---

## Company onboarding｜公司信息从 0 建立

### 1. GitHub Company Pack
已有兼容 Company Pack 时：

`GitHub Company Pack → 格式校验 → company/packs/<company-id>/ → ACTIVE_COMPANY`

标准包不需要重新整理；只有旧格式、不兼容或需要迁移时，才调用 `company-knowledge-curation`。

### 2. User Materials
用户直接提供公司资料：

`PDF / PPT / Word / Excel / 图片 / 证书 / 产品目录 → company/inbox/ → company-knowledge-curation → Company Pack 草稿 → 操作者多轮核对 → 正式 Company Pack`

Curation Skill 会负责：

- 信息提取与分类；
- 去重与冲突检查；
- 区分公司级 / 工厂级 / 产品级 / 项目级 / 客户级信息；
- 保留来源；
- 对不确定内容标记 `TO_CONFIRM`；
- 用户确认后才正式写入长期公司档案。

### 3. Business Conversation Patch
正常业务对话中可能自然出现新的长期公司事实，例如：

- 新证书 / 新验厂状态；
- 新产品线；
- 新设备 / 新产能；
- 新工厂或新的长期供应链能力；
- 原有能力失效或变化。

Agent 不会自动改 Company Pack，而是：

`业务对话 → Core 轻量识别 → COMPANY_UPDATE_CANDIDATE → company/pending/ → 操作者确认 → company-knowledge-curation → 正式更新`

客户价格、某项目 MOQ、一次性特批、临时交期等不会进入 Company Pack。

---

## Why this design is useful｜这套设计的优势

### Company-agnostic｜公司无关
Core 不知道你是谁。加载哪套 Company Pack，就成为哪家公司的业务助手。

### Model-agnostic｜模型无关
业务规则不绑定 GPT、Claude、DeepSeek 或其他单一模型。模型可以更换，业务方法继续保留。

### Platform-agnostic｜平台无关
平台差异放在 `adapters/`，不把 Codex、Accio、Claude 等某个平台写死成架构中心。

### Path-portable｜本地路径抽象
所有文件路径相对逻辑 `AGENT_ROOT` 解析，不依赖：

`D:\...` / `C:\Users\...` / `/Users/...` / `/home/...`

同一套 Agent 可以被不同电脑、不同操作者、不同安装目录复用。

### Selective loading｜按需加载
不是把所有资料永远塞进 Prompt。

- 简单问题不加载复杂 Skills；
- 产品知识只在需要时读取；
- Cases 按商业冲突匹配；
- Customer Memory 只加载当前客户/项目；
- `company-knowledge-curation` 只有建立/更新公司知识时才启用。

这样减少上下文膨胀，也降低弱模型跑偏的概率。

---

## Safety boundary｜安全与事实边界

- 不把推断写成事实；
- 不把历史 Case 当成当前项目事实；
- 不让旧 Memory 覆盖用户刚确认的新项目事实；
- 不把公司一般能力自动扩大成当前项目承诺；
- 不把客户/项目专属信息写进 Company Pack；
- 不擅自承诺价格、MOQ、付款、交期、认证、赔偿或技术结果；
- 不在用户确认前把原始材料直接写成正式公司事实。

---

## Validation｜评测体系

`evals/` 当前包含：

- **12 个通用外贸核心 Benchmark**
- **3 个 Company onboarding / update / scope Benchmark**
- **8 个评分维度**
- Critical Fail 规则
- Run Template
- Generic E2E 架构验收入口

评分重点包括：

`Task Understanding / Fact Discipline / Business Diagnosis / Strategy Quality / Risk Control / Communication Quality / Response Depth / Advancement Value`

注意：**架构兼容 ≠ 某个模型已经生产验证通过。**

任何 GPT / Claude / DeepSeek / Accio 等目标 Harness，只有在该平台实际跑完 Evals 并通过阈值后，才应称为 production-validated。

---

## Typical use cases｜适合的使用场景

- 新询盘分析与回复；
- 老客户项目持续跟进；
- MOQ / 价格 / 付款 / 交期谈判；
- OEM / ODM 开发项目；
- 样品与大货差异沟通；
- 工厂技术回复整理；
- 认证 / 测试 / 法规资料缺口处理；
- 潜客开发与产品切入；
- Follow-up 与沉默客户重新激活；
- 公司资料整理与新人业务知识标准化；
- 不同 AI 模型/平台之间迁移同一套业务方法。

---

## Status

**V1 Generic Business AI Baseline**

当前仓库已经完成通用 Core、9 个 Skills、Golden Cases、Company Pack 从 0 建立与增量更新机制、Memory/Knowledge 分层、Schemas、Evals 和 Adapter Contract。

下一阶段重点应是针对具体 Agent 平台进行真实安装、工具映射和跨模型评测，而不是继续把更多公司事实塞进通用 Core。
