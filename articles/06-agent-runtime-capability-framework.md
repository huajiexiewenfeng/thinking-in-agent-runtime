# Agent Runtime 能力框架

**当前状态：研究骨架**

## 核心问题

一个完整 Agent Runtime / Agent Infra 应该覆盖哪些能力域？这些能力为什么不能简单堆进一个大框架？它们又如何在不混淆责任边界的前提下，共同支撑一个持久 Domain subject？

## 核心主张

Loop、State、Knowledge、Tools、Policy、Trace、Eval 是责任不同但相互协作的能力域。它们可以部署在一起，也可以拆成多个模块或服务；能力边界不等于部署边界。

## 核心能力域

1. Loop Runtime
2. State & Workflow Runtime
3. Knowledge & Context Runtime
4. Tool Gateway / MCP Adapter
5. Policy / Identity / Approval
6. Trace Runtime
7. Eval Runtime

## Agent Infra 扩展能力

- Agent / Skill / Tool Registry
- Deployment 与 Scheduling
- Session Isolation 与 Multi-Tenancy
- Secrets
- Trace Storage 与 Offline Eval
- Cost、Audit 与 Governance
- Version、Capability Negotiation 与 Migration

## 综合验证目标

能力框架最终需要在真实系统中接受纵向组合验证。当前提出的目标之一是 Vertical Domain Agent：Skill 表达 Domain semantics，Harness 定义具体 workload lifecycle，Runtime 的七个能力域提供持续执行、状态、知识、工具、治理、Trace 与 Eval。

这个目标用于发现跨域 Contract 的缺口，而不是要求所有能力部署在同一个进程，也不是把 Vertical Domain Agent 写成 Agent Runtime 的唯一终点。

## 文章结构

1. 能力框架的目标和非目标
2. 一次 Agent Run 的最小数据流
3. 七个能力域的责任
4. 跨域 Contract
5. 哪些能力处于关键执行路径
6. 哪些能力属于控制面或离线平台
7. 模块化、服务化和本地化的取舍
8. 从单一 Knowledge Runtime 演进到组合 Runtime
9. 用 Vertical Domain Agent 检验七个能力域能否形成完整闭环

## 预期产物

- 总体参考架构图
- 能力责任矩阵
- Runtime 间最小 Contract
- 当前实现成熟度地图

## 实践映射

第 13—19 篇分别验证本章中的能力边界与 Agent Infra 集成。第 20 篇将把 Domain Skill、Harness 与七个 Runtime 能力放入同一责任模型，检验它们是否足以支撑持久、受治理、可恢复、可评测的 Domain subject。
