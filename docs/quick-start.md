# 快速开始

## 1. 复制文件

把根目录的 `CLAUDE.md` 复制到你的 Obsidian Vault 根目录。

然后把 `templates/` 里的内容复制到同一个 Vault。

## 2. 填写必要系统文件

先填写：

- `00_System/ProjectConfig.md`
- `00_System/ProjectState.md`
- `00_System/WritingRules.md`
- `00_System/CharacterRegistry.md`
- `00_System/EntityRegistry.md`

一开始不需要写得很完整。先写当前任务需要的最小事实。

## 3. 先做只读检查

使用这个提示词：

```text
请读取 CLAUDE.md 并检查当前 Vault 结构。不要修改任何文件。请报告缺失文件、设置风险和接下来的三步建议。
```

## 4. 运行小测试

写作项目：

```text
根据 CLAUDE.md，为第一个产出创建一页规划。先不要写正文。
```

研究项目：

```text
根据 CLAUDE.md，审阅当前资料笔记并提出综合结构。不要修改文件。
```

## 5. 进入完整闭环

当基础设置可用后：

```text
完整执行当前授权产出：准备上下文、生成草稿、审查质量、必要时返修、更新项目记忆，然后停止。
```

默认只处理当前一个任务单元。

