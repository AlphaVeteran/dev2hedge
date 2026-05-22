# dev2hedge 发布说明

## Obsidian 配置

1. **核心插件** → 启用 **模板**
2. 模板文件夹：`_templates`
3. 新建 `_posts` 文章时插入 **Jekyll模板**

## Front matter（Jekyll）

```yaml
---
layout: default
title: 文章标题
date: YYYY-MM-DD
---
```

## 部署

推送到 `main` → `.github/workflows/deploy.yml` 构建并发布到 GitHub Pages。

站点根路径为 `/dev2hedge`（已在 `_config.yml` 配置 `baseurl`）。
