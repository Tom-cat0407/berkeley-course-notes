# 15 Module 大纲

官方课程主页：[CS294/194-196: Agentic AI, Fall 2025](https://rdi.berkeley.edu/agentic-ai/f25)。下文“2025 官方”均指该页列出的讲次与阅读材料；“2024 补充”指 [Fall 2024 LLM Agents](https://rdi.berkeley.edu/llm-agents/f24) 的公开材料。

来源类型：

- **2025 官方关联**：与 2025 官方讲次或阅读主题对应。
- **2024 课程补充**：2025 课程未单独展开，用 2024 课程材料补足。
- **自学工程补充**：为形成可运行产物而加入的工程练习，不是官方教学安排。

Module 的关键知识点和计划实践按自学需要组织，不逐条对应讲座内容；具体覆盖范围以官方材料为准。每个 Module 的产物都是计划，不是已交付成果。学习状态只在[课程 README](README.md)的模块进度表维护。

## 模块索引

- [M01 · Agentic AI 基础](#m01)
- [M02 · LLM Agent 的模型基础](#m02)
- [M03 · Agent Stack 与基础设施](#m03)
- [M04 · Tools 与 Function Calling](#m04)
- [M05 · Reasoning 与 Planning](#m05)
- [M06 · Memory 与 Context](#m06)
- [M07 · Post-Training for Agents](#m07)
- [M08 · Agent Evaluation](#m08)
- [M09 · Multi-Agent Systems](#m09)
- [M10 · Coding Agents](#m10)
- [M11 · Web / Computer Agents](#m11)
- [M12 · Scientific Agents](#m12)
- [M13 · Production Agent Engineering](#m13)
- [M14 · Agent Safety & Security](#m14)
- [M15 · Final Agent Project](#m15)

<a id="m01"></a>
## M01 · Agentic AI 基础

**来源类型**：2025 官方关联

**目标**：区分 Agent、workflow 与单次 LLM 调用，能描述 agent loop 的组成和数据流。

**关键知识点**：

- AI Agent 的定义与基本结构
- Model / Environment / Observation / Action
- Agent loop
- Reasoning、Planning、Execution
- 单次 LLM 调用、workflow 与 agent 的差异
- Agentic AI 的主要应用场景

**计划实践产物**：画出并解释一张 agent loop 图（User → Agent → Reasoning → Tool / Environment → Observation → Agent → Final Answer），附一段场景对比，说明何时用 workflow、何时用 agent。

**来源**：

- 2025-09-08 Lecture：Introduction（Dawn Song）
- 2025-09-15 Lecture：LLM Agents Overview（Yann Dubois）

<a id="m02"></a>
## M02 · LLM Agent 的模型基础

**来源类型**：2025 官方关联

**目标**：根据任务约束选择模型，解释能力、上下文、延迟和成本之间的取舍。

**关键知识点**：

- Base model、instruct model、chat model、reasoning model
- Context window 与 tokenization
- Sampling、temperature、structured output
- Model selection
- Latency 与 cost
- 开源模型与 API 模型

**计划实践产物**：一份模型选型表，列出 3 个候选模型，按任务类型、上下文长度、结构化输出、延迟和成本打分，并注明假设。不要求深入 Transformer 训练。

**来源**：

- 2025-09-15 Lecture：LLM Agents Overview（Yann Dubois）
- 2025 官方阅读：[Kimi K2](https://rdi.berkeley.edu/agentic-ai/slides/d11.pdf)、[DeepSeek-V3](https://rdi.berkeley.edu/agentic-ai/slides/d22.pdf)

<a id="m03"></a>
## M03 · Agent Stack 与基础设施

**来源类型**：2025 官方关联

**目标**：解释 Agent 系统从应用到基础设施的分层，识别状态、并发、可观测性和成本控制的位置。

**关键知识点**：

- Agent runtime 与 model serving
- API 架构、async execution
- State management 与 agent session
- Observability、logging、traces
- Retry、timeout、rate limits、cost control
- Agent state machine

**计划实践产物**：一张 Agent 系统分层图（Application → Agent Runtime → Model API → Tool Layer → Memory / Retrieval → Infrastructure），加一页故障模式表，记录超时、重试、限流和状态丢失的现象与处理方式。

**来源**：

- 2025-09-22 Lecture：Evolution of system designs from an AI engineer perspective（Yangqing Jia）

<a id="m04"></a>
## M04 · Tools 与 Function Calling

**来源类型**：2024 课程补充 + 自学工程补充

**目标**：实现工具定义、调用、结果回填和错误处理，完成最小 AgentHarness。

**关键知识点**：

- Tool definition 与 function calling
- JSON Schema 与结构化参数
- Tool selection、tool execution、observation、tool result
- Tool retry 与 tool errors

**计划实践产物**：一个 Python AgentHarness，包含 `search()`、`calculator()`、`read_file()` 三个工具，用 `while not finished` 循环完成“模型给出 action → 执行 → 结果写回上下文”的流程；记录一次失败调用及修复过程。

**来源**：

- 2024-09-16 Lecture：LLM agents: brief history and overview（Shunyu Yao）
- 2024 课程主题：tool use
- 本仓库工程练习：三工具 AgentHarness

<a id="m05"></a>
## M05 · Reasoning 与 Planning

**来源类型**：2024 课程补充

**目标**：解释多步推理、任务分解与重规划，比较 ReAct 和 plan-and-execute 两种流程。

**关键知识点**：

- Chain-of-Thought 概念
- ReAct
- Plan-and-execute
- Reflection 与 self-correction
- Search、tree search
- Task decomposition

**计划实践产物**：对同一任务写 ReAct 与 plan-and-execute 两版流程，比较步骤数、失败点和可观测性。用文字或伪代码描述，不要求实现完整系统。

**来源**：

- 2024-09-16 Lecture：LLM agents: brief history and overview（Shunyu Yao）
- 2024 课程主题：reasoning、planning
- 2024 官方阅读：[ReAct](https://arxiv.org/abs/2210.03629)

<a id="m06"></a>
## M06 · Memory 与 Context

**来源类型**：2024 课程补充 + 自学工程补充

**目标**：区分短期、工作、长期、语义和情景记忆，设计记忆的写入、检索与淘汰策略。

**关键知识点**：

- Short-term memory：conversation history
- Working memory：当前任务状态
- Long-term memory：跨 session 保存的信息
- Semantic memory 与 episodic memory
- Embeddings、vector database、retrieval、RAG
- Memory summarization 与 retrieval policy
- 架构：Agent / Context / Working Memory / Long-term Memory / Retrieval

**计划实践产物**：一页记忆架构设计，写明存什么、何时写、何时检索、如何淘汰，并附一个记忆冲突或过期导致失败的案例。

**来源**：

- 2024 课程主题：RAG
- 2025 课程未设单独 Memory 讲次，本 Module 以工程补充为主

<a id="m07"></a>
## M07 · Post-Training for Agents

**来源类型**：2025 官方关联

**目标**：区分“训练会回答问题的模型”和“训练连续执行多步任务的 Agent”，解释可验证奖励与环境反馈的作用。

**关键知识点**：

- SFT、preference learning、RLHF、DPO
- RL for agents
- Verifiable reward
- Tool-use training
- Agent trajectory
- Environment feedback

**计划实践产物**：一页训练目标对比表，加一个可验证任务的奖励设计草案，说明状态、动作、成功条件和可能的奖励作弊方式。不训练模型。

**来源**：

- 2025-09-29 Lecture：Post-Training Verifiable Agents（Jiantao Jiao）
- 2025-10-13 Lecture：Some Challenges and Lessons from Training Agentic Models（Weizhu Chen）
- 2025 官方阅读：[SWE-bench Verified](https://openai.com/index/introducing-swe-bench-verified/)、[BrowseComp](https://openai.com/index/browsecomp/)

<a id="m08"></a>
## M08 · Agent Evaluation

**来源类型**：2025 官方关联

**目标**：把“Agent 很聪明”转成可测量、可比较的指标，并在报告中给出不确定度。

**关键知识点**：

- Success rate、error rate、task completion、exact match
- 平均步骤数、token cost、latency、tool call success
- LLM-as-judge 与 human evaluation
- Tool correctness
- Trajectory evaluation、step-level evaluation、end-to-end evaluation
- Benchmark：SWE-bench、SWE-bench Verified、BrowseComp、WebArena、τ-bench、τ²-bench
- 统计与不确定度：重复运行的均值与方差、标准误、置信区间、误差条、样本量与显著性
- 噪声来源：采样、环境状态、judge 波动

**计划实践产物**：一份评测方案和结果表模板，包含均值、误差条、运行次数、token 成本与延迟；用一个小任务重复运行多次，记录结果波动并解释误差条的含义。

**来源**：

- 2025-10-06 Lecture：Agent Evaluation & Project Overview
- 2025-10-27 Lecture：Predictable Noise in LLM（Sida Wang）
- 2025 官方阅读：[Survey on Evaluation of LLM-based Agents](https://arxiv.org/pdf/2503.16416)、[Adding Error Bars to Evals](https://arxiv.org/pdf/2411.00640)

<a id="m09"></a>
## M09 · Multi-Agent Systems

**来源类型**：2025 官方关联

**目标**：判断 multi-agent 何时优于 single-agent，设计委派、通信和共享状态，并识别协调成本。

**关键知识点**：

- Agent delegation 与 handoff
- Communication、role specialization、debate
- Supervisor pattern
- Swarm / decentralized agents
- Shared memory 与 coordination
- Multi-agent 的失败模式：成本、错误传播、协调开销

**计划实践产物**：一个 supervisor 加 2 个子角色的流程设计，以及与 single-agent 的对照实验方案，比较成功率、步骤数和 token 成本。

**来源**：

- 2025-10-20 Lecture：Multi-Agent AI（Noam Brown）
- 2025-11-17 Lecture：Multi-Agent Systems in the Era of LLMs（Oriol Vinyals）

<a id="m10"></a>
## M10 · Coding Agents

**来源类型**：2024 课程补充 + 2025 官方关联 + 自学工程补充

**目标**：理解 coding agent 的仓库检索、补丁生成、测试执行和失败修复循环。

**关键知识点**：

- Code generation 与 repo navigation
- Code execution、test execution
- Debugging 与 patch generation
- SWE-bench 与 SWE-bench Verified

**计划实践产物**：Mini Coding Agent。接收 issue，检索仓库、读取文件、生成 patch、运行测试并根据错误继续修复；先在一个小仓库上跑通流程，记录每一步的输入、输出和失败点。

**来源**：

- 2024-10-14 Lecture：Agents for Software Development（Graham Neubig）
- 2024 官方阅读：[SWE-agent](https://arxiv.org/abs/2405.15793)、[OpenHands](https://arxiv.org/abs/2407.16741)
- 2025 官方阅读：[SWE-bench Verified](https://openai.com/index/introducing-swe-bench-verified/)

<a id="m11"></a>
## M11 · Web / Computer Agents

**来源类型**：自学工程补充

**目标**：理解浏览器与 GUI agent 的观察空间、动作空间和评估难点，能把研究任务拆成可观测步骤。

**关键知识点**：

- Browser agent 与 GUI agent
- DOM interaction、screenshot reasoning
- Computer use
- Search agent 与 deep research agent
- 任务循环：检索 → 打开页面 → 阅读 → 跟踪链接 → 比较来源 → 生成报告

**计划实践产物**：一个 research agent 的任务分解与来源核对清单，逐步标注页面、引用、失败信号和人工确认点。可借助 WebArena、BrowserGym、OSWorld 设计任务。

**来源**：

- 本仓库工程补充：浏览器 / 计算机操作类 Agent 的流程练习
- 工程参考：[WebArena](https://github.com/web-arena-x/webarena)、[BrowserGym](https://github.com/ServiceNow/BrowserGym)、[OSWorld](https://github.com/xlang-ai/OSWorld)

<a id="m12"></a>
## M12 · Scientific Agents

**来源类型**：2025 官方关联

**目标**：理解 research agent 如何做文献检索、假设生成、实验规划和多 agent 协作。

**关键知识点**：

- Research agent 与 literature search
- Hypothesis generation 与 experiment planning
- Scientific tool use
- Multi-agent research
- Paper → agent

**计划实践产物**：一份论文到 agent 的流程图，说明输入、可用工具、输出和验证点。不实现完整科研系统。

**来源**：

- 2025-11-03 Lecture：AI Agents to Automate Scientific Discoveries（James Zou）
- 2025 官方阅读：[The Virtual Lab of AI agents designs new SARS-CoV-2 nanobodies](https://rdi.berkeley.edu/agentic-ai/f25)、[Paper2Agent](https://arxiv.org/abs/2509.06917)

<a id="m13"></a>
## M13 · Production Agent Engineering

**来源类型**：2025 官方关联

**目标**：把可演示的 agent 提升为可观测、可恢复、成本可控的服务。

**关键知识点**：

- Reliability：retry、fallback、error handling、guardrails、timeout
- Production：logging、tracing、monitoring、cost、latency、caching、rate limiting
- Agent lifecycle：Request → Agent execution → Tool calls → Trace → Evaluation → Failure analysis → Improve prompt / tools / model

**计划实践产物**：一页生产运行手册，包含 SLO、重试与降级策略、trace 字段、成本与延迟预算、故障演练清单。

**来源**：

- 2025-11-10 Lecture：Practical Lessons from Deploying Real-World AI Agents（Clay Bavor）
- 2025 官方阅读：[τ²-Bench](https://arxiv.org/pdf/2506.07982)

<a id="m14"></a>
## M14 · Agent Safety & Security

**来源类型**：2025 官方关联

**目标**：识别 agent 特有的攻击面，设计最小权限、沙箱和人工确认点。

**关键知识点**：

- Prompt injection 与 indirect prompt injection
- Tool poisoning、malicious tools
- Data exfiltration、memory poisoning
- Excessive permissions
- Sandbox、least privilege、human confirmation

**计划实践产物**：一个邮件或网页注入的攻击路径图，加一张对策表，列出权限边界、沙箱位置、人工确认点和日志记录。

**来源**：

- 2025-12-08 Lecture：Agentic AI Safety & Security（Dawn Song）

<a id="m15"></a>
## M15 · Final Agent Project

**来源类型**：2025 官方关联 + 自学工程补充

**目标**：交付 Personal AI Engineering Agent，覆盖工具调用、MCP、规划、记忆、评测、追踪和错误处理。

**关键知识点**：

- 需求分析与架构设计
- Planner 与 agent runtime
- Planning 覆盖 Web search、File search、Code execution、APIs 与 MCP tools
- Tool calling、MCP
- Memory
- Evaluation 与 agent benchmark
- Tracing、error handling
- 文档、架构图与 demo

**计划实践产物**：Personal AI Engineering Agent。交付项：

- tool calling
- MCP
- planning
- memory
- evaluation
- tracing
- error handling
- agent benchmark
- README
- architecture diagram
- demo

候选技术栈（规划用，未实现、未定版）：Python、FastAPI、LLM API、MCP、SQLite 或 PostgreSQL、Qdrant 或 pgvector、Docker、pytest、OpenTelemetry。

**来源**：

- 2025 官方课程项目：3/4 unit 学生的 project 占 70%，包含 proposal、early demo、Green Agent、White Agent 阶段；见[官方课程页](https://rdi.berkeley.edu/agentic-ai/f25)
- 本仓库的 Personal AI Engineering Agent 是自选项目，交付项按本页执行，不等同于官方 Green / White Agent 要求

## 高级扩展：具身智能

2025-12-01 的 Autonomous Agents: Embodiment, Interaction, and Learning（Peter Stone）作为高级扩展阅读，不新增 Module 编号，也不改变 15 个 Module 的划分。建议在 M15 完成后按兴趣选读。
