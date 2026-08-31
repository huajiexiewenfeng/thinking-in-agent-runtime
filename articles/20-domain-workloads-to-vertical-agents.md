# 从 Domain Workload 走向 Vertical Domain Agent

**当前状态：研究骨架，综合验证目标，尚未共同写作**

## 本章在全书中的位置

本章不是重新定义 Agent Runtime，也不是把 Vertical Domain Agent 写成 Agent Runtime 的唯一目的。

《Thinking in Agent Runtime》的 North Star 仍然是：建立一套能够解释、设计、实现和验证 Agent Runtime 的统一框架，并通过真实 Runtime 项目持续修正它。

本章承担的是后置综合职责：在 Loop、State、Knowledge、Tool、Policy、Trace、Eval 等能力域分别得到定义和实践检验后，追问它们能否共同支撑一个持久、受治理、可恢复、可评测的 Domain 运行主体。

本章可以作为“Agent 系统与持久知识”研究系列的第三篇公开专题文章提前讨论，但在全书阅读顺序中应位于能力框架与实践章节之后，不是书内第 03 章。

## 核心问题

> **一个 Domain 还需要什么，才能真正成为 Agent，而不只是被通用 Agent 临时调用？**

更具体地说：

- Skill 已经表达了 Domain semantics，为什么它还不等于 Domain Agent？
- Harness 已经承载了状态机、Evidence、Approval 与 Recovery，为什么它仍不自动成为持久 Agent？
- Runtime 需要提供哪些通用能力，才能让 Domain workload 跨模型调用、Harness run 和执行宿主持续存在？
- 什么证据足以证明这些能力已经形成一个 Vertical Domain Agent，而不是一组相邻组件？

## 核心 Thesis

> **Agent Runtime 不只是为 Skill 增加 Memory。对于具体 Domain，它通过 Loop、State、Knowledge、Tool、Policy、Trace 与 Eval 等通用能力，为 Skill 所表达的领域语义和 Harness 所承载的 workload 提供身份与权限边界、跨执行连续性、Evidence、Recovery 和受控演进条件，使其具备走向持久 Vertical Domain Agent 的可能。**

短锚点：

> **Skill 暴露 Domain，Harness 承载 workload，Agent Runtime 为它提供可持续运行、治理、恢复和评测的基础。**

证据限定：

> **这是组合架构与研究方向。当前仓库只验证了 Knowledge integration、Domain lifecycle 与 Principal authority 的部分机制，并未证明完整 Vertical Domain Agent 已经实现。**

## 与全书能力框架的关系

本章不引入第二套 Agent Runtime 词表，而是把现有七个能力域映射到同一个 Domain subject：

| 能力域 | 对 Domain subject 的贡献 |
| --- | --- |
| Loop Runtime | 让一次模型调用成为有退出边界的持续执行 |
| State & Workflow Runtime | 保存 Run state、Checkpoint、Retry 与 Recovery |
| Knowledge & Context Runtime | 建立与 Domain-owned knowledge 的持久受权关系 |
| Tool Gateway / MCP Adapter | 绑定可用 Capability，并控制外部副作用 |
| Policy / Identity / Approval | 表示 Principal、Authority、风险与 Human Gate |
| Trace Runtime | 关联 Model、Tool、Knowledge、State 与 Approval Evidence |
| Eval Runtime | 判断变化是否改善质量，并发现 Regression |

Runtime 可以使变化持续存在，但只有 Trace 与 Eval 能证明这种变化叫作成长。

## Domain 进入系统的三个层次

```text
Domain semantics
→ 通过 Skill 被表达

Domain work
→ 通过 Harness 被组织为 workload

Domain continuity
→ 通过 Runtime Contract 被持久化、治理和评测
```

这三个层次不能互相替代：

- Domain 不只是 Corpus 或 Tool Wrapper；
- Skill 不自动拥有持久 Identity；
- workload 能执行，不代表它已经成为 Agent；
- Runtime 不创造 Domain meaning；
- 持久化变化不等于质量已经提高。

## 责任模型

| 角色 | 核心责任 | 不应被混同为 |
| --- | --- | --- |
| 通用 Agent / Execution Host | 通用推理、工具使用与执行基础 | 每个 Domain 的永久 Identity |
| Skill | Domain semantics、方法与能力入口 | 完整 Domain Agent |
| Harness | Domain-specific workload、状态机、Evidence 语义与 Human Gates | 通用 Runtime 机制或最终持久主体 |
| Agent Runtime | Loop、State、Knowledge、Tool、Policy、Trace 与 Eval 的通用 Primitive 和 Contract | 某一个 Domain-specific workflow 或语义权威 |
| llm-wiki-runtime | 受治理的 Knowledge Plane | 完整 Agent Runtime |
| Human / Domain Owner | Governance、semantic acceptance 与最终授权 | 可被自动化消除的实现细节 |
| Vertical Domain Agent | 由上述责任形成的持久受治理 Domain subject | Prompt、Skill、Harness、Session 或模型实例 |

### Skill

Skill 让通用 Agent 理解并进入 Domain。它可以定义词汇、任务方法、解释方式、Capability discovery 与工具使用。本文不主张 Skill 天生无状态，只主张 Skill 不自动成为跨执行持续的授权主体。

### Harness

Harness 是可重复 Domain workload 的 Domain-specific operating layer。它定义具体状态机、Plan、Evidence 语义、Receipt、Human Gates、终态标准与业务恢复决策。

Harness 决定具体 Domain lifecycle 的意义；Runtime 提供持久状态、幂等、授权、知识访问与 Trace 等可复用机制。

### Agent Runtime

Agent Runtime 位于概率模型与真实业务世界之间，为 Agent 执行提供通用运行能力与确定性边界。它不拥有 Domain semantics，也不替代 Harness 定义具体 lifecycle。

Principal 只是 Agent Identity 的一种授权表示，不等于完整 Agent Identity。Capability Binding、状态归属、版本关系与跨宿主连续性仍需单独设计和验证。

### Vertical Domain Agent

> **一个持久且受治理的 Domain 运行主体。它拥有稳定 Identity，与特定 Capability、workload 和 Domain knowledge 建立显式关系，并能够跨多次执行保存状态、产生 Evidence、从失败中恢复，在 Human Authority 下接受经过 Eval 的变化。**

## 最小判定标准

后续实践至少需要逐项验证：

1. stable identity；
2. explicit capability and workload binding；
3. repeatable Domain lifecycle；
4. durable state and recovery；
5. governed relationship with Domain knowledge；
6. explicit Authority and Human Approval；
7. cross-run Evidence and Trace；
8. Eval-backed evolution；
9. 清楚的 Host、Harness 与 Runtime 可替换边界。

这些是验收标准与未来假设，不是当前仓库的完成清单。

## 当前局部实践证据

### llm-wiki-runtime：Knowledge Plane

当前能够直接支持的判断包括：

- deterministic Query 与 bounded Context；
- validation、authorization 与 provenance；
- accepted knowledge 与 controlled persistence；
- Principal 与 Mapping ownership 的明确边界。

它证明的是持久 Domain subject 所需的 Knowledge relationship 可以被显式治理，不能证明完整 Identity、Loop、Run checkpoint、统一 Trace、Eval 或跨宿主可移植性。

### Research Publishing Harness：Lifecycle 维度

仓库能够支持的事实：

- Harness 拥有状态、Digest、Approval、Evidence、Receipt 与恢复边界；
- `llm-wiki-runtime 0.2.0` 集成是可选、显式的；
- Runtime 只在有边界的 Query、校验、Record 访问和受控持久化节点被调用。

架构解释：Domain workload 可以跨时间和状态保持受治理的运行连续性。

限制：Lifecycle continuity 主要由 Harness 实现；案例没有证明完整 Agent Identity，也没有证明可量化业务收益。

### AI Research Observatory：Principal 与 Authority 维度

仓库能够支持的事实：

- Harness 是独立 workload Principal；
- Skill 是可选的交互 Principal；
- 两者可以读取同一 accepted record；
- Skill 借用 Harness Mapping 写入时返回 `mapping_owner_mismatch`。

架构解释：Domain workload 可以拥有独立且不可借用的 Authority boundary。

限制：Principal 只解决授权身份，不等于完整 Agent Identity，也没有证明跨 Host 连续性。

## 两个案例如何组合，又在哪里断开

| 能力 | Publishing Harness | Observatory | 当前结论 |
| --- | --- | --- | --- |
| Domain-specific lifecycle | 强 | Memory workflow 局部覆盖 | 已有局部证据 |
| Principal / Authority | 非主要证据 | 强 | 已有局部证据 |
| Knowledge continuity | 可选 Runtime 0.2 集成 | Runtime 0.3 集成 | 已有局部证据 |
| Recovery | Harness 层 | Receipt / recovery 局部覆盖 | 部分实现 |
| Capability Binding | 弱 | 主要是 Mapping | 尚未充分验证 |
| Cross-host identity | 无 | 无 | 未来假设 |
| Unified Trace / Eval | 无完整证明 | 无完整证明 | 未实现 |

两个案例形成组合假设，不构成同一个 Vertical Domain Agent 的端到端证明。

## 最强反对意见

### 这是否其实是 Agent Platform 或 Agent OS？

本章采用全书的责任型定义，但必须保留 Runtime 与 Agent Infra 的边界。直接参与 Agent Run 的 Loop、State、Knowledge、Tool policy、online Trace 与 online Eval 属于 Runtime；Registry、Deployment、组织级 Governance、Trace Storage 与 offline Eval 更偏 Agent Infra。

### Harness 已经执行并持久化全部工作，为什么还需要 Runtime？

Harness 可以自行实现这些机制。Runtime 的价值不是逻辑上不可替代，而是把状态、授权、知识访问、Trace、Eval 与恢复不变量从单个 Domain 中抽成可复用 Contract。

### Principal 为什么不能直接等同于 Agent Identity？

Principal 只证明“谁以什么 Authority 调用 Runtime”。稳定身份、版本、Capability Binding、状态归属与跨宿主连续性仍需独立验证。

### 垂直化来自 Skill、Domain data 与 Eval，Runtime 到底贡献什么？

Runtime 不创造垂直语义，也不保证能力提升。它让 Domain semantics、workload、knowledge 与经过 Eval 的变化能够持续、受控、可审计地归属于一个运行主体。

## 当前缺口

- Capability 与 workload 的版本化 Binding；
- stable Agent identity 与 cross-host continuity；
- 独立 Run State 与 Checkpoint；
- 统一 Trace schema；
- Eval cases、Golden Trace 与 Regression；
- Capability / Policy migration 与 rollback；
- 多个真实 Domain 的长期验证。

## 后续正式写作结构

1. 一个 Domain 还需要什么，才能成为 Agent？
2. 放回全书：本文不是重新定义 Agent Runtime。
3. Domain 进入系统的 semantics、workload、continuity 三层。
4. Skill：让通用 Agent 进入 Domain。
5. Harness：让 Domain work 成为可重复 workload。
6. Runtime：七个能力域如何支撑同一个 Domain subject。
7. Vertical Domain Agent 的最小判定标准。
8. llm-wiki-runtime 已经证明了什么。
9. Research Publishing Harness 的 lifecycle 证据。
10. AI Research Observatory 的 Authority 证据。
11. 两个案例如何组合，又在哪里断开。
12. 正面回应最强反对意见。
13. 从 continuity 到 growth 还缺什么。
14. 把 Vertical Domain Agent 变成全书的可验证问题。

## 研究闭环

```text
提出 Vertical Domain Agent 假设
→ 映射所需 Runtime 能力
→ 在真实 Domain 中实现局部机制
→ 收集 Trace 与 Bad Case
→ 用 Eval 判断是否有效
→ 修正 Agent Runtime Framework
```

本章的价值不是给 Agent Runtime 增加一个更宏大的定义，而是给全书七个能力域提供一个可以被长期证伪、验证和修正的综合目标。

## 关联章节

- [总览：我们研究的 Agent Runtime 到底是什么](01-overview.md)
- [Agent Runtime 在 AI 生态中的坐标](04-agent-runtime-ecosystem.md)
- [Agent Runtime Thinking Framework](05-agent-runtime-thinking-framework.md)
- [Agent Runtime 能力框架](06-agent-runtime-capability-framework.md)
- 第 07—12 篇能力域理论章节（尚未创建）
- 第 13—19 篇实践与集成章节（尚未全部创建）

## 后续 Evidence Pass

- [Research Publishing Harness](https://github.com/huajiexiewenfeng/research-publishing-harness)
- [AI Research Observatory](https://github.com/huajiexiewenfeng/ai-research-observatory)
- [llm-wiki-runtime Observatory reference example](https://github.com/huajiexiewenfeng/llm-wiki-runtime/tree/main/examples/ai-research-observatory)

正式写作前，所有仓库事实必须链接到精确文件与 immutable revision；架构解释与未来假设必须使用明确限定语。
