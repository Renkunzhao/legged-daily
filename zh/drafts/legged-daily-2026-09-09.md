[English](../../drafts/legged-daily-2026-09-09.md) | **中文**
# Legged Daily - 2026-09-09

## 摘要
- TANGO 将语言指令和第一视角 RGB 直接映射为 29 自由度人形动作，仅在仿真中训练后，即可零样本部署到 Unitree G1，在拥挤真实场景中完成全身避障穿行。
- PGMT 在通用人形动作先验上加入动作条件地形感知与地形感知式跟踪放松；其 Unitree G1 实机可通过论文所报最高 37 cm 障碍，并保留遥操作、动态动作跟踪和跌倒恢复能力。
- Mind the Phase 表明，按步态相位分析 effective rank 能揭示整周期平均值掩盖的策略结构；其训练方法从仿真迁移到实体 Spot 后，关节抖动约降低 3 倍。
- 腾讯发布 BSD-3-Clause 的 Unitree 强化学习栈，覆盖 Go2、G1、H1 和 H1_2 的 Isaac Gym 训练、MuJoCo sim-to-sim 验证与实机部署，并附带预训练策略和部署配置。
- 小鹏正式启用人形机器人生产线并展示 IRON 自主走下产线，说明其机器人项目正从研发样机向产线制造推进；本次未核验到新的官方招聘机会。

<details>
<summary><strong>新论文</strong></summary>

### TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body Vision-Language-Action Model
- Link: https://arxiv.org/abs/2609.09158
- Source: arXiv
- Date: 2026-09-08
- Authors: Anqi Li, Yuxin Chen, Zhaobo Li, Zhuo Cao, Junli Ren, Masayoshi Tomizuka, Dhruv Shah
- Topics: humanoid / vision-language-action / navigation / whole-body control / sim-to-real
- Summary: 提出全身视觉—语言导航框架，将自然语言指令和第一视角 RGB 观测转换为 29 自由度关节空间动作，使人形机器人能在拥挤三维环境中进行无碰撞全身穿行。
- Notes: 训练完全在仿真中完成，通过全局路径规划、运动学全身动作生成、障碍感知动作编辑和 RL 跟踪合成动力学可行示范。作者报告无需真实导航训练数据即可零样本部署到 Unitree G1；当前证据来自论文，本次未核验到公开代码。

### PGMT: Perceptive General Motion Tracking for Humanoid Robots
- Link: https://arxiv.org/abs/2609.08511
- Source: arXiv
- Date: 2026-09-08
- Authors: Hongyi Li, Li Peizhuo, Yucheng Tao, Ze Wang, Fangzhou Xu, Jinyi Chen, Yanyan Yuan, Dapeng Jia, Yongbin Jin, Mingfeng Fan, Guillaume Sartoretti, Hongtao Wang
- Topics: humanoid / motion tracking / terrain perception / locomotion / teleoperation / recovery
- Summary: 将通用人形动作跟踪扩展到复杂地形，通过“跟踪与恢复先验 + 动作条件地形局部观测 + 对不可行动作参考的地形感知式放松”实现地形适应。
- Notes: 论文报告在 Unitree G1 上零样本部署，可通过最高 37 cm 的真实障碍；同一策略同时支持地形自适应运动、多样全身行为、遥操作、动态动作跟踪与跌倒恢复。

### Mind the Phase: Effective Rank and Representation Health in Legged Locomotion
- Link: https://arxiv.org/abs/2609.06958
- Source: arXiv / CoRL 2026
- Date: 2026-09-07
- Authors: Felipe Tommaselli, Thiago H. Segreto, Juliano D. Negri, Ricardo V. Godoy, Marcelo Becker
- Topics: quadruped / reinforcement learning / representations / effective rank / sim-to-real
- Summary: 研究运动策略 Jacobian 的 effective rank，说明将分析按摆动相和支撑相划分，可以揭示被整步态平均值掩盖的、与网络架构相关的表征结构。
- Notes: 带 LayerNorm 和残差连接的策略在摆动相比支撑相约多分配两个 effective-rank 维度，而普通 MLP 不呈现这一模式。由此得到的架构与训练方法从仿真迁移到实体 Spot 后，关节抖动约降低 3 倍。项目页特别提醒：rank 越高并不天然代表策略越健康，当前 arXiv 版本也尚非最终 camera-ready 论文。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Unitree RL GYM
- Link: https://github.com/Tencent/legged_rl_gym
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: Isaac Gym / MuJoCo
- Deploy: both
- Summary: 腾讯以 BSD-3-Clause 发布的 Unitree 强化学习栈，支持 Go2、G1、H1 和 H1_2，覆盖 Isaac Gym 训练与策略导出、MuJoCo sim-to-sim 检查以及实体机器人部署。
- Notes: 仓库创建于 2026-09-09，包含各机器人环境、MuJoCo 与实机配置、预训练策略文件、Unitree SDK 2 通信以及仿真/实机演示。项目建立在 legged_gym 和 rsl_rl 之上；初始仓库体量较大且刚刚公开，其复现性和长期维护成熟度仍待社区验证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### XPENG Robotics / IRON
- Institution: XPENG
- Homepage: https://www.xpeng.com/news/01a080371029a057bc8e8a02a2c6012b
- Lab / Department: Humanoid Robotics / Physical AI
- Key Topics: humanoid / whole-body mobility / physical AI / robot manufacturing / commercialization
- Notes: 小鹏于 2026-09-08 宣布人形机器人生产线投产，并展示一台 IRON 完成生产后自主走下产线。公司称核心制造流程自动化率超过 80%，IRON 具有全身 76 个自由度、每只手 21 个自由度，并计划在 2026 年底进入量产、先在自有门店和园区落地。这些规格和时间表均为公司官方披露，不等同于经独立验证的实际量产规模。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次未从官方来源核验到足够新、仍有效且高置信度的腿足机器人相关机会。

</details>
