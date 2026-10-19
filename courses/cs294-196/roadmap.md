# 10 阶段学习路线

10 阶段主线覆盖 11 个 Module（M01、M02、M03、M04、M05、M06、M08、M09、M13、M14、M15）；另外 4 个 Module 作为应用分支（M10、M11）或高级扩展（M07、M12）。阶段与 Module 都是本仓库的自学结构，不是官方排课；官方讲次是内容来源。进度只在[课程 README](README.md)维护，本页不设状态表。

## 主线

| 阶段 | 主题 | Module | 小产物 |
| --- | --- | --- | --- |
| 1 | Agent Fundamentals | [M01](syllabus.md#m01) | agent loop 图与 workflow / agent 对比说明 |
| 2 | LLM for Agents | [M02](syllabus.md#m02) | 3 个候选模型的选型表 |
| 3 | Agent Infrastructure | [M03](syllabus.md#m03) | 系统分层图与故障模式表 |
| 4 | Tools + Function Calling | [M04](syllabus.md#m04) | 三工具 AgentHarness |
| 5 | Reasoning + Planning | [M05](syllabus.md#m05) | ReAct 与 plan-and-execute 流程对比 |
| 6 | Memory + RAG | [M06](syllabus.md#m06) | 记忆架构一页纸与失败案例 |
| 7 | Agent Evaluation | [M08](syllabus.md#m08) | 带误差条的评测方案与结果表 |
| 8 | Multi-Agent | [M09](syllabus.md#m09) | supervisor + 2 个子角色的对照实验方案 |
| 9 | Production + Safety | [M13](syllabus.md#m13) + [M14](syllabus.md#m14) | 生产运行手册与注入攻击对策表 |
| 10 | Final Agent Project | [M15](syllabus.md#m15) | Personal AI Engineering Agent 及全部交付项 |

顺序关系：

- **先评估，后多 Agent。** 阶段 7 先建立成功率、成本和误差范围；没有这组基线，阶段 8 无法判断 multi-agent 是否真的优于 single-agent。
- 阶段 10 以阶段 4 的工具循环、阶段 6 的记忆设计和阶段 7 的评测结果为输入。

阶段之间可以按已有基础调整。判定一个阶段是否继续往下走，看小产物能否独立复现或解释，并能指出至少一个失败模式；阶段 7 之后还要能用数据回答“这个改动是否提升了成功率”。

## 应用分支：M10 / M11

插入时机：主线阶段 8（M09）之后、阶段 9（M13 + M14）之前。两个分支都依赖 M04 的工具循环和 M08 的评测，可按方向选做。

- **M10 Coding Agents**：小产物是 Mini Coding Agent。先在小仓库跑通 issue → 检索 → 读文件 → patch → 测试 → 修复的循环。M10 也为 M15 的代码执行、benchmark 和 tracing 提供实现经验。
- **M11 Web / Computer Agents**：小产物是 research agent 的任务分解与来源核对清单，重点是页面观察、引用核对和人工确认点。

如果目标是先跑完主线，可以把 M10 / M11 推迟到 M15 之后；M15 的交付项不依赖这两个分支全部完成。

## 高级扩展：M07 / M12 / 具身智能

- **M07 Post-Training for Agents**：在阶段 7（M08）之后插入；若做 M10，放在 M10 之后、阶段 9 之前。先有评测基线和可验证任务，再看 SFT、RL 与 verifiable reward。小产物是训练目标对比表和奖励设计草案。
- **M12 Scientific Agents**：在阶段 10（M15）之后作为高级阅读；关注科研方向时可在阶段 8（M09）之后提前插入。小产物是论文到 agent 的流程图与验证点。
- **具身智能**：在 M15 之后选读 2025-12-01 的 Autonomous Agents: Embodiment, Interaction, and Learning。它不占 Module 编号，也没有必修产物。

高级扩展不改变主线的 10 个阶段，也不把 15 个 Module 扩成 16 个。

## 建议顺序

建议顺序：阶段 1–6 → 阶段 7（M08）→ 阶段 8（M09）→ M10 → 阶段 9（M13 + M14）→ 阶段 10（M15）。M11 按方向穿插在 M10 前后；M07 放在 M10 之后；M12 与具身智能放在 M15 之后。

## Module 覆盖核对

- 主线（11 个）：M01、M02、M03、M04、M05、M06、M08、M09、M13、M14、M15
- 应用分支（2 个）：M10、M11
- 高级扩展（2 个）：M07、M12

合计 15 个 Module。具身智能是高级扩展主题，不占 Module 编号。
