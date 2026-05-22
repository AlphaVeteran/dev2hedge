# dev2hedge 发布说明

## Obsidian 配置

1. **核心插件** → 启用 **模板**
2. 模板文件夹：`_templates`
3. 新建 `_posts` 文章时插入 **Jekyll模板**

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
