[English](../../drafts/legged-daily-2026-06-02.md) | **中文**
# Legged Daily - 2026-06-02

## 摘要
- 今天最强的论文信号集中在人形移动操作数据生成、稀疏落足地形上的感知式 locomotion，以及学习型人形全身跟踪策略的运行时安全约束。
- LEGS 值得重点跟踪：它用 3D Gaussian Splatting 真实感场景生成免遥操作 VLA 训练数据，并报告了 Unitree G1 真实移动操作实验。
- GLAD 是强相关的人形 locomotion 论文：它把全局地形上下文和局部落足几何显式分解，并报告了基于 Unitree G1 机载 LiDAR 的 zero-shot sim-to-real。
- ConstrainedMimic 适合放入安全控制观察列表：它通过 operational-space control 和 CBF 风格约束，把运行时运动学/动力学约束加入 RL 全身跟踪策略。
- 仓库信号偏实用实现：PHUMA 面向人形 locomotion 数据集，AMP Running Baseline 面向 Unitree G1 马拉松式跑步训练，convex-mpc-biped 是小型 MuJoCo 双足凸 MPC 栈。
- EPFL BioRob 与 ETH RSL 的官方招聘信号仍为活跃；今天未发现需要拟删除的过期条目。

<details>
<summary><strong>新论文</strong></summary>

### LEGS: Fine-Tuning Teleop-Free VLAs for Humanoid Loco-manipulation in an Embodied Gaussian Splatting World
- Link: https://arxiv.org/abs/2606.01458
- Source: arXiv
- Date: 2026-05-31
- Authors: Hojune Kim, Timothy Chen, Jiankai Sun, Lars W. Osterberg, Qianzhong Chen, Ke Wang, Mac Schwager
- Topics: 人形机器人 / 移动操作 / VLA / 合成数据 / 3D Gaussian Splatting / sim-to-real / Unitree G1
- Summary: 提出 LEGS，一个把机器人/物体 mesh 前景叠加到真实感 3D Gaussian Splatting 背景中的混合仿真器，并用程序化 motion primitives 生成无需人工遥操作标注的人形移动操作示范；论文报告在真实 Unitree G1 pick-and-place 任务中，纯 LEGS 数据微调的 VLA 策略达到或超过遥操作数据训练基线。
- Notes: 项目页：https://legsvla.github.io/。项目页描述了 1,110 次真实机器人实验、3 类任务和 3 个 VLA backbone；项目页显示匿名机构，作者列表中包含 Mac Schwager。

### Global-Local Attention Decomposition for Terrain Encoding in Humanoid Perceptive Locomotion
- Link: https://arxiv.org/abs/2606.00637
- Source: arXiv
- Date: 2026-05-30
- Authors: Shengcheng Fu, Yang Zhang, Zhanxiang Cao, Liyun Yan, Yizhi Chen, Yunpeng Yin, Yue Gao
- Topics: 人形机器人 / 感知式 locomotion / 地形编码 / 注意力机制 / 强化学习 / sim-to-real / Unitree G1
- Summary: 提出 GLAD，一个 coarse-to-fine 地形编码器，将机器人中心 elevation map 的全局上下文注意力与状态条件化的局部落足几何注意力分开，用于提升人形机器人在沟槽、踏脚石、楼梯、窄路和障碍密集地形上的运动能力。
- Notes: arXiv 摘要报告了在 Unitree G1 人形机器人上使用机载 LiDAR 的真实 zero-shot sim-to-real 部署。

### Constrained Whole-Body Tracking for Humanoid Robots
- Link: https://arxiv.org/abs/2606.00374
- Source: arXiv
- Date: 2026-05-29
- Authors: Daniel Morton, Pranit Mohnot, Marco Pavone
- Topics: 人形机器人 / 全身跟踪 / 强化学习 / 安全约束 / control barrier functions / operational space control / Unitree G1
- Summary: 提出 ConstrainedMimic，一个给学习型人形全身跟踪策略施加实时运行时约束的框架；它结合全身运动学/动力学、operational-space control 思路和 CBF 风格约束，在模拟 Unitree G1 跟踪与遥操作实验中展示了自碰/外部障碍避碰、关节限位和质心稳定性约束。
- Notes: arXiv 摘要称软件会在发表时免费开放；今天未验证到公开代码链接。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### PHUMA
- Link: https://github.com/DAVIAN-Robotics/PHUMA
- Category: 数据集 / 重定向 / 工具包
- Robot Type: 人形机器人
- Simulator: Isaac / ProtoMotions 集成；面向人形 locomotion 的数据流水线
- Deploy: data / sim
- Summary: PHUMA 的代码与数据流水线，用物理约束筛选和重定向人类运动，构建 physically grounded humanoid locomotion dataset，支持 Unitree G1 与 H1-2 等人形平台。
- Notes: README 链接了 arXiv 论文、项目页和 Hugging Face 数据集，并说明已被 NVIDIA ProtoMotions 原生支持；适合人形 imitation learning 与 motion prior 流水线跟踪。

### AMP Running Baseline
- Link: https://github.com/Jiarui-Xie/AMP_Running_baseline
- Category: RL / 模仿学习 / locomotion baseline
- Robot Type: 人形机器人
- Simulator: Isaac Lab
- Deploy: both
- Summary: 面向 2026 北京亦庄人形机器人半程马拉松的 Unitree G1 locomotion 训练代码库，基于 Isaac Lab、Adversarial Motion Priors、motion imitation、domain randomization、checkpoint 和硬件部署说明。
- Notes: README 描述 BASE 与高速 post-training 版本、SONIC 风格 actuator modeling、action-delay domain randomization 和 baseline checkpoint；作为应用型 G1 跑步 baseline 有参考价值，但复用前仍需核查真实验证细节。

### convex-mpc-biped
- Link: https://github.com/ispaik06/convex-mpc-biped
- Category: MPC / 控制
- Robot Type: 人形机器人 / 双足
- Simulator: MuJoCo
- Deploy: sim / browser viewer
- Summary: 一个小型 MuJoCo 人形 locomotion 栈，核心是 single-rigid-body convex MPC、contact-wrench optimization、heuristic swing-foot planning、touchdown handling 和机器人特定 YAML 调参。
- Notes: 仓库创建于 2026 年 5 月，规模小于主流实验室栈，但适合作为学习凸 MPC 双足行走和原地转向的可读实现。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Mac Schwager / Multi-Robot Systems Lab
- Institution: Stanford University
- Homepage: https://msl.stanford.edu/
- Google Scholar: https://scholar.google.com/citations?user=-EqbTXoAAAAJ&hl=en
- Lab / Department: Multi-Robot Systems Lab
- Key Topics: 人形机器人 / 移动操作 / 机器人学习 / 合成数据 / 多机器人系统 / autonomy
- Notes: LEGS 作者列表包含 Mac Schwager；MSL 页面描述其研究覆盖数据、机器人学习、机械臂、人形机器人和自主系统。这个组适合作为人形移动操作数据与 VLA 迁移方向的跟踪源。

### Marco Pavone / Autonomous Systems Lab
- Institution: Stanford University
- Homepage: https://web.stanford.edu/~pavone/
- Lab / Department: Autonomous Systems Laboratory
- Key Topics: 人形机器人 / 安全约束 / 全身跟踪 / 机器人学习 / autonomy
- Notes: ConstrainedMimic 列出 Marco Pavone 为共同作者。Daniel Morton 主页说明他是 Stanford PhD candidate，并在 Marco Pavone 指导下于 Autonomous Systems Lab 工作，因此 ASL 是安全感知人形跟踪和部署约束方向的相关观察源。

### DAVIAN Robotics / KAIST AI
- Institution: KAIST AI
- Homepage: https://davian-robotics.github.io/PHUMA/
- GitHub: https://github.com/DAVIAN-Robotics/PHUMA
- Lab / Department: DAVIAN Robotics
- Key Topics: 人形机器人 / locomotion 数据集 / motion retargeting / physics-aware curation / 模仿学习
- Notes: PHUMA 仓库标注 DAVIAN Robotics, KAIST AI，并提供 physically grounded humanoid locomotion data 的代码和数据入口；适合跟踪人形运动数据集与重定向基础设施。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: 人形机器人 / 人类 locomotion 神经力学 / 仿生 locomotion 控制 / 强化学习
- Status: active
- Notes: 官方 openings 页面仍列出 1 个 Postdoc 和 1 个 PhD 位置，主题是用人形机器人研究并利用人类 locomotion 神经力学，结合数值神经力学仿真、仿生控制器和强化学习。

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: 腿足机器人 / 移动操作 / 野外机器人 / motion planning / MPC / 强化学习 / 感知 / 导航 / actuation / teleoperation / ROS / C++
- Status: active
- Notes: RSL 官方页面继续列出 PhD、PostDoc、research staff/software engineer、robot designer 和 embedded-systems engineer 等滚动机会，方向覆盖腿足机器人、移动操作、野外机器人、控制、学习、规划和部署。

</details>
