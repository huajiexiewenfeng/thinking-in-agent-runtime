# Agent Runtime 在 AI 生态中的坐标

**当前状态：研究骨架**

## 核心问题

Agent Runtime 位于 Model、Agent Framework、MCP、Tools、RAG、Workflow Engine 和 Agent Application 之间的什么位置？

## 核心主张

Agent Runtime 是概率模型与业务执行之间的运行底座；Agent Infra 则进一步覆盖构建、部署、观测、评测和治理。

## 文章结构

1. AI 生态不能只用一条技术栈表示
2. 上游：Model、Agent SDK、Skill、数据与工具提供者
3. 核心：Agent Runtime 的执行、状态、知识与治理
4. 横向：RAG Infra、Workflow Engine、MCP、Observability、Eval
5. 下游：Role Copilot、Agentic Workflow、AI Native App
6. Framework、Runtime、Infra、Platform 的区别
7. 使用一张责任地图定位具体产品

## 关键边界表

本章将逐项比较：

- Model 与 Runtime
- Skill 与 Runtime
- Agent Framework 与 Runtime
- MCP 与 Runtime
- Tool 与 Runtime
- Knowledge Runtime 与 RAG
- State Runtime 与 Workflow Engine
- Agent Runtime 与 Agent Infra

## 实践映射

第 13—19 篇将把实际项目重新放回这张生态图，检查定位是否准确。
