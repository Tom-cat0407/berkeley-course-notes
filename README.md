# berkeley-course-notes

个人整理 Berkeley 课程学习笔记的仓库：按课程归档官方资源索引、课次笔记、示例、练习和本地素材。仓库采用多课程结构，每门课程独立维护学期版本、学习路线和进度。

> 这是个人学习整理，不是 Berkeley 官方仓库或官方课程网站。课程名称、资料与版权归课程团队及原作者所有。

## 为什么建立这个仓库

[序：从使用 AI，到系统学习](docs/preface.md)

记录我使用 AI 的经历、建立这个仓库的初衷，以及接下来系统学习大模型与 Agent 的方向。

## 当前课程

[CS294-196 / CS194-196 · Agentic AI](courses/cs294-196/README.md) · Fall 2025

- [课程入口与模块进度](courses/cs294-196/README.md)
- [15 Module 大纲](courses/cs294-196/syllabus.md)
- [10 阶段学习路线](courses/cs294-196/roadmap.md)
- [资源索引](courses/cs294-196/resources.md)

课程入口是学习状态的唯一来源，大纲和路线不重复记录进度。

## 课程导航

所有课程登记在[课程索引](courses/README.md)。当前已登记 1 门课程，后续课程按同一结构追加。

每门课程的学期版本、官方链接、先修要求、环境配置和课次状态，只在该课程的 `README.md` 中维护。

## 开始方式

1. 克隆仓库：

   ```bash
   git clone https://github.com/Tom-cat0407/berkeley-course-notes.git
   cd berkeley-course-notes
   ```

2. 打开[课程索引](courses/README.md)，选择要学习的课程。
3. 进入 `courses/<course-code>/`，先读课程 README，按其中的导航开始学习。
4. 课次笔记在开始写作后按 `lectures/NN-topic/` 建立；当前课程的入口与下一步见其 README。

新增课程或课次前，从[课程模板](templates/course-readme.md) / [课次模板](templates/lesson-readme.md) 复制并替换占位符；复制命令见课程索引。

## 目录结构

```text
berkeley-course-notes/
├── README.md
├── .gitignore
├── docs/
│   └── preface.md
├── templates/
│   ├── course-readme.md
│   └── lesson-readme.md
└── courses/
    ├── README.md
    └── cs294-196/
        ├── README.md
        ├── syllabus.md
        ├── roadmap.md
        ├── resources.md
        └── lectures/              # 后续按需创建
```

课程内容按 `courses/<course-code>/` 隔离：路径和标识符优先使用英文，目录名以小写短横线为主，说明文字使用中文。每节的示例、练习和素材放在该节课次目录；实验、作业和项目放在课程层。资源链接集中记录在课程的 `resources.md`。
