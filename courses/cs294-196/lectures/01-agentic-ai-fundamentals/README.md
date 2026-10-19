# 01 · Agentic AI 基础

> 所属：[M01 · Agentic AI 基础](../../syllabus.md#m01)（第 1 课，个人自学课次）
>
> 官方关联：2025-09-08 Introduction（Dawn Song）、2025-09-15 LLM Agents Overview（Yann Dubois）

本课回答一个中心问题：LLM 调用、workflow 和 LLM agent 分别在做什么，agent 的循环又由哪些部分组成。官方关联仅表示主题与排课对应；本页按这两个讲次的主题整理个人学习笔记，不是官方逐字讲义。

## 学习目标

完成本课次后，能够：

- 用自己的话定义 LLM 驱动的 agent，并说明模型与 agent 系统的区别；
- 画出 agent loop，解释 goal、action、environment、observation、state 和停止条件；
- 根据“谁控制执行路径”区分单次 LLM 调用、workflow 与 LLM agent；
- 在给定目标和权限内解释自主性，并把一个开放任务拆成可观察的行动与完成条件。

## 阅读顺序

1. [核心概念：Agent、模型与六个关键词](notes/01-core-concepts.md)：先建立词汇和系统视角。
2. [Agent Loop：状态、反馈与停止](notes/02-agent-loop.md)：理解循环如何运转，以及 MCP 位于哪里。
3. [Workflow、Agent 与自主性](notes/03-workflows-and-autonomy.md)：比较三种执行方式，判断何时适用。
4. [三种执行方式的伪代码](examples/pseudocode.md)：对照控制流；伪代码不可运行。
5. [Coding Agent 教学轨迹](examples/coding-agent-walkthrough.md)：看一次假设的“修复登录 500”过程。

笔记中的短片段用于说明概念；完整伪代码集中在示例页，不重复维护。

## 练习

- [练习题与完成标准](practice/exercises.md)：A/B/C 执行方式判断，以及 MacBook 任务拆解。
- [参考答案](practice/solutions.md)：先独立作答，再对照答案与理由。

## 回顾问题

- 如果模型只返回一次答案，没有读取外部结果，它为什么还不是 agent？
- 一个带 `while` 和多个工具的流程，什么情况下仍然只是 workflow？
- Agent loop 有哪些终止方式？只靠模型说“完成了”足够吗？
- “自主性”与“权限”是什么关系？哪些动作可能按策略需要人工确认？

## 参考

- [课程资源索引](../../resources.md)：官方 2025 材料、2024 补充与工程补充。
- [官方课程主页](https://rdi.berkeley.edu/agentic-ai/f25)（访问日期 2026-10-19）。
- [课程入口](../../README.md)、[M01 大纲](../../syllabus.md#m01) 与 [M05 · Reasoning 与 Planning](../../syllabus.md#m05)。
- [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)、[MCP architecture](https://modelcontextprotocol.io/docs/learn/architecture)：本课工程补充，不是 Berkeley 官方必读。

M01 的后续方向是 Reasoning、Planning 与 Acting 的概览；ReAct 等具体机制在 M05 深入。
