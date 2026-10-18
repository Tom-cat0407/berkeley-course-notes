# berkeley-course-notes

个人整理 Berkeley 课程学习笔记的仓库：按课程归档官方资源索引、课次笔记、示例、练习和本地素材。目标是让每门课的学习路径可复现、内容可检索，而不是堆积零散文件。

> 这是个人学习整理，不是 Berkeley 官方仓库或官方课程网站。课程名称、资料与版权归课程团队及原作者所有。

## 课程导航

课程入口统一维护在 [课程索引](courses/README.md)。当前尚未添加课程；新增课程请遵循索引页的规则。

每门课程的学期版本、官方链接、先修要求、环境配置和课次状态，只在该课程的 `README.md` 中维护。

## 开始方式

1. 克隆仓库：

   ```bash
   git clone https://github.com/Tom-cat0407/berkeley-course-notes.git
   cd berkeley-course-notes
   ```

2. 打开 [courses/README.md](courses/README.md)，选择要学习的课程。
3. 进入 `courses/<course-code>/`，先读课程 README，确认学期版本、环境和先修要求，再按课次目录学习。
4. 课程依赖在该课程目录内单独安装，按该课程 README 的说明运行。

新增课程或课次前，先读 [写作规范](docs/writing-guide.md)，再从 [课程模板](templates/course-readme.md) / [课次模板](templates/lesson-readme.md) 复制并替换占位符；复制命令见课程索引。

## 目录结构

```text
berkeley-course-notes/
├── README.md
├── .gitignore
├── docs/
│   └── writing-guide.md
├── templates/
│   ├── course-readme.md
│   └── lesson-readme.md
└── courses/
    ├── README.md
    └── <course-code>/              # 规划中；当前没有课程
        ├── README.md
        ├── resources.md
        ├── lectures/
        │   └── 01-topic/
        │       ├── README.md
        │       ├── examples/
        │       ├── practice/
        │       └── assets/
        └── labs/ homework/ projects/   # 按需创建，不预建空目录
```

课程内容按 `courses/<course-code>/` 隔离：路径和标识符优先使用英文，目录名以小写短横线为主，说明文字使用中文。每节的示例、练习和素材放在该节课次目录；实验、作业和项目放在课程层。资源链接集中记录在课程的 `resources.md`。
