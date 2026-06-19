[English](../../drafts/legged-daily-2026-06-19.md) | **中文**
# Legged Daily - 2026-06-19

## 摘要
- 今天最强的 locomotion/control 信号是 SWAP：面向四足 parkour 的对称等变世界模型，摘要中报告了实机跨越 2.13 m 间隙、攀爬 1.63 m 平台。
- CTS-MoE 是很实用的感知式运动控制更新：用 perception-conditioned MoE routing 加 task-specific critics，让 Unitree Go1 在台阶、间隙、坡面和地形切换中做隐式地形适应。
- HALOMI 推进 humanoid loco-manipulation：从人类示范中学习主动感知和头手轨迹跟踪，并在 Unitree G1 真实任务上验证。
- HumanoidArena 给出了 egocentric hierarchical whole-body humanoid learning 的 benchmark / project 信号；项目页和页面仓库已上线，但核心代码仓库检查时还不可公开访问。
- EPFL BioRob 有 Fall 2026 Postdoc + PhD 机会，主题是人类步态 neuromechanics 与 bio-inspired humanoid controllers。

<details>
<summary><strong>新论文</strong></summary>

### SWAP: Symmetric Equivariant World-Model for Agile Robot Parkour
- Link: https://arxiv.org/abs/2606.19928
- Source: arXiv
- Date: 2026-06-18
- Authors: Kaixin Lan, Ze Wang, Hongyi Li, Lei Jiang, Chaojie Fu, Chengkai Su, Choi Lam Wong, Yongbin Jin, Hongtao Wang
- Topics: quadruped, agile locomotion, parkour, world models, equivariance, reinforcement learning
- Summary: 提出端到端的对称等变 latent world model 和 actor-critic 结构，把左右对称作为结构先验，用于提升四足 parkour 的样本效率与几何泛化能力。
- Notes: 摘要报告了真实机器人跨越 2.13 m 间隙、攀爬 1.63 m 平台，并在不同户外地形上展示 zero-shot transfer；值得后续检查代码、视频和硬件细节。

### CTS-MoE: Implicit Terrain Adaptation via Mixture-of-Experts for Perceptive Locomotion
- Link: https://arxiv.org/abs/2606.19633
- Source: arXiv
- Date: 2026-06-17
- Authors: Francisco Affonso, Matheus P. Angarola, Ana Luiza Mineiro, Aditya Potnis, Marcelo Becker, Girish Chowdhary
- Topics: quadruped, perceptive locomotion, reinforcement learning, mixture-of-experts, terrain adaptation, sim-to-real
- Summary: 在 concurrent teacher-student RL 框架中结合 dense MoE actor、基于感知的 routing 和 task-specific critic heads，使 Unitree Go1 部署时无需显式 task label 也能适应不连续地形。
- Notes: 项目页显示在已见和未见真实地形上做了硬件测试；仿真中 gap 地形相对 perceptive baseline 成功率提升 29.3 个百分点。

### HALOMI: Learning Humanoid Loco-Manipulation with Active Perception from Human Demonstrations
- Link: https://arxiv.org/abs/2606.18772
- Source: arXiv
- Date: 2026-06-17
- Authors: Zehui Zhao, Yuxuan Zhao, Gaojing Zhang, Chenxi Liu, Maolin Zheng, Wenzhao Lian
- Topics: humanoid, loco-manipulation, active perception, imitation learning, human demonstrations, Unitree G1
- Summary: 提出从人类示范学习 humanoid loco-manipulation 的可扩展框架：采集 ego-view 和 wrist-view 观测，做 observation/action 对齐，并用 manifold-constrained head-hand tracking controller 转移到 Unitree G1。
- Notes: 论文摘要报告三个定量真实任务平均成功率 85%，并展示 dynamic tossing、deep-squat grasping 等定性 demo。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### HumanoidArena / humanoidarena.github.io
- Link: https://github.com/HumanoidArena/humanoidarena.github.io
- Category: benchmark / project page / dataset-preview
- Robot Type: humanoid
- Simulator: IsaacLab
- Deploy: browser / sim
- Summary: HumanoidArena 的公开项目页仓库；HumanoidArena 是面向 egocentric hierarchical whole-body humanoid control 的 simulation-first benchmark，包含 7 个 leg-critical HOI/HSI 任务。
- Notes: 项目页写明核心栈包括 TWIST2、IsaacLab、LeRobot，并链接到 `HumanoidArena/humanoid_arena`；检查时该代码仓库尚不可公开访问，因此先按 project/page 信号而非可运行代码发布记录。

### halomi-humanoid / halomi-humanoid.github.io
- Link: https://github.com/halomi-humanoid/halomi-humanoid.github.io
- Category: project page / demo hub
- Robot Type: humanoid
- Simulator: none
- Deploy: browser / hardware demos
- Summary: HALOMI 的静态项目页仓库，承载论文页、demo 视频、代码/数据/slides 链接占位，以及 humanoid loco-manipulation from human demonstrations 的 follow-up work 区块。
- Notes: 值得作为 watch target：仓库 README 明确预留 code / dataset 资源入口；但本次抓取到的项目页正文仍较简略。

### OpenDriveLab / WholebodyVLA
- Link: https://github.com/OpenDriveLab/WholebodyVLA
- Category: VLA / resource list / project page
- Robot Type: humanoid
- Simulator: none
- Deploy: browser / reference
- Summary: WholeBodyVLA 的资源仓库；WholeBodyVLA 是面向大空间 humanoid loco-manipulation 的 unified latent VLA 框架，从 action-free egocentric videos 中学习 latent actions，并结合 loco-manipulation-oriented RL policy。
- Notes: 仓库明确说明当前没有具体开源代码时间表，因此应作为 reference/resource hub 跟踪，而不是当作已可用实现。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### HIROL Lab
- Institution: Shanghai Jiao Tong University
- Homepage: https://hirol.sjtu.edu.cn/
- GitHub: https://github.com/halomi-humanoid/halomi-humanoid.github.io
- Lab / Department: HIROL Lab
- Key Topics: humanoid, loco-manipulation, active perception, imitation learning, human demonstrations
- Notes: HALOMI 项目页链接到 HIROL Lab，主题集中在从人类数据学习带主动感知的 humanoid loco-manipulation；适合作为 Unitree G1 whole-body manipulation 和潜在 code/data release 的跟踪源。
- Students and Representative Works:
  - Zehui Zhao — [HALOMI: Learning Humanoid Loco-Manipulation with Active Perception from Human Demonstrations](https://arxiv.org/abs/2606.18772)

### HumanoidArena Team
- Institution: The Hong Kong University of Science and Technology (Guangzhou); Beijing University of Technology; Harbin Institute of Technology, Shenzhen; Shenzhen MSU-BIT University; JD Explore Academy
- Homepage: https://humanoidarena.github.io/
- GitHub: https://github.com/HumanoidArena/humanoidarena.github.io
- Key Topics: humanoid, egocentric control, whole-body learning, simulation benchmark, HOI, HSI
- Notes: 项目页将 HumanoidArena 定位为 simulation-first benchmark，包含 7 个 leg-critical tasks，并围绕 visual、semantic、execution、cross-GMT robustness 做评测。
- Students and Representative Works:
  - Taowen Wang — [HumanoidArena: Benchmarking Egocentric Hierarchical Whole-body Learning](https://arxiv.org/abs/2606.17833)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL BioRob — Biorobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: rolling / until filled
- Topics: humanoid, human locomotion, neuromechanics, bio-inspired locomotion controllers, reinforcement learning, legged control
- Status: active
- Notes: 官方页面显示 Fall 2026 有 1 个 Postdoc 和 1 个 PhD 名额，方向是用 humanoid robots 研究和利用人类步态 neuromechanics。Postdoc 申请邮件发给 Prof. Auke Ijspeert；PhD 申请者需先申请 EPFL 博士项目。页面说明从现在开始持续审理直到招满，理想开始时间是 2026 年 9 月。

</details>
