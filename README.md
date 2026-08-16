# AI Security Learning Workbench ｜ AI 安全学习工作台

> 高级、优雅、沉浸式的 CISSP + AI Security 智能学习工作台
> 单文件 HTML · 零外部依赖 · 数据本地存储 · 可部署为 PWA 级学习系统

一个能够**长期陪伴用户备考 CISSP、持续学习 AI Security、自动管理学习计划、聚合个人知识、记录技术笔记并形成个人技术博客**的智能学习工作台。

## ✨ 核心能力

| 模块 | 能力 |
|------|------|
| **CISSP 动态学习计划** | 8 阶段 × 教材 21 章索引；学习时间自动重算计划：延期自动顺延、提前自动提前、延期>4 天红色风险预警、提前完成动画 |
| **沉浸式阅读** | 全屏讲义、滚动时标题收缩、回到顶部、考试重点/易错/案例 Callout 分层 |
| **AI Security 知识体系** | 岗位技能分类方块（内含技能树 ◉●○）、点击筛选内容卡片、14 张深度知识卡片 |
| **个人知识库** | KBAdapter 数据源适配器：内嵌教材 / 本地 Markdown 导入 / IMA 知识库（预留） |
| **月度技术学习** | Top 10 技术推荐（按热度/重要性排序，已学自动排除） |
| **Markdown 笔记** | 编辑/预览双栏、代码高亮、表格、Checklist |
| **博客发布** | 草稿 → 编辑 → 发布全流程 |
| **学习数据** | 积分/等级/成就、错题集、艾宾浩斯滚动复习、成绩趋势、打卡热力图 |

## 🚀 快速开始

1. 直接用浏览器打开 `AI安全学习工作台.html`（零依赖，离线可用）
2. 数据保存在浏览器 localStorage，可通过界面「导出 JSON」备份
3. 部署后手机浏览器打开 → 添加到主屏幕，即可当 App 使用

## 📁 项目结构

```
├── AI安全学习工作台.html   # 主工作台（单文件，全部内联）
├── data/
│   ├── cissp-chapters.json  # ★ 教材正文数据（OSG 第9版中文 21 章真实正文，26.7万字）
│   ├── cissp-content.json   # 教材章节大纲（21 章结构化）
│   └── syllabus-brief.json  # 章节索引摘要
├── docs/
│   └── ARCHITECTURE.md     # 系统架构说明
├── notes/                  # Markdown 笔记（导出的笔记文件）
├── posts/                  # 博客文章（发布的文章文件）
├── img/                    # 图片资源（笔记/博客引用）
│   ├── cissp/
│   └── ai-security/
├── reports/                # 每周定时任务生成的岗位需求周报
├── build_content.js        # 教材大纲内容管道
├── build_body.js           # ★ 教材正文内容管道（提取 21 章真实正文）
├── LICENSE
└── README.md
```

## 🧩 系统架构

- **数据层**：localStorage（key: `wb_sec_workbench_v1`），JSON 导出/导入备份
- **内容管道**：`build_content.js` 从 OSG 第 9 版中文 + 第 10 版英文提取 21 章大纲 → `data/cissp-content.json`
- **学习计划引擎**：`Adaptive Study Planner`——以学习记录（分钟数）为输入，动态计算各阶段预计完成日期与风险
- **知识库适配器**：`KBAdapter` 抽象接口（Embedded / LocalFile / IMA 预留），不伪造未接入的数据源
- **渲染**：全部内联 SVG 图标/图表，零外部 CDN

## 🔒 数据与隐私

- 所有数据仅存于浏览器本地，不上传服务器
- 部署后为公开链接，页面不预填真实隐私数据
- 建议定期「导出 JSON」备份；清空数据需二次确认

## 📄 License

MIT
