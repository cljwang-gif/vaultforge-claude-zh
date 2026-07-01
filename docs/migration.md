# 迁移已有 Vault

本指南用于把 `vaultforge-claude-zh` 接入一个已经存在的 Obsidian Vault。

## 第一步：添加总控协议

把 `CLAUDE.md` 复制到 Vault 根目录。

## 第二步：添加系统文件

创建 `00_System/`，并添加：

- `ProjectConfig.md`
- `ProjectState.md`
- `WritingRules.md`
- `LanguageRules.md`
- `PlatformRules.md`
- `CharacterRegistry.md`
- `EntityRegistry.md`

不需要第一天就全部填完。先填当前任务所需的最小事实。

## 第三步：映射已有目录

你可以保留原目录名，只需要在 `00_System/ProjectConfig.md` 中写清楚映射。

示例：

```markdown
## 目录映射

| VaultForge 职责 | 当前 Vault |
|---|---|
| 系统规则 | `00_System/` |
| 项目逻辑 | `Plot/` |
| 产出物 | `Drafts/` |
| 审稿记录 | `Reviews/` |
| 归档 | `Archive/` |
```

## 第四步：逐步建立 Registry

不要试图一次登记整个 Vault。

优先登记：

- 当前活跃人物或角色。
- 当前重要实体。
- 当前未解决线程。
- 当前矛盾或风险。

## 第五步：运行只读迁移审计

使用：

```text
请读取 CLAUDE.md 并执行只读迁移审计。识别缺失系统文件、目录命名不一致、可能的事实源和迁移风险。不要修改文件。
```

## 第六步：分批授权修复

审计之后，一次只授权一组修复。

适合优先修复：

- 填写 `ProjectState.md`。
- 建立初始 Registry。
- 把模板放入 `07_Templates/`。
- 为最常用任务创建一个 Skill。

