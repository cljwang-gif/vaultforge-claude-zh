# vaultforge-claude-zh

面向 **Obsidian + Claudian 长篇小说写作** 的 `CLAUDE.md` 项目总控框架。

`vaultforge-claude-zh` 的初衷很明确：让作者可以在 Obsidian Vault 中管理长篇小说资料，并让 Claude / Claudian 按稳定流程协作完成大纲、章节正文、审稿、返修和项目记忆更新。

它不是 Obsidian 插件，也不是自动写作脚本，而是一套可以直接复制进 Vault 的 **小说项目操作协议 + 目录模板 + 岗位 Skill**。

## 为什么需要它？

长篇小说写到几十章、几百章之后，真正困难的不是“让 AI 写一章”，而是让 AI 长期稳定地不乱来：

- 不把未来大纲当成已经发生的正文事实。
- 不擅自进入下一章。
- 不随手新增角色、势力、地点和世界观规则。
- 不把写作、审稿、项目更新混在同一次输出里。
- 不忘记角色状态、伏笔进度、支线数量和章节质量问题。
- 不为了凑字写水文、总结腔、AI 腔。

VaultForge 的目标是给长篇小说项目建立一套“生产秩序”：

```text
先判断岗位
再读取上下文
只处理当前授权章节
先写作
再审稿
必要时返修
通过后更新长期记忆
完成当前章后停止
```

## 适合谁

- 用 Obsidian 管理小说设定、角色卡、大纲和章节正文的作者。
- 使用 Claudian / Claude 辅助写长篇小说、网文或系列故事的人。
- 正在做 50 章、100 章、300 章以上长项目的人。
- 想把“写正文、审稿、更新设定”拆成稳定流程的人。
- 想让 AI 按规则协作，而不是每次重新解释项目背景的人。

也可以改造用于研究笔记、产品文档和知识库项目，但本仓库的第一目标是 **长篇小说创作**。

## 它提供什么

- `CLAUDE.md`：项目总控协议，负责权限、路由、上下文读取和停止条件。
- `templates/00_System/`：小说项目配置、当前状态、写作规则、语言规则、角色索引和实体索引。
- `templates/03_Plot/`：主线、支线、伏笔、新增信息池和矛盾清单。
- `templates/09_SKILLS/`：规划、写作、审稿、项目更新和审计五个岗位 Skill。
- `templates/06_Review/`：章节评分、审稿记录和新增信息审查。
- `examples/minimal-vault/`：最小示例 Vault。
- `docs/`：架构、快速开始、迁移和 Skill 编写说明。

## 核心思想

把 AI 从“万能写手”拆成多个岗位：

```text
CreateOutline   -> 剧情规划
WriteChapter    -> 正文写作
ReviewChapter   -> 严格审稿
UpdateProject   -> 项目记忆更新
AuditProject    -> 阶段审计
```

每个岗位只做自己的事。

写手不更新设定，审稿人不擅自改正文，项目管理员不扩写剧情。这样可以降低长篇项目里最常见的上下文污染和设定漂移。

## 推荐小说工作流

单章完整闭环：

```text
读取 CLAUDE.md
→ 判断当前任务是第几章
→ 读取当前章纲、上一章结尾、相关角色和伏笔
→ WriteChapter 生成正文
→ ReviewChapter 审稿评分
→ 必要时返修
→ 通过后 UpdateProject 更新角色、实体、主线、支线、伏笔
→ 汇报字数、评分、修改文件和待确认事项
→ 停止，不自动进入下一章
```

新增信息生命周期：

```text
发现 → 捕获 → 分级 → 登记 → 观察 → 升级 / 休眠 / 废弃
```

这可以防止 AI 写着写着就把一个临时路人、临时地点或临时设定升级成长篇核心设定。

## 快速开始

1. 把根目录的 `CLAUDE.md` 复制到你的小说 Obsidian Vault 根目录。
2. 把 `templates/` 内的文件复制到你的 Vault。
3. 先填写这些文件：
   - `00_System/ProjectConfig.md`
   - `00_System/ProjectState.md`
   - `00_System/WritingRules.md`
   - `00_System/LanguageRules.md`
   - `00_System/CharacterRegistry.md`
   - `00_System/EntityRegistry.md`
   - `03_Plot/Mainline.md`
   - `03_Plot/Foreshadowing.md`
4. 在 Vault 根目录启动 Claudian / Claude。
5. 先运行只读检查：

```text
请读取 CLAUDE.md 并检查当前小说 Vault 结构。不要修改任何文件，只报告缺失文件、设置风险和下一步建议。
```

然后可以从一个小任务开始：

```text
请根据 CLAUDE.md，只规划第 1 章。不要写正文。
```

或：

```text
请完整执行第 1 章闭环：准备上下文、写正文、审稿、必要时返修、通过后更新项目记忆，然后停止。
```

## 推荐目录结构

```text
CLAUDE.md

00_System/
  ProjectConfig.md       # 小说基本配置
  ProjectState.md        # 当前进度与授权状态
  WritingRules.md        # 本书写作规则
  LanguageRules.md       # 通用语言规则
  PlatformRules.md       # 平台规则
  CharacterRegistry.md   # 角色索引
  EntityRegistry.md      # 地点、势力、物品、能力等索引

01_World/                # 世界观、能力体系
02_Characters/           # 角色卡
03_Plot/                 # 主线、支线、伏笔、新增信息、矛盾
04_Plans/                # 卷纲、章纲
05_Outputs/              # 章节正文
06_Review/               # 审稿、评分、项目更新记录
07_Templates/            # 模板
08_Archive/              # 归档
09_SKILLS/               # 岗位 Skill
10_WritingSupport/       # 可选写作支持包
```

## 文档

- [架构说明](docs/architecture.md)
- [快速开始](docs/quick-start.md)
- [迁移已有 Vault](docs/migration.md)
- [编写 Skill 文件](docs/skill-authoring.md)
- [常见问题](docs/faq.md)

## 当前状态

`v0.1.0` 是中文版初始发布，重点提供：

- 通用小说项目 `CLAUDE.md`
- Obsidian Vault 模板
- 五个基础岗位 Skill
- 最小示例 Vault
- 中文使用文档

后续计划：

- 增加长篇小说专用完整示例 Vault。
- 增加网文连载场景模板。
- 增加角色、伏笔、支线审计示例。
- 增加一键初始化脚本。

## 开源协议

MIT License。见 [LICENSE](LICENSE)。

