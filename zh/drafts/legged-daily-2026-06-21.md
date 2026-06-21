[English](../../drafts/legged-daily-2026-06-21.md) | **中文**
# Legged Daily - 2026-06-21

## 摘要
- 周末 arXiv 更新较少，今天优先筛选 6 月 17-18 日已验证批次里的高信号论文，以及官方项目页 / 仓库页。
- SWAP 把对称等变结构嵌入四足跑酷 world model，声称在 Apollo 四足上实现 2.13 m 跳沟和 1.63 m 登台。
- CTS-MoE 面向离散地形的感知式运动控制，用视觉 / 地形感知路由 mixture-of-experts 策略，并在 Unitree Go1 上做了硬件验证。
- HALOMI 是从第一视角人类示教迁移到 Unitree G1 的人形 loco-manipulation 框架，强调主动感知与流形约束全身控制器。
- 仓库信号值得预览：SurGE 腿足机器人可微协同设计代码、Pronto ROS 2 状态估计栈、Go2 粗糙地形 IsaacLab 到 MuJoCo / 硬件部署管线。
- 机会信号：EPFL BioRob 有 Fall 2026 人形 neuromechanics PhD/Postdoc 项目；ETH RSL 继续列出滚动 PhD/Postdoc/研究工程岗位。

<details>
<summary><strong>新论文</strong></summary>

### SWAP: Symmetric Equivariant World-Model for Agile Robot Parkour
- Link: https://arxiv.org/abs/2606.19928
- Source: arXiv
- Date: 2026-06-18
- Authors: Kaixin Lan, Ze Wang, Hongyi Li, Lei Jiang, Chaojie Fu, Chengkai Su, Choi Lam Wong, Yongbin Jin, Hongtao Wang
- Topics: quadruped / parkour / world models / symmetry equivariance / reinforcement learning
- Summary: 提出端到端的对称等变 world model 和 actor-critic 策略，把左右对称作为 latent dynamics 与控制策略的结构先验；论文报告 Apollo 四足实机 2.13 m 跳沟、1.63 m 登台，以及户外环境零样本迁移。
- Notes: 项目页：https://swap-parkour.github.io。适合跟踪 world-model locomotion 与结构先验方向。

### CTS-MoE: Implicit Terrain Adaptation via Mixture-of-Experts for Perceptive Locomotion
- Link: https://arxiv.org/abs/2606.19633
- Source: arXiv
- Date: 2026-06-17
- Authors: Francisco Affonso, Matheus P. Angarola, Ana Luiza Mineiro, Aditya Potnis, Marcelo Becker, Girish Chowdhary
- Topics: legged locomotion / quadruped / perception / mixture-of-experts / reinforcement learning / terrain adaptation
- Summary: 针对台阶、沟壑、斜坡和地形过渡等不连续地形，提出 dense MoE actor、感知条件路由和 task-specific value heads；部署时根据感知隐式适应地形，不依赖显式任务标签。
- Notes: 项目页：https://cts-moe.github.io/。与 terrain-adaptive policy architecture 和 concurrent teacher-student RL 相关。

### HALOMI: Learning Humanoid Loco-Manipulation with Active Perception from Human Demonstrations
- Link: https://arxiv.org/abs/2606.18772
- Source: arXiv
- Date: 2026-06-17
- Authors: Zehui Zhao, Yuxuan Zhao, Gaojing Zhang, Chenxi Liu, Maolin Zheng, Wenzhao Lian
- Topics: humanoid / loco-manipulation / imitation learning / active perception / whole-body control / Unitree G1
- Summary: 提出从第一视角人类示教到人形 loco-manipulation 的可扩展管线，结合 UMI 风格手部数据、头戴式第一视角感知、视角对齐、controller-aware reference adaptation 和流形约束全身控制器；在 Unitree G1 三个量化真实任务上报告平均 85% 成功率。
- Notes: 项目页：https://halomi-humanoid.github.io。适合跟踪 human-data-to-humanoid transfer。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### ARCaD-Lab-UM/surge-codesign
- Link: https://github.com/ARCaD-Lab-UM/surge-codesign
- Category: control / RL / co-design / toolkit
- Robot Type: legged / hopper
- Simulator: Isaac Gym
- Deploy: both
- Summary: “SurGE: Surrogate Gradient-guided Evolution for Co-design of Legged Robots with Parallel Elasticity”的官方实现，用 surrogate-gradient-injected CMA-ES 联合优化并联弹性腿足机器人的弹簧设计与控制策略。
- Notes: 仓库标注 IROS 2026，论文 coming soon；包含预训练 checkpoint 和定制 legged-gym / rsl_rl 包。会议 / 论文状态目前按作者声明处理，后续需等官方 proceedings 或 arXiv 验证。

### ori-drs/pronto
- Link: https://github.com/ori-drs/pronto
- Category: state estimation / toolkit / ROS
- Robot Type: humanoid / quadruped / general legged
- Simulator: none
- Deploy: hardware
- Summary: 面向腿足机器人的模块化 EKF 状态估计器，融合本体感知与外部传感器信息，包含 biped 与 quadruped leg odometry 模块；README 标注主分支已支持 ROS 2 Humble。
- Notes: 历史上用于 Atlas、Valkyrie、HyQ 和 ANYmal；最近仍有更新，可作为经典状态估计 baseline 跟踪。

### gpai-robotics/go2-lab-rough-terrain-locomotion
- Link: https://github.com/gpai-robotics/go2-lab-rough-terrain-locomotion
- Category: RL / locomotion / deployment pipeline
- Robot Type: quadruped / Unitree Go2
- Simulator: IsaacLab / MuJoCo
- Deploy: both
- Summary: Unitree Go2 粗糙地形公开训练 / 部署管线，使用 blind history-conditioned asymmetric PPO；actor 只用可部署观测，critic 训练时使用 privileged terrain/dynamics 信号，并包含 IsaacLab 训练、MuJoCo/Unitree FSM 验证和硬件部署说明。
- Notes: 星标较少，但部署文档细，适合先预览再决定是否进入正式仓库列表。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Center for X-Mechanics / Zhejiang University and Mirrorme Technology
- Institution: Zhejiang University; ZJU-Hangzhou Global Scientific and Technology Innovation Center; Mirrorme Technology Co., Ltd.
- Homepage: https://swap-parkour.github.io
- arXiv: https://arxiv.org/abs/2606.19928
- GitHub: https://github.com/swap-parkour/swap-parkour.github.io
- Key Topics: quadruped / parkour / world models / symmetry equivariance / agile locomotion
- Notes: SWAP 是高敏捷四足跑酷里 symmetry-aware world model 的强信号；建议继续跟踪代码 / 数据释放和 Apollo 四足相关演示。

### HIROL Lab / Shanghai Jiao Tong University
- Institution: Shanghai Jiao Tong University
- Homepage: https://hirol.sjtu.edu.cn/
- arXiv: https://arxiv.org/abs/2606.18772
- GitHub: https://halomi-humanoid.github.io
- Key Topics: humanoid / loco-manipulation / active perception / imitation learning / whole-body control
- Notes: HALOMI 把第一视角人类示教收集与 Unitree G1 人形执行连接起来；该组值得作为人形 manipulation 与 active perception 来源跟踪。

### BioRobotics Laboratory / EPFL
- Institution: EPFL
- Homepage: https://www.epfl.ch/labs/biorob/
- Key Topics: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- Notes: 官方 openings 页面列出 Fall 2026 Postdoc 和 PhD 项目，主题是利用人形机器人研究并借鉴人类运动 neuromechanics。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL BioRobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: unknown
- Topics: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- Status: active
- Notes: 官方页面列出 Fall 2026 一个 Postdoc 和一个 PhD position，主题为 using humanoid robots investigating and leveraging human locomotion neuromechanics；PhD 申请者需要先被 EPFL doctoral program 录取。

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / teleoperation / actuation and system design
- Status: active
- Notes: ETH RSL 官方页面继续列出多类滚动岗位，包括腿足机器人和移动操作相关 PhD/Postdoc/研究工程岗位；申请需使用页面链接的表单，不走邮件。

</details>
