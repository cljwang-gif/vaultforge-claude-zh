# vaultforge-claude-zh

把任意 Obsidian Vault 变成可被 Claude / Claudian 稳定驱动的结构化项目工作区。

`vaultforge-claude-zh` 是一套通用 `CLAUDE.md` 框架，适合长期写作、小说连载、研究笔记、知识库、产品文档和创作项目。它不是一个插件，而是一套可复制到 Obsidian Vault 的项目操作协议。

## 适合谁

- 用 Obsidian 管理长期项目的人。
- 用 Claude、Claude Code 或 Claudian 协作写作的人。
- 想让 AI 不乱读、不乱改、不乱扩张项目的人。
- 管理小说、研究、课程、产品规格、知识库或创作资料的人。

## 它解决什么问题

长项目中，AI 常见问题包括：

- 读太多无关资料，反而混淆上下文。
- 写作、审稿、更新记忆混在一起。
- 把未来计划当成已发生事实。
- 自动进入下一章、下一任务或下一阶段。
- 角色、实体、伏笔、状态长期不同步。

VaultForge 的目标是让 AI 有清晰边界：

```text
先判断任务
再读取上下文
只处理授权范围
先审查质量
再更新长期记忆
完成当前任务后停止
```

## 快速开始

1. 把根目录的 `CLAUDE.md` 复制到你的 Obsidian Vault 根目录。
2. 把 `templates/` 内的文件复制到你的 Vault。
3. 先填写这些文件：
   - `00_System/ProjectConfig.md`
   - `00_System/ProjectState.md`
   - `00_System/WritingRules.md`
   - `00_System/CharacterRegistry.md`
   - `00_System/EntityRegistry.md`
4. 在 Vault 根目录启动 Claude / Claudian。
5. 先运行只读检查：

```text
请读取 CLAUDE.md 并检查当前 Vault 结构。不要修改任何文件，只报告缺失文件、设置风险和下一步建议。
```

## 核心结构

```text
CLAUDE.md      -> 总控协议
00_System/    -> 项目规则与事实源
09_SKILLS/    -> 岗位行为规范
03_Plot/      -> 主线、支线、伏笔、矛盾、新增信息
05_Outputs/   -> 正文、文章、报告、规格等产出物
06_Review/    -> 审稿、评分、审计和项目更新记录
```

## 推荐工作流

```text
准备上下文
→ 生成或修改产出
→ 检查硬指标
→ 审稿或质量审查
→ 必要时返修
→ 更新长期项目记忆
→ 汇报并停止
```

## 文档

- [架构说明](docs/architecture.md)
- [快速开始](docs/quick-start.md)
- [迁移已有 Vault](docs/migration.md)
- [编写 Skill 文件](docs/skill-authoring.md)
- [常见问题](docs/faq.md)

## 开源协议

MIT License。见 [LICENSE](LICENSE)。

