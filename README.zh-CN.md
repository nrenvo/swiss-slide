<p align="center">
  <h1 align="center">swiss-slide</h1>
</p>

<p align="center">
  <a title="License" href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-002FA7.svg?style=flat-square"></a>
  <a title="Agent Skill" href="https://github.com/nrenvo/swiss-slide"><img src="https://img.shields.io/badge/agent-skill-002FA7.svg?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cGF0aCBkPSJNMTIgMkM2LjQ3NyAyIDIgNi40NzcgMiAxMnM0LjQ3NyAxMCAxMCAxMCAxMC00LjQ3NyAxMC0xMFMxNy41MjMgMiAxMiAyeiIgZmlsbD0iI2ZmZiIvPjwvc3ZnPg=="></a>
</p>

<p align="center">
  <strong>IBM Carbon + Swiss International Style</strong> &mdash; 用自然语言把工作汇报变成精致全屏 HTML 演示稿。<br>
  单个 HTML 文件。零依赖。任何浏览器直接打开。
</p>

[English](./README.md)

![swiss-slide 封面](./assets/preview.png)

---

## 这是什么？

一个 **agent skill** &mdash; 支持 Claude Code、Codex，以及任何兼容 skill 格式的平台。用日常语言描述你的需求 &mdash; 周报、季度汇报、架构评审、事故复盘 &mdash; swiss-slide 会生成一份可以直接拿去讲的工作汇报。

---

## 版式展示

| | |
|---|---|
| ![目录](./assets/screens/02-agenda.png) | ![模块](./assets/screens/03-modules.png) |
| ![上手流程](./assets/screens/06-get-started.png) | ![KPI](./assets/screens/05-kpis.png) |

---

## 特性

<table>
<tr><td width="150"><strong>6 种配色</strong></td><td>IKB 克莱因蓝（默认）、朱红、森林绿、石板灰、紫罗兰、琥珀。改两个 CSS 变量即可切换。</td></tr>
<tr><td><strong>8 种布局</strong></td><td>封面、目录（分栏）、模块、卡片、前后对比、计划、结尾、KPI &mdash; 每种布局有独立的视觉风格。</td></tr>
<tr><td><strong>动态网格</strong></td><td>封面和强调页带漂移点阵与细线网格，纯 CSS 实现，无需 canvas。</td></tr>
<tr><td><strong>键盘导航</strong></td><td>&larr; &rarr; 或空格键翻页，方形原点指示器。平滑 scroll-snap 过渡。</td></tr>
<tr><td><strong>响应式排版</strong></td><td>视口缩放字号 &mdash; Inter、JetBrains Mono、CJK 兜底。极端字号对比，遵循 Swiss 设计规则。</td></tr>
<tr><td><strong>零依赖</strong></td><td>一个独立的 HTML 文件。分享、打开、演示即可。观众无需安装任何东西。</td></tr>
</table>

---

## 快速上手

```bash
npx skills add nrenvo/swiss-slide --skill swiss-slide
```

然后：

```
> 帮我把 Q4 基础设施迁移的事后复盘做成幻灯片

> 把这些会议纪要转成演示文稿

> 根据这份设计文档生成架构评审的 deck
```

技能会自动把内容映射到合适的布局、选色并处理排版。你会得到一个 `.html` 文件。

---

## 幻灯片布局

| # | 布局 | 适用场景 |
|---|------|----------|
| R01 | **封面** | 全出血强调色开篇 &mdash; 一行标题, 一行摘要 |
| R02 | **目录** | 分栏：左侧摘要陈述 + 右侧编号列表 |
| R03 | **模块** | 四列横向列表 &mdash; 项目拆解、交付物 |
| R04 | **卡片** | 四卡片网格 &mdash; 功能特性、并行工作流 |
| R05 | **前后对比** | 暗色对比 &mdash; 迁移、重构、安全升级 |
| R08 | **KPI** | 灰底大数字统计展示 |
| R06 | **计划** | 三列后续计划，首列强调色边框 |
| R07 | **结尾** | 与封面对称 &mdash; 全出血强调色致谢页 |

---

## 设计规则

Swiss International Style，通过 IBM Carbon 落地：

> 直角。发丝线。极端字号对比。大量留白。无阴影。无圆角。

| 令牌 | 亮色 | 暗色 |
|------|------|------|
| 表面 | `#fafaf8`（暖白） | `#0a0a0a`（近黑） |
| 强调色 | `#002FA7`（IKB 克莱因蓝）&mdash; 可配置 | |
| 字体 | Inter · JetBrains Mono · 系统 CJK | |
| 网格 | 6 列，2.4vh 间距 | |

---

## 文件结构

```
swiss-slide/
├── SKILL.md                  ← 技能定义（触发规则 + 工作流）
├── assets/
│   └── template.html          ← 精简 CSS/JS 壳、动态网格、导航
├── references/
│   ├── slide-recipes.md       ← R01–R08 完整 HTML 片段
│   └── design-tokens.md       ← 设计令牌速查、字号体系、组件
├── README.md
├── README.zh-CN.md
└── LICENSE
```

---

## 参与贡献

这是一个开源项目。发现 bug 或有想法？

1. 提交 [Issue](https://github.com/nrenvo/swiss-slide/issues)
2. Fork 仓库，修改后提交 PR
3. 保持简洁 &mdash; 这个技能看重精炼和视觉清晰度
