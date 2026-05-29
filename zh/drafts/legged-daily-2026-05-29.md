[English](../../drafts/legged-daily-2026-05-29.md) | **中文**
# Legged Daily - 2026-05-29

## 摘要
- 今天的人形运动信号明显偏向高动态与全身任务：SPRINT 使用频率自适应谱先验，在 Unitree G1 上报告零样本 sim-to-real 冲刺，峰值速度 6 m/s。
- HumanoidMimicGen 是高信号的人形移动操作数据论文：通过全身规划从少量源演示生成大规模演示，并报告生成数据与真实数据联合训练能提升真实策略表现。
- ETH Zurich RSL 发布一篇技术报告，讨论如何让 SAC 在大规模并行腿足运动训练中接近 PPO，对未来在线适应和硬件微调有参考价值。
- 新仓库信号集中在人形移动操作生态：WholeBodyVLA、SoccerLab、PHUMA 分别覆盖 VLA 资源、足球技能/多智能体平台、物理约束人形运动数据。
- ETH Zurich RSL 官方仍列出与腿足机器人、移动操作、控制、学习、规划和真实部署相关的 PhD、博后、研究/软件工程、机器人设计和嵌入式岗位。

<details>
<summary><strong>新论文</strong></summary>

### SPRINT: Efficient Spectral Priors for Humanoid Athletic Sprints
- 链接: https://arxiv.org/abs/2605.28549
- 来源: arXiv
- 日期: 2026-05-27
- 作者: Yantong Wei, Kaihong Huang, Hainan Pan, Jiawei Luo, Jiawei Zhou, Ziyan Mai, Zhiwen Zeng, Yaonan Wang, Huimin Lu
- 主题: humanoid / sprinting / spectral priors / imitation learning / reinforcement learning / sim-to-real / Unitree G1
- 摘要: 提出频率自适应谱先验，从仅五段参考运动序列中生成可行的人形关节轨迹，并指导策略覆盖行走、慢跑和冲刺。
- 备注: 摘要报告在 Unitree G1 上零样本 sim-to-real，峰值冲刺速度 6 m/s，并实现平滑步态切换；发现时项目页为匿名链接，进入主列表前应复核作者和资产信息。

### HumanoidMimicGen: Data Generation for Loco-Manipulation via Whole-Body Planning
- 链接: https://arxiv.org/abs/2605.27724
- 来源: arXiv
- 日期: 2026-05-26
- 作者: Kevin Lin, Ajay Mandlekar, Caelan Reed Garrett, Nikita Chernyadev, Yu Fang, Runyu Ding, Yuqi Xie, Justin Tran, Linxi Fan, Yuke Zhu
- 主题: humanoid / loco-manipulation / imitation learning / demonstration generation / whole-body planning / Unitree G1
- 摘要: 通过把少量源演示中的接触丰富全身技能迁移到新的物体位姿，并交织手臂技能、运动规划和操作规划，生成稳定的人形移动操作演示。
- 备注: 项目页报告一个含 9 个工业风格任务的模拟 G1 benchmark，并显示生成数据与少量真实数据联合训练，比仅用真实数据训练的真实世界策略成功率高 20%。

### Bridging the Gap: Enabling Soft Actor Critic for High Performance Legged Locomotion
- 链接: https://arxiv.org/abs/2605.24975
- 来源: arXiv
- 日期: 2026-05-24
- 作者: Gianluca Sabatini, Chenhao Li, Marco Hutter
- 主题: legged locomotion / reinforcement learning / Soft Actor-Critic / PPO / IsaacLab / online adaptation
- 摘要: 分析 SAC 在大规模并行腿足运动训练中落后 PPO 的原因，并通过策略初始化、timeout-aware critic targets、多步回报等修改缩小性能差距。
- 备注: HTML 版本说明该文是配套开源 RSL-RL-SAC 发布的技术报告，但本次运行未验证到官方代码 URL；加入仓库条目前应继续检查 RSL-RL 生态。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### WholeBodyVLA
- 链接: https://github.com/OpenDriveLab/WholebodyVLA
- 类别: toolkit / resource list / VLA / loco-manipulation
- 机器人类型: humanoid
- 仿真器: none
- 部署: data
- 摘要: ICLR 2026 人形 VLA 项目的资源仓库；方法从无动作标注的第一视角视频学习 latent actions，并结合面向移动操作的 RL 策略做全身控制。
- 备注: README 明确表示目前没有具体开源代码时间表；现阶段更适合作为项目/资源中心和文献 watchlist，而不是可执行代码库。

### SoccerLab
- 链接: https://github.com/Renforce-Dynamics/soccerLab
- 类别: RL / simulator / toolkit
- 机器人类型: humanoid / legged
- 仿真器: IsaacLab / MuJoCo-Warp / MJLab
- 部署: sim
- 摘要: 面向人形机器人足球的全栈平台，覆盖起身恢复、运动、踢球、带球、多智能体组合和有限状态机技能切换，支持 IsaacLab 与 MJLab 后端。
- 备注: 仓库仍在活跃开发，包含 fall recovery、AMP-guided kicking、RSL-RL PPO dribbling、Unitree G1 相关运动 baseline 和多智能体足球任务结构。

### PHUMA
- 链接: https://github.com/DAVIAN-Robotics/PHUMA
- 类别: dataset / retargeting / toolkit
- 机器人类型: humanoid
- 仿真器: MuJoCo / ProtoMotions
- 部署: data
- 摘要: PHUMA 的代码与数据管线；PHUMA 是一个通过数据清洗和物理约束 retargeting 从大规模人体运动数据构建的物理 grounded 人形运动数据集。
- 备注: 仓库链接论文、项目页、Hugging Face 数据集、预构建 G1 与 H1-2 数据，并说明已被 NVIDIA ProtoMotions 原生支持，可直接用于策略训练。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### NVIDIA / UT Austin HumanoidMimicGen team
- 机构: NVIDIA; The University of Texas at Austin
- 主页: https://humanoidmimicgen.github.io/
- arXiv: https://arxiv.org/abs/2605.27724
- 关键主题: humanoid / loco-manipulation / imitation learning / synthetic data generation / whole-body planning / VLA data
- 备注: 这是一个值得跟踪的人形移动操作数据源信号：它连接了模拟 G1 benchmark、生成演示和 sim-plus-real 联合训练，而不是只报告单个控制器。

### OpenDriveLab WholeBodyVLA team
- 机构: OpenDriveLab 及合作者；进入主列表前需核实具体机构归属
- 主页: https://opendrivelab.com/wholebodyvla
- GitHub: https://github.com/OpenDriveLab/WholebodyVLA
- 关键主题: humanoid / Vision-Language-Action / latent action learning / loco-manipulation / egocentric video
- 备注: WholeBodyVLA 是值得跟踪的人形 VLA hub：仓库整理了 2025-2026 年相关人形移动操作工作，并体现作者围绕 manipulation-aware locomotion 视频学习 latent action 的方向。

### ETH Zurich Robotic Systems Lab
- 机构: ETH Zurich
- 主页: https://rsl.ethz.ch/
- 实验室 / 系: Robotic Systems Lab
- 关键主题: legged robots / mobile manipulation / MPC / reinforcement learning / perception / field robotics / robot design
- 备注: RSL 同时出现在今天的 SAC 论文和官方招聘信号中；后续继续跟踪 RSL-RL、IsaacLab、ANYmal 和真实世界腿足部署相关的算法发布。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab
- 类型: PhD / Postdoc / Research Engineer / Software Engineer / Robot Design Research Staff / Embedded Systems Engineer
- 地点: Zurich, Switzerland
- 来源: official website
- 截止时间: rolling / unknown
- 主题: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / navigation / actuation / systems
- 状态: active
- 备注: RSL 官方 openings 页面列出持续招收 PhD 和博后，同时有研究人员/软件工程、机器人设计、嵌入式系统岗位，方向包括腿足机器人、移动操作、挖掘机机器人、真实机器人挑战、工业展示和搜救部署；申请通过 ETH 外部表单，不通过邮件。

</details>
