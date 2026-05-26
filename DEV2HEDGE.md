# dev2hedge 发布说明

## Obsidian 配置

1. **核心插件** → 启用 **模板**（模板文件夹：`_templates`）
2. **社区插件** → 安装并启用 **Templater**（配置已预写在 `.obsidian/plugins/templater-obsidian/data.json`）
3. 确认 Templater 设置与下表一致（一般安装后自动读取）

### 新建 `_posts` 笔记时自动套用 GEO 模板（Templater 文件夹模板）

| Templater 设置项 | 值 |
|------------------|-----|
| Trigger Templater on new file creation | **开** |
| Enable Folder Templates | **开** |
| Folder | `_posts` |
| Template | `_templates/Jekyll模板-Templater.md` |

**正确新建方式（会自动插入模板）：**

1. 在左侧文件列表进入 **`_posts` 文件夹**
2. 点「新建笔记」或 `Cmd+N`（`app.json` 已设默认在 `_posts` 创建）
3. **文件名**用 Jekyll 格式：`YYYY-MM-DD-英文slug.md`（例：`2026-05-22-personal-hedge.md`）
4. 文首应自动出现 front matter +「一句话」+「常见问题」占位

若未自动插入：`Cmd+P` → **Templater: Replace templates in the active file**（快捷键 `Cmd+Shift+T`）。

**不要**在仓库根目录新建文章；根目录不会触发 `_posts` 模板。

**手动插入（无 Templater 时）：** `Cmd+Alt+T` → 选 **Jekyll模板**（核心模板，`{{date}}` 语法）。

### Obsidian Git（已预配置，见 `.obsidian/plugins/obsidian-git/data.json`）

| 项 | 值 | 作用 |
|----|-----|------|
| 启动时 pull | 开 | 打开库先拉远程 |
| 改文件后 commit | 开 | 停止编辑后自动提交 |
| 自动 commit 间隔 | 10 分钟 | 定时备份 |
| 自动 push 间隔 | 10 分钟 | **推送到 GitHub → 触发 Pages 构建** |
| 自动 pull 间隔 | 30 分钟 | 多设备同步 |
| push 前 pull | 开 | 减少冲突 |

**首次使用：** 设置 → 社区插件 → 启用 **Git**。在命令面板执行 **Create a backup** 或 **Push**，按提示用 GitHub 用户名 + Fine-grained Token 登录（仅首次）。

**手动：** 左下角 Git 图标，或 `Cmd+P` → `Obsidian Git: Create a backup` / `Push`.

## Front matter（Jekyll + GEO）

```yaml
---
layout: post
title: 文章标题
description: 2–3 句结论摘要（用于 meta / AI 摘引）
date: YYYY-MM-DD
updated: YYYY-MM-DD   # 可选，有修订时填写
tags:
  - 量化
---
```

`layout` 可省略（`_config.yml` 已为 posts 默认 `post`）。

## GEO 已内置

- 每篇：`description`、canonical、Open Graph、BlogPosting JSON-LD
- 全站：`robots.txt`（允许常见 AI 爬虫）、`sitemap.xml`、`feed.xml`
- 作者信息：`_config.yml` 的 `author`

## 部署

推送到 `main` → `.github/workflows/deploy.yml` 构建并发布到 GitHub Pages。

- 站点：<https://alphaveteran.github.io/dev2hedge/>
- Sitemap：<https://alphaveteran.github.io/dev2hedge/sitemap.xml>
- RSS：<https://alphaveteran.github.io/dev2hedge/feed.xml>
