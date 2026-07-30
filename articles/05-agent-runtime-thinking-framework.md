# Agent Runtime Thinking Framework

**当前状态：研究骨架**

## 核心问题

当新的 Agent 技术、协议或产品出现时，怎样判断它解决的是哪一层问题，而不是被名称和功能列表带着走？

## 核心主张

Agent Runtime Thinking Framework 不是一张固定架构图，而是一组从责任、不变量、生命周期、失败与证据出发的分析问题。

## 十个稳定问题

1. 谁拥有业务语义？
2. 谁控制执行循环？
3. Knowledge、Context、Memory 与 State 分别在哪里？
4. 哪些行为交给模型，哪些必须由代码保证？
5. 工具通过什么合同接入？
6. 失败后怎样重试、暂停与恢复？
7. 行为怎样被 Trace？
8. 结果怎样被 Eval？
9. 权限与审批由谁控制？
10. 模块怎样替换、迁移和演进？

## 文章结构

1. 从“它有什么功能”切换到“它负责什么”
2. 语义与机制
3. 概率性与确定性
4. Knowledge 与 State
5. Protocol 与 Runtime
6. Data Plane 与 Control Plane
7. Online Runtime 与 Offline Platform
8. 能力边界与部署边界
9. 从失败反推责任层
10. 从证据修正 Framework

## 实践验证方式

每个实践 Runtime 都必须说明：

- 采用了哪些 Framework 判断；
- 哪些不变量由代码保证；
- 运行中出现了什么反例；
- Framework 因此发生了什么变化。

## 关联文章

- [能力框架](06-agent-runtime-capability-framework.md)
- 第 19 篇集成实践（尚未创建）
