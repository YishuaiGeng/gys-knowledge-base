---
title: 🏠 工作台
tags:
  - meta
---

> 这是 Obsidian 专用仪表盘（网站不发布此页）。数据来自日记 frontmatter 和全库任务，自动更新。

## ✅ 待办任务

```tasks
not done
sort by due
limit 15
```

## 📊 项目进度

- [ ] 🚀 知识空间建设
    - [x] Quartz 部署上线
    - [x] Things 主题 + 首页 Dashboard
    - [x] Obsidian 工作台配置
    - [ ] 迁移存量论文笔记
    - [ ] 全私有化（Cloudflare Access）
    - [ ] RAG 问答助手
- [ ] 📖 论文阅读（示例：换成你的真实目标）
    - [x] ReAct
    - [ ] Toolformer
    - [ ] RecSys survey

## 🔥 学习打卡

在每天日记的 frontmatter 里填 `学习时长`（小时），这里自动点亮：

```dataviewjs
const calendarData = { entries: [] }
for (let page of dv.pages('"Daily Journal"').where(p => p['学习时长'])) {
  calendarData.entries.push({
    date: page.file.name,
    intensity: page['学习时长'],
    content: "",
  })
}
renderHeatmapCalendar(this.container, calendarData)
```

## 📚 最近论文

```dataview
TABLE WITHOUT ID file.link AS "论文", date AS "阅读日期", tags AS "标签"
FROM "Reading Notes"
WHERE file.name != "index"
SORT date DESC
LIMIT 10
```

## 📝 最近日记

```dataview
LIST
FROM "Daily Journal"
WHERE file.name != "index"
SORT file.name DESC
LIMIT 7
```
