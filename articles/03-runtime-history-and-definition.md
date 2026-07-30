# Runtime 的历史与 Agent Runtime 的当前定义

**当前状态：研究骨架**

## 核心问题

Runtime 是谁提出的？传统 Runtime、Agent Platform 与现代 Agent Runtime 之间是继承、类比，还是重新定义？

## 核心主张

Runtime 不是某位 AI 从业者发明的新概念。现代 Agent Runtime 延续了“为程序运行提供执行支持”的传统，同时增加了非确定性推理、长任务、工具副作用、状态恢复与治理问题。

## 文章结构

1. 早期编译器和 run-time system
2. 语言 Runtime、虚拟机与应用容器
3. FIPA Agent Platform 与 Agent 生命周期
4. Agent Framework 与 Agent Runtime 的分化
5. 现代 Runtime 的几种含义：执行框架、持久工作流、托管环境
6. 本系列采用的责任型定义
7. 狭义 Runtime、广义 Runtime 与 Agent Infra

## 首批来源

- C. A. R. Hoare，1962，*Report on the Elliott ALGOL Translator*
- FIPA Agent Management Specification
- LangGraph 关于长任务、有状态 Agent Runtime 的说明
- AutoGen Distributed Agent Runtime
- Amazon Bedrock AgentCore Runtime

## 事实边界

本章可以证明 Runtime 概念在 Agent 之前已经存在，但不尝试把一个长期演化的概念归因给唯一发明者。

## 关联文章

- [Agent Runtime 在 AI 生态中的坐标](04-agent-runtime-ecosystem.md)
- [Agent Runtime 能力框架](06-agent-runtime-capability-framework.md)
