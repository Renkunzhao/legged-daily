**中文** | [English](../../drafts/legged-daily-2026-07-24.md)
# 腿足机器人日报 - 2026-07-24

## 摘要
- 今日精选 1 篇高置信度新论文：CAT 将机器人本体能力直接作为地形可通行性条件，并在 Boston Dynamics Spot 与 TerraSentia 上完成真实导航验证。
- 今日没有达到收录标准的新实现仓库。CAT 已公开项目网站仓库，但尚未发现公开的训练或部署代码。
- University of São Paulo Mobile Robotics Group 是值得新增跟踪的来源；此前已跟踪的 LAAS-CNRS/JRL 人形机器人博士职位仍在开放，截止日期为 2026-07-31。

<details>
<summary><strong>新论文</strong></summary>

### Towards Capability-Aware Traversability Navigation for Unstructured Environments
- 链接: https://arxiv.org/abs/2607.20679
- 项目页: https://capability-aware-traversability.github.io/
- 来源: arXiv / IROS 2026
- 日期: 2026-07-22
- 作者: Gianluca Capezzuto, Felipe Tommaselli, Matheus P. Angarola, Ricardo V. Godoy, Marcelo Becker
- 主题: traversability / embodiment conditioning / quadruped navigation / semantic perception / unstructured environments
- 摘要: Capability-Aware Traversability（CAT）在预测稠密地形代价时，将目标机器人的能力配置直接注入感知表示。方法结合 RGB-D DINOv3 特征、CLIPSeg 语义地形图、机器人专属可通行性向量、SPADE 解码器和每机器人原型，避免仅在轨迹输出末端再过滤不符合本体约束的路径。
- 备注: 作者报告，相比最强基线，CAT 在真实执行轨迹上的 AUROC 提升 11.0%，在人类轨迹上的 AUPRC 提升 15.8%。系统在 Jetson Orin Nano 上以 4.8 Hz 运行；Boston Dynamics Spot 完成 10/10 次林地试验，TerraSentia 在 7/10 次试验中避开楼梯。核验时项目页仓库仅包含网站资源，未看到公开实现代码。

</details>

<details>
<summary><strong>新仓库</strong></summary>

今日没有精选出新的高置信度实现仓库。CAT 项目网站仓库已公开：https://github.com/capability-aware-traversability/capability-aware-traversability.github.io ，但 GitHub 元数据和网站内容均表明它是项目页仓库，而非已发布的训练或部署代码。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Marcelo Becker / Mobile Robotics Group
- 机构: University of São Paulo（USP），São Carlos，Brazil
- 主页: https://capability-aware-traversability.github.io/
- arXiv: https://arxiv.org/abs/2607.20679
- 实验室 / 院系: Mobile Robotics Group, University of São Paulo
- 重点方向: mobile robotics / traversability / semantic perception / quadruped navigation / field deployment
- 备注: CAT 是该组在多本体户外导航方向上的一个具体新信号。工作把物理轨迹监督与基础视觉模型特征结合，并在 Boston Dynamics Spot 和轮式滑移转向机器人上验证同一套能力感知表示，因此该组值得作为 field robotics 与 embodiment-aware perception 来源持续跟踪。
- 学生与代表工作:
  - [Gianluca Capezzuto](https://arxiv.org/search/cs?searchtype=author&query=Capezzuto,+G) — [Towards Capability-Aware Traversability Navigation for Unstructured Environments](https://arxiv.org/abs/2607.20679)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### LAAS-CNRS Gepetto / CNRS-AIST JRL — PhD in Humanoid Robotics
- 类型: PhD
- 地点: 法国 Toulouse，部分工作在日本 Tsukuba 的 JRL 开展
- 来源: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止日期: 2026-07-31 23:59（职位页面当地时间）
- 主题: humanoid locomotion / reinforcement learning / online MPC / whole-body control / safe control
- 状态: active；此前已跟踪，本次为截止日期提醒
- 备注: 课题由 RL 负责离散的高层接触、落脚、步态与行为决策，在线 MPC 负责保证连续全身运动的可行性与安全性。导师为 LAAS-CNRS Gepetto 的 Olivier Stasse 和 CNRS-AIST JRL 的 Mehdi Benallegue；计划硬件包括 PAL Robotics Kangaroo 和/或 Unitree H1/R1 级人形机器人。官方页面给出的预计入职日期为 2026-10-01。

### EPFL BioRob 人形运动职位
- 当前状态: closed / 不作为活跃机会收录
- 原因: 官方 openings 页面将 Fall 2026 humanoid neuromechanics Postdoc/PhD 条目标为“CLOSED”，正文也明确写有 positions are now closed；页面仍残留较早的申请说明，不能据此判断职位仍开放。
- 已核验来源: https://www.epfl.ch/labs/biorob/openings/

</details>
