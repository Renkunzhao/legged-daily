[English](../../drafts/legged-daily-2026-07-26.md) | **中文**
# 腿足机器人日报 - 2026-07-26

## 摘要
- 今日有 2 篇此前未跟踪的论文达到收录标准：ZONDA 在实体 Direct Drive Tech TITA 双足机器人上验证跨楼层目标导航与动态行人避障；Robostral Navigate 提出面向轮式、腿式和飞行平台迁移的单目视觉语言导航模型。
- ZONDA 与腿足机器人更直接相关：它结合基于几何约束的楼梯可通行性、多视角 VLM 目标核验和前瞻式行人避障，并完成实体双足部署。
- Robostral Navigate 是高信号的邻近基础模型成果，但论文公开的实体实验使用 Galaxea R1 和 JetAuto 轮式底盘，而非腿足平台；其腿足适用性目前属于迁移能力主张，不是已验证的腿足部署。
- 今日没有新公开仓库达到收录标准。核验时，两篇论文都未链接论文专属的公开实现或模型发布。
- Mistral AI 正在为巴黎机器人团队招聘 AI Scientist 和 Research Engineer，两个官方职位均聚焦真实移动操作、具身智能、导航和实体部署。此前跟踪的 LAAS-CNRS/JRL 人形机器人博士职位仍有效，截止 2026-07-31。

<details>
<summary><strong>新论文</strong></summary>

### ZONDA: Zero-shot Object Navigation with Dynamic Avoidance in Multi-floor Environments
- 链接: https://arxiv.org/abs/2607.21025
- 来源: arXiv
- 日期: 2026-07-23
- 作者: Shaomin Liang, Xuanhong Liao, Shiyao Zhang
- 主题: biped navigation / object goal navigation / multi-floor planning / stair traversal / dynamic obstacle avoidance / vision-language models
- 摘要: ZONDA 结合高度差可通行地图、启发式跨楼层探索、多视角 VLM 目标核验和行人轨迹预测，用于多楼层动态环境中的零样本目标导航。
- 备注: 系统在 Habitat 的 HM3D、MP3D 和作者扩展的 HM3D-DYNA 上评测，并部署到实体 Direct Drive Tech TITA 双足机器人。其平台迁移机制用与平台相关的几何极限替代学习式底层 PointNav 策略，但实体证据目前仅覆盖一种双足平台。核验时未发现论文专属公开代码仓库。

### Robostral Navigate
- 链接: https://arxiv.org/abs/2607.20785
- 来源: arXiv
- 日期: 2026-07-22
- 作者: Arjun Majumdar, Avinash Sooriyarachchi, Benjamin Tibi, Chris Bamford, Elliot Chane-Sane, Guillaume Lample, Khyathi Raghavi Chandu, Ludovic Ho Fuh, Mathieu Poiree, Olivier Duchenne, Rosalie Millner, Srijan Mishra, Theo Cachet, Thomas Chabal
- 主题: vision-language navigation / monocular navigation / cross-embodiment transfer / reinforcement learning / simulation data / mobile robots
- 摘要: Robostral Navigate 是一个 8B 视觉语言模型，根据语言指令和单目 RGB 历史预测图像空间 waypoint，并利用 240 万条仿真轨迹、前缀缓存训练和在线 RL 支持不同机器人几何形态间的导航迁移。
- 备注: 论文报告 R2R-CE validation unseen 成功率 77.4%，英文 RxR-CE validation unseen 成功率 75.1%。论文主张可迁移到轮式、腿式和飞行机器人，但公开的实体部署使用 Galaxea R1 与 Hiwonder JetAuto 轮式平台，腿足部署尚未验证。核验时，Mistral 官方发布页未提供公开模型权重或代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

今日没有新公开仓库达到收录标准。入选论文未链接论文专属公开代码或模型，且未核验到近期新仓库同时具备足够的腿足机器人相关性和文档质量，因此不为数量凑项。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Shiyao Zhang / ZONDA 合作团队
- 机构: Great Bay University / Southern University of Science and Technology / Guangdong Direct Drive Technology
- 主页: https://arxiv.org/abs/2607.21025
- arXiv: https://arxiv.org/abs/2607.21025
- 实验室 / 院系: School of Advanced Engineering / School of Automation and Intelligent Manufacturing / Direct Drive Technology
- 重点方向: biped navigation / multi-floor exploration / dynamic obstacle avoidance / embodied perception / VLM-based target verification
- 备注: 该产学合作团队是在 Direct Drive Tech TITA 双足机器人上验证导航栈的有效信号。ZONDA 将楼梯通行、开放词汇目标搜索和行人感知规划结合起来，适合持续跟踪其在人类环境中的腿足自主导航工作。
- 学生与代表工作:
  - [Shaomin Liang](https://arxiv.org/search/cs?searchtype=author&query=Liang,+S) — [ZONDA](https://arxiv.org/abs/2607.21025)

### Mistral AI Science Robotics
- 机构: Mistral AI, France
- 主页: https://mistral.ai/news/robostral-navigate/
- arXiv: https://arxiv.org/abs/2607.20785
- 实验室 / 院系: AI Science Robotics
- 重点方向: embodied navigation / vision-language models / cross-embodiment transfer / online reinforcement learning / mobile manipulation
- 备注: Robostral Navigate 标志着 Mistral 自研基础模型工作具体扩展到具身导航。团队也在招聘负责实体部署的机器人科学家和工程师，值得继续跟踪后续腿足平台验证、模型开放情况及移动操作研究。
- 学生与代表工作:
  - [Theo Cachet](https://arxiv.org/search/cs?searchtype=author&query=Cachet,+T) — [Robostral Navigate](https://arxiv.org/abs/2607.20785)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Mistral AI Robotics — AI Scientist, Robotics
- 类型: Research Scientist / Full-time
- 地点: 法国巴黎；现场办公
- 来源: https://jobs.ashbyhq.com/mistral.ai/c70522d8-73cb-46ed-9f9a-5cb807420485
- 截止日期: rolling / unknown
- 主题: mobile manipulation / embodied intelligence / vision-language models / robot learning / navigation / simulation / deployment
- 状态: active；官方职位发布于 2026-07-03
- 备注: 面向通用移动操作机器人开发可扩展 AI 方法与基础设施，包括 VLM/VLA 能力和实体平台部署。

### Mistral AI Robotics — Research Engineer, Robotics
- 类型: Research Engineer / Full-time
- 地点: 法国巴黎；现场办公
- 来源: https://jobs.ashbyhq.com/mistral.ai/25944723-62e2-498e-8149-a588907c39d6
- 截止日期: rolling / unknown
- 主题: mobile manipulation / real-robot deployment / data pipelines / robot fleets / ROS / control / perception
- 状态: active；官方职位发布于 2026-07-03
- 备注: 聚焦在真实机器人上部署和改进 AI 模型、建设训练数据流水线、维护多样化机器人集群，并在接近生产的环境中验证系统。

### LAAS-CNRS Gepetto / CNRS-AIST JRL — 人形机器人博士职位
- 类型: PhD
- 地点: 法国 Toulouse，部分工作在日本 Tsukuba 的 JRL 开展
- 来源: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止日期: 2026-07-31 23:59（职位页面当地时间）
- 主题: humanoid locomotion / reinforcement learning / online MPC / whole-body control / hybrid contact decisions
- 状态: active；此前已跟踪，本次为截止日期提醒
- 备注: 课题将基于 RL 的离散接触、步态和行为决策与在线 MPC 结合，以生成可行的连续全身运动，并计划在 PAL Robotics Kangaroo 和/或 Unitree 人形机器人上验证。

</details>
