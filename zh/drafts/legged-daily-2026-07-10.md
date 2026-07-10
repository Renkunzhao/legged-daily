[English](../../drafts/legged-daily-2026-07-10.md) | **中文**
# Legged Daily - 2026-07-10

## 摘要
- 今天最高信号的论文主题是接触丰富的人形机器人移动操作：ContactMimic 在人形动作跟踪中加入显式身体部位接触命令，并报告了 Unitree G1 的真实机器人接触控制验证。
- 极端坡面人形行走仍在活跃推进：HumoSlope 用坡面自适应 ZMP 正则和生物力学奖励门控，让机器人在陡峭草坡上实现盲式、本体感知行走。
- 交互式人形遥操作正在变成数据采集接口：Vision Pro + LLM 辅助的 Unitree H1 系统结合了语音行走命令、VR 操作重定向和多模态记录。
- 仓库信号中等，不是当天爆发式更新；今天最可操作的是 Isaac Lab / Unitree Go2 行走基线，带 6 月发布的 push-recovery 扩展和明确的鲁棒性课程训练细节。
- 实验室/来源跟踪：ContactMimic 指向 Saurabh Gupta 组，适合作为人形移动操作来源继续跟踪；STL 四足行走项目页作为 CoRL 2026 投稿信号值得观察。
- 招聘信号：今天没有验证到新的腿足机器人专项机会；保留现有 active watchlist，本轮不建议删除条目。

<details>
<summary><strong>新论文</strong></summary>

### ContactMimic: Humanoid Object Interaction via Contact Control
- Link: https://arxiv.org/abs/2607.08742
- Source: arXiv
- Date: 2026-07-09
- Authors: Xinyao Li, Xialin He, Runpei Dong, Saurabh Gupta
- Topics: humanoid / loco-manipulation / contact control / motion tracking / sim-to-real
- Summary: 提出 ContactMimic，在关键点轨迹之外加入显式的身体部位二值接触命令，让同一姿态动作可以按命令产生或抑制物理接触。
- Notes: 项目页报告了 Unitree G1 在 5 类接触丰富动作上的真实机器人验证，并强调仅靠关键点跟踪不足以定义坐下、擦白板、推物体、倚靠等任务。

### Physics-Guided Biomechanical Gait Adaptation for Humanoid Locomotion on Extreme Sloped Terrains
- Link: https://arxiv.org/abs/2607.07830
- Source: arXiv
- Date: 2026-07-08
- Authors: Xuanyu Chen, Mohan Liu, Dengchen Mei, Zhihao Gu, Haitian Zhang, Kaimin Mao, Haiyue Zhu, Shijun Yan, Lin Wang
- Topics: humanoid / locomotion / reinforcement learning / slope traversal / sim-to-real / proprioceptive control
- Summary: 提出 HumoSlope，两阶段物理引导框架结合坡面自适应 ZMP 正则与生物力学坡面步态适配器，缓解陡坡上常见的低重心蹲伏步态退化。
- Notes: 论文报告了在最高 62.7% / 32.1° 室外草坡上的盲式穿越；部署 actor 依赖本体感知，不需要在线外感知。

### Immersive Social Interaction with VR and LLM-Assisted Humanoids
- Link: https://arxiv.org/abs/2607.07430
- Source: arXiv
- Date: 2026-07-08
- Authors: Niraj Pudasaini, Geeta Chandra Raju Bethala, Pranav Doma, Anthony Tzes, Yi Fang
- Topics: humanoid / teleoperation / VR / LLM-assisted control / locomotion commands / data collection
- Summary: 描述了基于 Apple Vision Pro 的 Unitree H1 遥操作系统，结合语音控制行走、VR 操作重定向、灵巧手控制和双向社交交互。
- Notes: 新手用户评估中，物体操作成功率为 80%，社交传方块任务成功率为 70%；系统记录的多模态日志被定位为后续模仿学习数据。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### BrandoUlissi/isaaclab-go2-locomotion
- Link: https://github.com/BrandoUlissi/isaaclab-go2-locomotion
- Category: RL / control / training baseline
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: NVIDIA Isaac Lab 中的 Unitree Go2 强化学习行走基线，包含 PPO 训练、确定性回放脚本、TensorBoard 绘图和 push-recovery 扩展文档。
- Notes: 已验证的最新 release `v0.2.0-pushrecovery` 发布于 2026-06-03，加入混合脉冲/持续扰动课程；release 报告在仿真中对 120 N 峰值脉冲负载达到 87.5% 恢复率。

### CMUYUY/legged-gym-in-isaac-lab
- Link: https://github.com/CMUYUY/legged-gym-in-isaac-lab
- Category: RL / simulator migration / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: 将经典 `legged_gym` 的 ANYmal-C 崎岖地形强化学习设置从 Isaac Gym 风格 API 迁移到 NVIDIA Isaac Lab，包括 DirectRLEnv、USD 资产、观测/动作/奖励和 RSL-RL 训练衔接。
- Notes: 不是 2026-07 的新更新，但对把旧 Isaac Gym 腿足行走代码迁移到 Isaac Lab 的团队有参考价值。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Saurabh Gupta / UIUC Robotics and Embodied AI
- Institution: University of Illinois Urbana-Champaign
- Homepage: https://saurabhg.web.illinois.edu/
- arXiv: https://arxiv.org/abs/2607.08742
- Lab / Department: Robotics and Embodied AI research group / UIUC Computer Science
- Key Topics: humanoid / loco-manipulation / embodied AI / contact-rich interaction / robot learning
- Notes: ContactMimic 给出了该作者网络在人形接触控制方向的强信号；后续应跟踪 contact-conditioned humanoid motion tracking 相关项目页和代码发布。
- Students and Representative Works:
  - [Xinyao Li](https://lixinyao11.github.io/contactmimic-page/) — [ContactMimic: Humanoid Object Interaction via Contact Control](https://arxiv.org/abs/2607.08742)

### STL-based Quadruped Locomotion Project
- Institution: unknown / anonymous CoRL 2026 submission
- Homepage: https://stl-locomotion.github.io/
- Lab / Department: unknown
- Key Topics: quadruped / reinforcement learning / temporal logic specifications / reward shaping / gait control / MuJoCo XLA
- Notes: 项目页展示了一个 CoRL 2026 投稿，主题是用 Signal Temporal Logic 奖励塑形训练 Barkour 四足在 MJX 中行走。由于作者匿名，在作者公开前应作为来源观察信号，而不是确认实验室条目。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### No newly verified legged-specific opening found today
- Type: watching
- Location: unknown
- Source: current daily search / existing `jobs.md` watchlist
- Deadline: unknown
- Topics: locomotion / humanoid / quadruped / RL / MPC / robot learning
- Status: watching
- Notes: 部分网页搜索查询遇到 bot-detection，因此本轮没有新增招聘。现有 `jobs.md` active 条目仍是最值得监控的机会，尤其是 EPFL Biorobotics、ETH RSL、RoMI Lab、CUHK Legged Robot Lab、Legged AI Lab / Shanghai Innovation Institute、Field AI、NVIDIA GEAR 和 Amazon 机器人相关岗位。

</details>
