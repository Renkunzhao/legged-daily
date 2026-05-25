[English](../README.md) | **中文**
# 腿足机器人研究索引

一个面向研究的 **腿足机器人** curated index，重点支持：
- 通过 master lists 做长期检索
- 通过日期日志做每日发现
- 直接在 GitHub Markdown 中浏览和编辑

本仓库用于支持从事腿足运动及相关方向的学生和研究者进行 **研究发现、方向定位和长期参考**。

> 本仓库是 curated index，不是 benchmark、ranking 或 evaluation。
> 条目基于公开信息整理，目标是在 GitHub 中保持有用、可读、可维护。

---

## Master Lists

- [papers.md](papers.md) — 长期 curated 论文列表
- [repos.md](repos.md) — 长期 curated 仓库和工具列表
- [labs.md](labs.md) — 实验室、教授和相关研究者来源网络
- [jobs.md](jobs.md) — 活跃或 watchlist 状态的学术/工业机会列表

## 每日日志

- [legged-daily/](legged-daily/) — 按日期记录的每日更新和新发现

## 搜索策略

发现来源按以下层级展开：

1. **优先会议/期刊** — arXiv, IROS, ICRA, RA-L, RSS, IJRR, Science Robotics, T-RO, CoRL, CVPR, NeurIPS, AAAI。
2. **已跟踪实验室和研究者** — 记录在 [labs.md](labs.md) 中的主页、GitHub、X、Google Scholar、YouTube、Bilibili 等渠道。
3. **聚合来源** — 非实验室、非会议期刊的信息流，例如 arXiv category RSS、curator accounts、industry media、community channels，维护在 [source-watchlist.md](../source-watchlist.md)。
4. **相邻高信号来源** — 仅在与腿足机器人明确相关时纳入。

## 模板与草稿

本仓库由 agent 维护。[templates/legged-daily-template.md](templates/legged-daily-template.md) 定义每日输出格式，[drafts/](drafts/) 存放正式发布前可推送到 GitHub 预览的工作草稿。

---

## 仓库工作方式

### 每日日志

每日日志记录新发现的：
- 论文
- 仓库
- 实验室 / 教授信号
- 招聘信号

每日文件保存于：
- `legged-daily/YYYY-MM-DD.md`

### Master lists

Master lists 只保留值得长期检索的信息。

- `papers.md` 和 `repos.md` 是 curated reference lists
- `labs.md` 是持续增长的 source network
- `jobs.md` 跟踪活跃或 watchlist 状态的机会

---

## 当前范围

本仓库关注腿足机器人及相邻主题，包括：
- 四足、人形、双足和多足系统
- 运动、全身控制和 MPC
- 强化学习、模仿学习和机器人学习
- 感知、地形适应和 sim-to-real 迁移
- 相关实验室、教师团队、开源项目和招聘信号
