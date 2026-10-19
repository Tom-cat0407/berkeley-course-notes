<!--
模板使用说明（复制到课次目录后删除本段）：

在仓库根目录执行：
course_code='替换为课程代码'
lesson_slug='01-topic'
mkdir -p "courses/$course_code/lectures/$lesson_slug"
cp templates/lesson-readme.md "courses/$course_code/lectures/$lesson_slug/README.md"

先选定一种组织方式，再删除未用部分：
- 短课：只保留本 README，删除“阅读顺序”整节，把正文写入“核心讲解（短课使用）”。
- 长课：README 只保留目标、前置、阅读顺序、练习、回顾和参考入口，删除“核心讲解（短课使用）”；
  正文按主题放入 `notes/`，每篇笔记自行加回课次入口和前后篇导航。

可选段落标有“（可选）”；没有对应内容时整段删除。
`{{MODULE}}` 仅用于按 Module 组织的课程；未采用 Module 时删除对应行。
替换全部 `{{...}}` 占位符；模板中的路径只放在行内代码或代码块中，
实例化后再改成相对链接，避免复制前出现坏链接。

常用变量：
`{{COURSE_CODE}}` | `{{NN}}` | `{{TOPIC_SLUG}}` | `{{TOPIC_TITLE}}`
`{{MODULE}}` | `{{SOURCE_MATERIAL}}` | `{{OBJECTIVE_N}}`
`{{NOTE_FILE}}` | `{{EXAMPLE_FILE}}` | `{{EXERCISE_FILE}}` | `{{SOLUTION_FILE}}`
`{{REFERENCE_TITLE}}` | `{{REFERENCE_URL}}` | `{{ACCESS_DATE}}`
-->

# {{NN}} · {{TOPIC_TITLE}}

> 所属课程：`{{COURSE_CODE}}`（个人自学课次）
>
> 所属 Module：`{{MODULE}}`（可选）
>
> 官方关联：`{{SOURCE_MATERIAL}}`

用一两句话说明本课要解决的问题，以及这是个人整理而非官方讲义。

## 学习目标

完成本课次后，能够：

- {{OBJECTIVE_1}}
- {{OBJECTIVE_2}}
- {{OBJECTIVE_3}}

## 前置知识（可选）

- {{PREREQUISITE_1}}

## 阅读顺序（长课使用）

1. `notes/{{NOTE_FILE}}`：{{NOTE_PURPOSE}}
2. `examples/{{EXAMPLE_FILE}}`：{{EXAMPLE_PURPOSE}}
3. `practice/{{EXERCISE_FILE}}`：题目与完成标准。

长课时这里只列入口；短课删除本节。

## 核心讲解（短课使用）

### {{CONCEPT_1}}

{{EXPLANATION_1}}

### {{CONCEPT_2}}

{{EXPLANATION_2}}

长课删除本节，正文写入 `notes/`；每篇笔记加回课次入口和前后篇导航。

## 示例 / 推导（可选）

- 问题：{{PROBLEM}}
- 思路：{{APPROACH}}
- 关键步骤：{{STEPS}}
- 结论：{{CONCLUSION}}

完整代码或伪代码放 `examples/`，正文只保留必要短片段。伪代码要标注未实现、不可运行。

## 运行方式与预期结果（可选）

有可运行代码时填写；没有时整段删除。

- 工作目录：`courses/{{COURSE_CODE}}/lectures/{{NN}}-{{TOPIC_SLUG}}`
- 依赖安装：`{{INSTALL_COMMAND}}`
- 运行命令：`{{RUN_COMMAND}}`

预期输出：

```text
{{EXPECTED_OUTPUT}}
```

结果必须是实际输出；未运行时明确标注。

## 易错点（可选）

- {{PITFALL_1}}：{{WHY_AND_FIX_1}}

## 练习

- 题目与完成标准：`practice/{{EXERCISE_FILE}}`
- 参考答案：`practice/{{SOLUTION_FILE}}`

## 回顾

- [ ] {{REVIEW_QUESTION_1}}
- [ ] {{REVIEW_QUESTION_2}}

## 参考

- {{REFERENCE_TITLE}}：`{{REFERENCE_URL}}`
- 访问日期：`{{ACCESS_DATE}}`

官方材料与个人理解分开标注。
