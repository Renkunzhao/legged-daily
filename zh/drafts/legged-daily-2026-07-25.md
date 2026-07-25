[English](../../drafts/legged-daily-2026-07-25.md) | **中文**
# 腿足机器人日报 - 2026-07-25

## 摘要
- 今日精选 2 篇此前未跟踪的论文：面向微型 ROBOTIS OP3 的 VR + RL 遥操作移动操作系统，以及面向 Unitree G1-Edu 零售任务的数据高效后训练框架 DEED。
- 2 个实现仓库达到收录标准：新公开的智元灵犀 X2 ROS 2 建图、定位与导航栈，以及今日更新、覆盖训练、评估和 MuJoCo sim-to-sim 的 Unitree G1 MJLab AMP 运动代码库。
- University of Louisville 的微型人形工作适合跟踪低门槛全身遥操作研究；HIVE Robots 与 Technical University of Denmark 构成一条新的人形 VLA 实际部署信号。
- 今日未核验到新的高置信度招聘机会。此前跟踪的 LAAS-CNRS/JRL 人形机器人博士职位仍是最近的可行动截止项，截止 2026-07-31。

<details>
<summary><strong>新论文</strong></summary>

### Towards Miniature Humanoid Tele-Loco-Manipulation Using Virtual Reality and Reinforcement Learning
- 链接: https://arxiv.org/abs/2607.20399
- 来源: arXiv
- 日期: 2026-07-22
- 作者: Nicolas Kosanovic, Jordan Dowdy, Jean Chagas Vaz
- 主题: miniature humanoid / teleoperation / loco-manipulation / reinforcement learning / virtual reality / compliant control
- 摘要: 该工作在 ROBOTIS OP3 上把 VR 上半身动作映射与 RL 行走、平衡控制结合成全身遥临栈，目标是在更小、更易获得的人形平台上开展遥操作移动操作研究。
- 备注: 机器人在不受手臂动作影响的情况下最高行走速度达到 0.45 m/s；在方块搬运实验中，专家操作者在 10 分钟内平均移动两个 40 g 方块，机器人累计行走约 5 m。论文描述了 Unity/ROS 通信、逆运动学手臂控制、RL 下半身控制和关节侧阻抗控制；核验时未发现论文专属的公开实现仓库。

### Closing the Lab-to-Store Gap: A Data-Efficient Post-Training and Experience-Driven Learning VLA Framework for Retail Humanoids
- 链接: https://arxiv.org/abs/2607.20345
- 来源: arXiv
- 日期: 2026-07-22
- 作者: Roger Sala Sisó, Tiago Silvério, Jakob Sand, Tran Nguyen Le
- 主题: humanoid manipulation / vision-language-action / post-training / experience-driven learning / retail robotics / Unitree G1
- 摘要: DEED 是一套把 GR00T N1.6 适配到 Unitree G1-Edu 超市货架补货任务的系统流程，包含控制频率对齐、演示数据筛选、任务相关视觉突出、降低 VLA 依赖、经验驱动细化和潜空间分布分析。
- 备注: 作者认为可靠部署更多取决于数据与系统集成，而不是修改模型架构，并报告用单张 GPU 将朴素微调下无法工作的策略转化为可用系统。实验主要控制手臂与躯干，同时保留 Unitree 的运动控制器，因此更适合作为人形部署与移动操作系统信号，而不是新的学习运动方法。核验时未发现论文专属公开代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Nova-Valley/agibot-x2-navigation
- 链接: https://github.com/Nova-Valley/agibot-x2-navigation
- 类别: perception / SLAM / localization / navigation / toolkit
- 机器人类型: humanoid
- 仿真器: none
- 部署: hardware
- 摘要: 面向智元灵犀 X2 的 ROS 2 Humble 导航工作区，覆盖雷达与 IMU 校正、Spark FAST-LIO 建图、PCD 处理、NDT-OMP 定位、OctoMap 投影、Nav2 规划与点云避障，以及把 `/cmd_vel` 转为 X2 AIMDK 运动指令。
- 备注: 该 MIT 许可 C++ 仓库创建于 2026-07-24，为 Ubuntu 22.04 提供面向实体硬件的端到端集成说明。文档明确提示系统会向真实机器人发送运动指令，并建议在有人看护和可随时急停的条件下分阶段验证。

### yhx1203/humanoid_amp_mjlab
- 链接: https://github.com/yhx1203/humanoid_amp_mjlab
- 类别: reinforcement learning / locomotion / imitation learning
- 机器人类型: humanoid
- 仿真器: MuJoCo / MJLab
- 部署: sim
- 摘要: 面向 Unitree G1 AMP 运动的 Apache-2.0 强化学习代码库，提供动作预览、并行训练、Viser 可视化评估、随附检查点，以及基于 Unitree SDK2 Python 的 MuJoCo sim-to-sim 流程。
- 备注: 仓库于 2026-07-25 更新。当前文档覆盖使用 4096 个环境训练 `Unitree-G1-AMP-Flat`，以及无线/手柄驱动的 sim-to-sim 评估，但尚未说明直接部署到实体机器人的流程。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Jean Chagas Vaz / 微型人形遥临团队
- 机构: University of Louisville, USA
- 主页: https://arxiv.org/abs/2607.20399
- arXiv: https://arxiv.org/abs/2607.20399
- 实验室 / 院系: Department of Electrical and Computer Engineering
- 重点方向: miniature humanoids / VR teleoperation / reinforcement-learning locomotion / compliant control / loco-manipulation
- 备注: 该工作是一条值得跟踪的低成本、易获得人形研究信号：团队没有依赖昂贵的全尺寸人形，而是围绕 OP3 重建支持柔顺全身遥临的控制栈，并把 VR 动作映射、平衡感知 RL 行走和实体方块操作结合起来。
- 学生与代表工作:
  - [Nicolas Kosanovic](https://arxiv.org/search/cs?searchtype=author&query=Kosanovic,+N) — [Towards Miniature Humanoid Tele-Loco-Manipulation Using Virtual Reality and Reinforcement Learning](https://arxiv.org/abs/2607.20399)

### HIVE Robots / Technical University of Denmark 合作团队
- 机构: HIVE Robots and Technical University of Denmark, Denmark
- 主页: https://arxiv.org/abs/2607.20345
- arXiv: https://arxiv.org/abs/2607.20345
- 实验室 / 院系: HIVE Robots / DTU Department of Engineering Technology
- 重点方向: humanoid manipulation / VLA post-training / data curation / experience-driven learning / retail deployment
- 备注: DEED 是一条把基础 VLA 策略部署到真实 Unitree G1-Edu、并在近似商店环境中评估的具体应用信号。该合作值得持续跟踪其部署工程、真实数据反馈及人形基础模型策略的实用评估。
- 学生与代表工作:
  - [Roger Sala Sisó](https://arxiv.org/search/cs?searchtype=author&query=Sala+Siso,+R) — [Closing the Lab-to-Store Gap](https://arxiv.org/abs/2607.20345)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日未核验到新的高置信度招聘信号。

### LAAS-CNRS Gepetto / CNRS-AIST JRL — 人形机器人博士职位
- 类型: PhD
- 地点: 法国 Toulouse，部分工作在日本 Tsukuba 的 JRL 开展
- 来源: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止日期: 2026-07-31 23:59（职位页面当地时间）
- 主题: humanoid locomotion / reinforcement learning / online MPC / whole-body control / safe control
- 状态: active；此前已跟踪，本次为截止日期提醒
- 备注: 这是当前追踪列表中最近的已核验截止项。课题使用 RL 处理离散的高层接触与步态决策，并用在线 MPC 保证连续全身运动的可行性和安全性。

</details>
