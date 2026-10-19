# CS294/194-196 · Agentic AI（Fall 2025）

- 课程：UC Berkeley CS294/194-196: Agentic AI
- 学期：Fall 2025
- 教师：Dawn Song
- 官方主页：[rdi.berkeley.edu/agentic-ai/f25](https://rdi.berkeley.edu/agentic-ai/f25)
- 仓库目录：`courses/cs294-196/`

官方课程同时使用 CS294-196 与 CS194-196 两个代码；本仓库目录取 `cs294-196`。

## 课程说明

课程覆盖 Agentic AI 的基础概念（LLM、reasoning、planning、agent 框架与基础设施）、代表性应用（代码生成、机器人、Web 自动化、科学发现），以及当前 LLM agent 的限制与风险。

本仓库把官方课程材料重组为 15 个自学 Module，并整理成 10 阶段学习路线。Module 是本仓库的自学单元，官方 Lecture 是内容来源；15 个 Module 与 10 个阶段不是官方排课，学习顺序按本仓库路线执行。

## 导航

- [15 Module 大纲](syllabus.md)：每个 Module 的目标、关键知识点、计划产物与来源。
- [10 阶段学习路线](roadmap.md)：主线顺序、应用分支和高级扩展的插入时机。
- [资源索引](resources.md)：官方 2025 材料、2024 补充与本仓库工程补充。
- [第 1 课：Agentic AI 基础](lectures/01-agentic-ai-fundamentals/README.md)：M01 的首课入口。

## 先修知识

官方建议在选课前具备机器学习与深度学习的基础，例如修过 CS182、CS188、CS189 等课程。

自学本仓库路线还需要 Python 与 Git 基础。这是本仓库对自学方式的建议；官方先修要求以课程主页为准。

## 模块进度

本表是仓库内学习状态的唯一来源。开始学习后在此更新状态，不在 `syllabus.md`、`roadmap.md` 或课次笔记中重复维护。

| Module | 主题 | 大纲 | 状态 |
| --- | --- | --- | --- |
| M01 | Agentic AI 基础 | [大纲](syllabus.md#m01) | 进行中 |
| M02 | LLM Agent 的模型基础 | [大纲](syllabus.md#m02) | 未开始 |
| M03 | Agent Stack 与基础设施 | [大纲](syllabus.md#m03) | 未开始 |
| M04 | Tools 与 Function Calling | [大纲](syllabus.md#m04) | 未开始 |
| M05 | Reasoning 与 Planning | [大纲](syllabus.md#m05) | 未开始 |
| M06 | Memory 与 Context | [大纲](syllabus.md#m06) | 未开始 |
| M07 | Post-Training for Agents | [大纲](syllabus.md#m07) | 未开始 |
| M08 | Agent Evaluation | [大纲](syllabus.md#m08) | 未开始 |
| M09 | Multi-Agent Systems | [大纲](syllabus.md#m09) | 未开始 |
| M10 | Coding Agents | [大纲](syllabus.md#m10) | 未开始 |
| M11 | Web / Computer Agents | [大纲](syllabus.md#m11) | 未开始 |
| M12 | Scientific Agents | [大纲](syllabus.md#m12) | 未开始 |
| M13 | Production Agent Engineering | [大纲](syllabus.md#m13) | 未开始 |
| M14 | Agent Safety & Security | [大纲](syllabus.md#m14) | 未开始 |
| M15 | Final Agent Project | [大纲](syllabus.md#m15) | 未开始 |

## 课次目录

| 课次 | 所属 Module | 主题 | 入口 |
| --- | --- | --- | --- |
| 01 | M01 | Agentic AI 基础 | [01-agentic-ai-fundamentals](lectures/01-agentic-ai-fundamentals/README.md) |

课次只登记实际存在的目录；首课只是 M01 的开始，不代表整个 Module 完成。

## 环境与依赖

当前课次包含概念笔记、伪代码和教学轨迹，暂无可运行代码，因此不记录安装命令或依赖版本。首次加入可运行示例时，在本节补充实际环境、安装命令和验证方式。

## 后续课次写作约定

- 具体课次放在 `lectures/NN-topic/`，`NN` 从 `01` 开始补零，`topic` 使用英文小写短横线。
- 课次 README 记录所属 Module 与官方来源，包括官方讲次、日期和材料链接。
- 长课用短 README 作入口，正文按主题放在 `notes/`；短课可以只有一页 README。
- `notes/`、`examples/`、`practice/`、`assets/` 与课次 README 同目录，按需创建；练习题目与答案分文件。
- 目录在实际开始写该课次时建立，不为 15 个 Module 预建空文件夹。
- 课次笔记不维护完成状态；状态回到本页的模块进度表。

## 下一步

从 [第 1 课：Agentic AI 基础](lectures/01-agentic-ai-fundamentals/README.md) 开始，按课次 README 的阅读顺序学习。M01 的后续方向是 Reasoning、Planning 与 Acting 的概览；ReAct 等具体机制在 [M05](syllabus.md#m05) 深入。完成 M01 的计划产物后，在本页表格更新状态。
