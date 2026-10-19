# 伪代码：单次调用、Workflow 与 Agent Loop

> [← 课次入口](../README.md) · 上一篇：[Workflow、Agent 与自主性](../notes/03-workflows-and-autonomy.md) · 下一篇：[Coding Agent 教学轨迹](coding-agent-walkthrough.md)

以下为 Python 风格伪代码，辅助函数未实现，不能直接运行；用它们对照三种控制流。

## 单次 LLM 调用

```python
def answer_once(question: str) -> str:
    prompt = build_prompt(question)  # 未实现：拼装上下文
    return call_llm(prompt)          # 未实现：一次模型调用
```

没有循环，也没有根据外部结果改变下一步。适合答案能由一次生成完成的任务。如果产品在模型外接了检索或工具，就要看那些步骤是否由模型动态决定，不能只看这一次调用的形状。

## PDF Workflow（路径由代码预先定义）

```python
def summarize_pdf(pdf_path: str) -> str:
    text = extract_text(pdf_path)  # 未实现：读取 PDF
    if not text.strip():           # 预定义分支：扫描件改走 OCR
        text = ocr_pdf(pdf_path)   # 未实现

    summary = call_llm(build_summary_prompt(text))               # 未实现
    translation = call_llm(build_translation_prompt(summary))    # 未实现
    save_text(translation, "summary.txt")                        # 未实现
    return translation
```

模型参与生成，但下一步走向由代码决定。这里只画了一个分支；workflow 也可以写循环、并行和重试，只要路径是开发者预先定义的。

<a id="agent-loop"></a>
## Agent Loop（模型决定下一步）

```python
def run_agent(goal: str, max_steps: int = 8) -> dict:
    state = {"goal": goal, "history": []}

    for step in range(1, max_steps + 1):
        action = choose_next_action(state)  # 未实现：模型根据状态选择行动

        if action.kind == "finish":         # 显式终止：模型判断目标已完成
            return {
                "status": "completed",
                "result": action.result,
                "steps": step,
            }

        observation = execute_action(action)  # 未实现：执行工具；失败也应作为观察返回
        state["history"].append({
            "action": action,
            "observation": observation,
        })

    return {"status": "step_limit", "result": None, "steps": max_steps}  # 步数用尽
```

`choose_next_action` 读取目标、历史行动、观察和约束，选择下一步；`execute_action` 把行动作用到环境。循环有两个显式出口：完成时返回 `completed`，步数用尽时返回 `step_limit`。

真实实现还要处理超时、权限和无效工具参数，并把工具异常转成可处理的观察或停止信号。

工具循环、推理规划和生产化分别见 [M04 · Tools 与 Function Calling](../../../syllabus.md#m04)、[M05](../../../syllabus.md#m05) 和 [M13](../../../syllabus.md#m13)。
