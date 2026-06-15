[English](../../drafts/legged-daily-2026-06-15.md) | **中文**
# Legged Daily - 2026-06-15

## 摘要
- 精选两篇 6 月 12 日新近 arXiv / RA-L 足式机器人论文：面向无臂双足轮式机器人的力引导跌倒恢复，以及面向 Unitree Go1 的注意力式本体状态估计。
- 保留一篇 6 月 10 日人形 loco-manipulation 强化学习论文，因为它在 Isaac Lab / Unitree G1 上对 dual critic 与 unified critic 做了紧凑的受控比较。
- 精选两个仓库 / 资源：一个新建的 Isaac Lab H1 崎岖地形行走项目，以及一个从四足到人形的 Isaac Lab 教程；二者更适合作为社区代码和学习材料，不宜直接当作标准基线。
- 产业与实验室信号：Figure 发布 Helix 02，称其为全身 loco-manipulation VLA 系统；PSI Lab 的 RSS 2026 Ψ₀ 页面继续强化 USC / NVIDIA / WorldEngine 这条人形 foundation model 线索。
- 招聘信号：NC State HIER Lab 页面列出 2027 PhD / postdoc 预期机会，方向包括 hierarchical RL whole-body control 与 humanoid tele whole-body control；Amazon Personal Robotics 有官方 2026 PhD research intern/co-op 岗位，明确包含 locomotion 但范围较宽。

<details>
<summary><strong>新论文</strong></summary>

### Robust Fall Recovery for Armless Bipedal-Wheeled Robots Via Force-Guided Learning
- Link: https://arxiv.org/abs/2606.14270
- Source: arXiv / RA-L
- Date: 2026-06-12
- Authors: Haidong Hou, Zhangguo Yu, Tao Han, Hengbo Qi, Khaleel Ghazal, Yu Zhang, Yidong Du, Xuechao Chen, Fei Meng
- Topics: fall recovery / bipedal-wheeled robots / constrained reinforcement learning / teacher-student learning / humanoid generalization
- Summary: 提出 FTSR：带阶段式奖励的力引导 teacher-student 强化学习框架，让无臂双足轮式机器人只依赖腿部驱动完成跌倒恢复，并在真实硬件部署，同时报告了向高自由度人形机器人的泛化。
- Notes: 已被 IEEE Robotics and Automation Letters 2026 接收。作者列出的项目页：https://2350575870.github.io/force-guided.github.io/ 。对真实部署很有价值，因为跌倒恢复是足式机器人自主性的关键失效恢复能力。

### GAIT: Legged Robot Proprioceptive State Estimation with Attention over Inertial-Leg Tokens
- Link: https://arxiv.org/abs/2606.14160
- Source: arXiv
- Date: 2026-06-12
- Authors: Young-Rang Seo, Hajun Kim, Sangmin Kim, Dongyun Kang, Hae-Won Park
- Topics: proprioceptive state estimation / attention / inertial-leg tokens / contact uncertainty / quadruped locomotion
- Summary: 将惯性测量和逐腿测量 token 化，构建注意力式本体状态估计器，让网络在没有显式接触估计器的情况下，根据接触状态自动重加权不同传感通道。
- Notes: 在 Unitree Go1 上验证，包括仿真中未建模的碎石地形和训练未见过的步态；适合跟踪学习式 locomotion policy 底层的状态估计设计。

### Critic Architecture Matters: Dual vs. Unified Critics for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.11891
- Source: arXiv / ICRA 2026 Workshop on Reinforcement Learning for Imitation Learning
- Date: 2026-06-10
- Authors: Mehmet Turan Yardımcı
- Topics: humanoid loco-manipulation / reinforcement learning / critic architecture / Isaac Lab / Unitree G1
- Summary: 在 Isaac Lab 中用 Unitree G1 比较 unified critic 与 dual critic 的 loco-manipulation RL 设计；在 13 级顺序课程中，dual critic 带来更快 reaching、更高吞吐和更高 validated reach rate。
- Notes: 篇幅较短的 workshop paper，但对把 imitation / manipulation policy 与 locomotion 目标一起做 RL fine-tuning 时的 critic 架构选择很有启发。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### egeozgul/humanoid-locomotion-isaaclab
- Link: https://github.com/egeozgul/humanoid-locomotion-isaaclab
- Category: RL / locomotion / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: 社区 Isaac Lab 项目，用 4096 个并行环境为 Unitree H1 训练 PPO 崎岖地形行走策略，包含地形课程、奖励曲线和训练指标。
- Notes: README 报告环境为 Isaac Lab 0.45.9 / Isaac Sim 5.0、RSL-RL 2.3.3、393M timesteps、RTX 5070 Ti 上约 1h14m 训练，并在其设置下得到 0.74% fall rate。GitHub API 检查：2026-06-12 创建，2026-06-12 更新，检查时 0 stars。

### Lab-of-AI-and-Robotics/IsaacLab-Tutorial
- Link: https://github.com/Lab-of-AI-and-Robotics/IsaacLab-Tutorial/
- Category: tutorial / RL / locomotion / toolkit
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab
- Deploy: sim
- Summary: 多章节 Isaac Lab 教程，从 Unitree Go2 四足 locomotion 逐步走向 Unitree H1 人形 locomotion，适合作为足式机器人 RL 环境开发学习路线。
- Notes: 更适合作为教学材料，而不是 benchmark。GitHub API 检查：9 stars，2026-06-06 更新。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Jaemin Lee — HIER Lab, NC State University
- Institution: North Carolina State University
- Homepage: https://hier-robotics.github.io/
- Lab / Department: Hybrid Intelligent Experimental Robotics Lab; Department of Mechanical and Aerospace Engineering; Joint Department of Biomedical Engineering at UNC–Chapel Hill and NC State
- Key Topics: legged humanoid and animaloid robotics / loco-manipulation / whole-body control / robot intelligence / hierarchical RL / tele whole-body control
- Notes: 官方实验室页面列出 humanoid loco-manipulation、hybrid dynamical systems、learning-based robotics、safety-critical control、heterogeneous robot teams 和 generative AI for motion；2026 年新闻还包括 NVIDIA Academic Award 支持该实验室人形机器人研究。

### PSI Lab / USC Physical Superintelligence Lab — Ψ₀ project
- Institution: USC / NVIDIA / WorldEngine collaboration signal from project page
- Homepage: https://psi-lab.ai/Psi0/
- Key Topics: humanoid loco-manipulation / foundation models / VLA / real-world humanoid data / egocentric human video
- Notes: RSS 2026 Ψ₀ 项目页介绍了面向人形 loco-manipulation 的开放 foundation model，使用约 829 小时第一视角人类视频和 31 小时人形机器人数据训练，并声明计划开源完整生态。是值得加入 source network 的信号；今日未验证到代码已发布。

### Figure AI — Helix 02
- Institution: Figure AI
- Homepage: https://www.figure.ai/news/helix-02
- Key Topics: humanoid loco-manipulation / whole-body VLA / visuomotor policy / learned whole-body controller / sim-to-real RL
- Notes: 官方公告称 Helix 02 将 Helix 从上半身控制扩展到全身 autonomy，把行走、操作和平衡整合到统一神经系统中；细节仍属于公司自述，应作为产业信号而非可复现实验结果看待。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### HIER Lab — NC State University
- Type: PhD / Postdoc
- Location: Raleigh, North Carolina, USA
- Source: official lab page
- Deadline: unknown / 2027 intake signal
- Topics: hierarchical RL-based whole-body control / tele whole-body control of humanoids / loco-manipulation
- Status: watching
- Notes: 官方页面称实验室预计为 2027 PhD students 和 postdocs 提供机会，并给出 interest form；申请人仍需通过正式研究生招生系统申请。

### Amazon Personal Robotics Group — Research Scientist II Intern / Co-op 2026
- Type: Internship / Co-op
- Location: multiple Amazon locations; exact team/location finalized at offer stage
- Source: official Amazon Jobs page
- Deadline: unknown
- Topics: robotics / manipulation / autonomous mobile robots / mobile manipulation / locomotion / controls / perception / robot learning / planning / HRI
- Status: active
- Notes: 官方岗位面向在读 PhD，招聘 2026 Robotics Research Scientist II intern/co-op，覆盖 Amazon 多个机器人团队；locomotion 被明确列入方向，但岗位范围很宽，相关性取决于最终团队匹配。

### Proposed Removal / Stale Item
- Current Status: 今日不建议删除
- Reason: 之前跟踪的 EPFL BioRob、ETH RSL 和 Field AI 机会从近期官方检查看仍可行动；本次 scheduled draft 未做正式 `jobs.md` 清理。
- Source Checked: daily search and recent official-source checks

</details>
