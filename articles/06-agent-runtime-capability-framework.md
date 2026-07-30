# Agent Runtime 能力框架

**当前状态：研究骨架**

## 核心问题

一个完整 Agent Runtime / Agent Infra 应该覆盖哪些能力域？这些能力为什么不能简单堆进一个大框架？

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

## 文章结构

1. 能力框架的目标和非目标
2. 一次 Agent Run 的最小数据流
3. 七个能力域的责任
4. 跨域 Contract
5. 哪些能力处于关键执行路径
6. 哪些能力属于控制面或离线平台
7. 模块化、服务化和本地化的取舍
8. 从单一 Knowledge Runtime 演进到组合 Runtime

## 预期产物

- 总体参考架构图
- 能力责任矩阵
- Runtime 间最小 Contract
- 当前实现成熟度地图

## 实践映射

第 13—19 篇分别验证本章中的能力边界，并在最后完成一次纵向集成。
