# 课程索引

本目录按课程代码收录个人 Berkeley 课程学习笔记。当前尚未添加课程。

## 课程列表

添加课程后，在此登记课程入口和学期版本；单门课程的详细状态只在其课程 README 维护。

| 课程代码 | 课程名称 | 学期/版本 | 笔记入口 |
| --- | --- | --- | --- |
| — | — | — | 暂无课程 |

## 课程目录结构

```text
courses/<course-code>/
├── README.md              # 课程入口：学期、官方链接、先修、环境、课次与状态
├── resources.md           # 官方链接、教材、工具和本地资源索引
├── lectures/
│   └── NN-topic/
│       ├── README.md      # 单次课笔记
│       ├── examples/      # 可运行示例或推导材料，按需
│       ├── practice/      # 练习、提示与解答，按需
│       └── assets/        # 图片、数据等本地素材，按需
└── labs/ homework/ projects/   # 课程层，仅在有真实内容时创建
```

## 新增课程规则

1. 只登记真实存在的课程，不创建示例课程或空占位目录。
2. 课程目录使用官方课程代码的小写英文形式：`courses/<course-code>/`。目录名优先使用英文小写短横线；`README.md` 及语言/工具的标准文件名按惯例保留。
3. 在仓库根目录从 [课程模板](../templates/course-readme.md) 创建课程入口：

   ```bash
   course_code='替换为课程代码'
   mkdir -p "courses/$course_code"
   cp templates/course-readme.md "courses/$course_code/README.md"
   ```

4. 填写课程 README 中的学期版本、官方链接、先修知识、环境与依赖，并删除模板说明和不适用的占位内容。
5. 课次按 `lectures/NN-topic/README.md` 组织，`NN` 从 `01` 开始补零，`topic` 使用英文小写短横线。可依据真实教学大纲提前登记未开始课次，完成状态据实填写。课次内容从 [课次模板](../templates/lesson-readme.md) 创建，以下命令同样在仓库根目录执行：

   ```bash
   course_code='替换为课程代码'
   lesson_slug='01-topic'
   mkdir -p "courses/$course_code/lectures/$lesson_slug"
   cp templates/lesson-readme.md "courses/$course_code/lectures/$lesson_slug/README.md"
   ```

6. `examples/`、`practice/`、`assets/` 放在对应课次目录，与课次 README 并列，按需创建；`labs/`、`homework/`、`projects/` 位于课程目录，按需创建。不要用空目录或 `.gitkeep` 占位。
7. 依赖按课程管理，在课程目录内记录安装与运行方式。
8. 课次状态只在课程 README 的课次目录维护，课次笔记与根 README 不重复记录。
9. `resources.md` 用于集中记录官方主页、教材、工具链和本地素材；引用受版权保护的材料时优先链接官方来源并注明出处。
10. 新增后把课程追加到上方课程列表，并在提交前检查所有 Markdown 本地链接。写作与引用细节见 [写作规范](../docs/writing-guide.md)。

## 新增课程检查清单

- [ ] 课程与课次来自真实教学安排，完成状态与实际一致。
- [ ] 模板占位符已替换，课程目录层级与命名符合约定。
- [ ] 官方链接可访问，本地相对链接可解析。
- [ ] 环境安装命令实际执行过，运行结果与笔记一致。
- [ ] 未提交 `.env`、密钥、虚拟环境、依赖目录或构建产物。
