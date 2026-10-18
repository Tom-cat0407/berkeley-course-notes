<!--
模板使用说明（复制到课次目录后删除本段）：

在仓库根目录执行，变量值需替换为真实课程与课次信息：
course_code='替换为课程代码'
lesson_slug='01-topic'
mkdir -p "courses/$course_code/lectures/$lesson_slug"
cp templates/lesson-readme.md "courses/$course_code/lectures/$lesson_slug/README.md"

将全部 `{{...}}` 替换为真实内容；没有运行示例时可删除“运行方式与预期结果”。
模板中的路径和 URL 只放在代码块或行内代码中，实例化后再改成相对链接，
以免复制前产生坏链接。

常用变量：
`{{COURSE_CODE}}` 课程代码 | `{{NN}}` 课次序号 | `{{TOPIC_SLUG}}` 课次英文短名
`{{TOPIC_TITLE}}` 课次标题 | `{{SOURCE_MATERIAL}}` 对应课件/教材位置
`{{INSTALL_COMMAND}}` 安装命令 | `{{RUN_COMMAND}}` 运行命令
-->

# {{NN}} · {{TOPIC_TITLE}}

> 所属课程：`{{COURSE_CODE}}` · 对应材料：`{{SOURCE_MATERIAL}}`

## 学习目标

完成本课次后，能够：

- {{OBJECTIVE_1}}
- {{OBJECTIVE_2}}
- {{OBJECTIVE_3}}

## 前置知识

- {{PREREQUISITE_1}}
- {{PREREQUISITE_2}}

如果前置内容记不清，先回到对应课次：`../{{PREV_NN}}-{{PREV_TOPIC_SLUG}}/README.md`。

## 核心讲解

### {{CONCEPT_1}}

{{EXPLANATION_1}}

### {{CONCEPT_2}}

{{EXPLANATION_2}}

写清楚“是什么、为什么这样设计、什么时候适用”，不要只罗列定义。

## 示例 / 推导

### 示例 1：{{EXAMPLE_TITLE}}

- 问题：{{PROBLEM}}
- 思路：{{APPROACH}}
- 关键步骤：{{STEPS}}
- 结论：{{CONCLUSION}}

```text
{{CODE_OR_DERIVATION}}
```

### 示例 2（可选）：{{EXAMPLE_TITLE_2}}

{{EXAMPLE_2}}

## 运行方式与预期结果

适用于有可运行代码或实验的课次；没有时删除本节，或写“本课次无运行示例”。

- 工作目录：`courses/{{COURSE_CODE}}/lectures/{{NN}}-{{TOPIC_SLUG}}`
- 依赖安装：`{{INSTALL_COMMAND}}`
- 运行命令：`{{RUN_COMMAND}}`

预期输出：

```text
{{EXPECTED_OUTPUT}}
```

记录实际使用的版本和平台；预期结果应与真实运行一致，未验证时明确标注。

## 易错点

- {{PITFALL_1}}：{{WHY_AND_FIX_1}}
- {{PITFALL_2}}：{{WHY_AND_FIX_2}}

## 练习

1. {{EXERCISE_1}}
2. {{EXERCISE_2}}

练习文件放在本课次目录的 `practice/`；参考答案或提示说明位置，例如：`practice/{{EXERCISE_FILE}}`。

## 回顾

- [ ] 能用自己的话解释：{{REVIEW_QUESTION_1}}
- [ ] 能独立完成：{{REVIEW_QUESTION_2}}
- [ ] 仍不清楚、需要回看：{{REVIEW_QUESTION_3}}

## 参考

- {{REFERENCE_1_TITLE}}：`{{REFERENCE_1_URL}}`
- {{REFERENCE_2_TITLE}}：`{{REFERENCE_2_URL}}`
- 对应课件/教材位置：`{{SOURCE_LOCATION}}`

官方材料与个人理解分开标注；引用外部内容时标明来源和访问日期。
