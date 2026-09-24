# rikka-research
Research notes and evolving frameworks on complex systems, enterprise AI, Cognito Atlas and Decision Space.

这是 Rikka 公开文章与研究内容的版本档案。阅读网站：[rikkalab.com](https://rikkalab.com/zh/)。网站工程由独立的私有 `rikkalab` 仓库维护。

中文是语义真相源；英文目录仅收录已有正式译文。待译页面不会以占位正文进入本仓库。

## 内容

- [中文理论](zh/research/)：世界观、Representation、Cognito Atlas、Decision Space。
- [AI 与数字化](zh/digitalization/)：业务建模、治理能力、共享业务地图、企业 AI、Agent Harness 等文章。
- [案例与思考](zh/cases/)：设备视图、产品定义与 BOM、OA 审批建模。
- [English theory](en/research/) and [AI & Digitalization](en/digitalization/).
- [文章 metadata](article-metadata.json)：标题、说明、网站路径、发布日期、更新日期、源码与历史链接。
- [中英术语表](glossary.md)。后续研究笔记、论文可分别放入 `notes/`、`papers/`。

## 时间与历史

`publishedAt` 是内容 metadata 显式维护的正式发布日期；`updatedAt` 是实质内容更新日期。导入、搬目录、同步、排版和 Git 提交不会自动改变这些日期。

Git commit history 仅用于追溯实际公开版本。首次导入不表示文章首次发布，也不补造导入前的 Git 历史。阅读旧版本可在对应 Markdown 文件页面查看 History。

## 网站同步

本仓库保存公开原文，网站仓库保留独立构建副本。Codex 同步维护两边正文和 metadata，检查内容哈希及日期一致性。网站构建不依赖本仓库在线，不使用 submodule。

正文中的 `/zh/`、`/en/` 站内路径属于阅读网站，可通过 metadata 的 `websitePath` 打开文章。文章公开不代表授权任意再利用；目前未另行授予内容许可证。
