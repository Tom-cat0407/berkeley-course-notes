<!--
模板使用说明（复制到课程目录后删除本段）：

在仓库根目录执行，变量值需替换为真实课程信息：
course_code='替换为课程代码'
mkdir -p "courses/$course_code"
cp templates/course-readme.md "courses/$course_code/README.md"

将全部 `{{...}}` 替换为真实内容；不适用的小节直接删除。
模板中的路径和 URL 只放在代码块或行内代码中，实例化后再改成 Markdown 链接，
以免复制前产生坏链接。

常用变量：
`{{COURSE_CODE}}` 课程代码 | `{{COURSE_NAME}}` 课程名称 | `{{SEMESTER}}` 学期
`{{COURSE_VERSION}}` 课程版本/年份 | `{{OFFICIAL_URL}}` 官方主页 | `{{PREREQUISITES}}` 先修
`{{TOOLCHAIN}}` 语言与工具版本 | `{{INSTALL_COMMAND}}` 安装命令
`{{RUN_COMMAND}}` 运行/验证命令 | `{{NN}}` 课次序号 | `{{TOPIC_SLUG}}` 课次英文短名
`{{STATUS}}` 课次状态
-->

# {{COURSE_CODE}} · {{COURSE_NAME}}

## 学期与版本

- 学期：{{SEMESTER}}
- 课程版本/年份：{{COURSE_VERSION}}
- 记录周期：{{START_DATE}} 至 {{LAST_UPDATED}}
- 官方主页：`{{OFFICIAL_URL}}`

## 官方链接

- 课程主页：`{{OFFICIAL_URL}}`
- 课程平台/公告：`{{COURSE_PLATFORM_URL}}`
- 教学大纲：`{{SYLLABUS_URL}}`
- 资源索引：`resources.md`

## 先修知识

{{PREREQUISITES}}

## 环境与依赖

- 语言/工具：{{TOOLCHAIN}}
- 安装依赖：`{{INSTALL_COMMAND}}`
- 运行/验证：`{{RUN_COMMAND}}`
- 依赖说明：{{DEPENDENCY_NOTES}}

依赖与运行方式记录在课程目录内。环境变量只提交 `.env.example`，不要提交真实 `.env` 或密钥。

## 目录结构

```text
courses/{{COURSE_CODE}}/
├── README.md
├── resources.md
├── lectures/
│   └── {{NN}}-{{TOPIC_SLUG}}/
│       ├── README.md
│       ├── examples/
│       ├── practice/
│       └── assets/
└── labs/ homework/ projects/   # 课程层，按需创建
```

## 课次目录

课次目录使用 `lectures/{{NN}}-{{TOPIC_SLUG}}/README.md`：`{{NN}}` 从 `01` 开始补零，`{{TOPIC_SLUG}}` 使用英文小写短横线。依据真实教学大纲登记课次；未开始的课次也可以先登记，状态据实填写。

| 课次 | 主题 | 笔记路径 | 状态 |
| --- | --- | --- | --- |
| {{NN}} | {{TOPIC_TITLE}} | `lectures/{{NN}}-{{TOPIC_SLUG}}/README.md` | {{STATUS}} |

## 资源与素材

- 课程资源、教材和工具链链接维护在 `resources.md`。
- 本地图片、数据和其他素材放在对应课次的 `assets/` 目录，笔记中使用相对路径引用。
- 只提交有权使用的材料；受版权保护的内容优先链接官方页面。

## 备注

{{NOTES}}
