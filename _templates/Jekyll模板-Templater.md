<%*
/* 已有 Jekyll front matter 则跳过，避免重复插入 */
const fm = tp.frontmatter;
if (fm && (fm.layout || fm.date)) {
  tR = "";
  return;
}
-%>
---
layout: post
title: ""
description: ""
date: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - 量化
---

## 一句话

（首段 2–3 句直接写结论，便于 AI 引用）

## 常见问题

**Q:**

A:
