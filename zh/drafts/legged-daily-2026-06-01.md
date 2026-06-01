[English](../../drafts/legged-daily-2026-06-01.md) | **中文**
# Legged Daily - 2026-06-01

## 摘要
- 今天的新信号主要集中在腿足移动操作、面向机器人学习的 GPU 原生动力学，以及人形机器人的人机交互式操作。
- TA-WBC 与腿足方向高度相关：它把地形外感知、全身控制、强化学习和真实实验放在同一个 legged manipulator 框架里。
- BARD 同时适合作为论文和仓库跟踪：它面向 GPU 机器人学习流水线中的批量可微刚体动力学，并报告了在 Isaac Lab AMP 四足训练中的集成。
- Hugging Face / Pollen 发布 LeRobot Humanoid：一个低成本开源双足平台，覆盖硬件、runtime、辨识和 MJLab 训练组件；当前仍是实验平台，但对开放人形学习生态很有信号价值。
- EPFL BioRob 的人形机器人神经力学 PhD/Postdoc 机会仍在官方页面显示为活跃；今天未发现需要拟删除的过期招聘条目。

<details>
<summary><strong>新论文</strong></summary>

### Learning Terrain-Aware Whole-Body Control for Perceptive Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2605.31343
- Source: arXiv
- Date: 2026-05-29
- Authors: Sikai Guo, Yudong Zhong, Guoyang Zhao, Botao Dang, Zhihai Bi, Jun Ma
- Topics: 腿足移动操作 / 全身控制 / 地形感知 / 强化学习 / sim-to-real
- Summary: 提出 TA-WBC，一个面向腿足移动操作机器人的地形感知全身控制框架；它结合混合外感知编码、基于足端接触平面的末端采样，以及双策略蒸馏，在仿真和真实实验中提升复杂地形下的移动操作稳定性和可达性。
- Notes: 与腿足方向强相关，重点在地形拓扑感知、姿态/落足自适应和 legged loco-manipulation 的统一控制。

### Batched Differentiable Rigid Body Dynamics in PyTorch for GPU-Accelerated Robot Learning
- Link: https://arxiv.org/abs/2605.31481
- Source: arXiv
- Date: 2026-05-29
- Authors: Yue Wang, Yanran Xu, Wenbo Wu, Chuanhang Qiu, Zhaoxing Li
- Topics: 机器人动力学 / 可微仿真 / PyTorch / GPU 加速 / 强化学习 / 四足机器人
- Summary: 提出 BARD，一个 PyTorch 原生的批量可微刚体动力学库，支持 GPU 与 autograd；论文报告其数值上匹配 Pinocchio，并在 FK/Jacobian 吞吐上有大幅提升，还集成到 Isaac Lab AMP 的 11 自由度带脊柱四足训练流水线中。
- Notes: 仓库：https://github.com/YueWang996/bard-pytorch-dynamics。

### Gaze2Act: Gaze-Conditioned Vision-Language-Action Policies for Interactive Robot Manipulation
- Link: https://arxiv.org/abs/2605.30282
- Source: arXiv
- Date: 2026-05-28
- Authors: Kuangji Zuo, Gen Li, Bofan Lyu, Yanshuo Lu, Boyu Ma, Shijia Han, Xinyu Zhou, Xichen Yuan, Chuhao Zhou, Jiaqi Bai, Geng Li, Jianfei Yang
- Topics: 人形机器人 / VLA / 人机交互 / gaze conditioning / 操作 / Unitree G1
- Summary: 用人类视线作为连续意图信号来增强 VLA 操作策略，将第一视角 gaze 映射到机器人视角，并在 Unitree G1 人形机器人上完成 7 类、16 个真实任务评测。
- Notes: 不是纯 locomotion，但对人形机器人交互与操作栈有价值；项目/GitHub 页面：https://github.com/zuo-kuangji/Gaze2Act。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### BARD PyTorch Dynamics
- Link: https://github.com/YueWang996/bard-pytorch-dynamics
- Category: dynamics / toolkit
- Robot Type: general / quadruped
- Simulator: 论文报告 Isaac Lab 集成
- Deploy: sim
- Summary: PyTorch 原生刚体动力学库，支持 URDF 机器人、CPU/GPU 批量计算、autograd、floating base、FK、Jacobian、RNEA、ABA 和 CRBA。
- Notes: README 强调可直接嵌入 ML/机器人学习流水线并与 Pinocchio benchmark；论文报告其用于 11 自由度带脊柱四足的 AMP 训练。

### LeRobot Humanoid
- Link: https://github.com/Virgileboat/lerobot-humanoid
- Category: hardware / simulator / toolkit
- Robot Type: humanoid / biped
- Simulator: 通过相关 training zoo 使用 MJLab
- Deploy: both
- Summary: Hugging Face / Pollen 低成本实验性双足人形平台的主 workspace，目标是打通硬件设计、仿真、数据采集、参数辨识、训练和真实控制闭环。
- Notes: Hugging Face 官方博客称当前双足平台零件成本约 2500 美元，提供硬件文件、装配文档、runtime、辨识流水线和训练环境；当前仓库 owner 是 Virgileboat，不是 Hugging Face org，需要按实验项目看待。

### LeRobot Legged Zoo
- Link: https://github.com/Virgileboat/lerobot-legged-zoo
- Category: simulator / RL / training environments
- Robot Type: humanoid / legged
- Simulator: MJLab
- Deploy: sim
- Summary: LeRobot/Pollen 腿足机器人模型与 MJLab 训练示例，包含 LeRobot Humanoid；仓库描述明确不提供 pretrained policies。
- Notes: 可作为 LeRobot Humanoid 发布中的训练环境侧入口；目前早期阶段，适合跟踪但不应视为成熟基准。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Hugging Face / Pollen Robotics
- Institution: Hugging Face; Pollen Robotics
- Homepage: https://huggingface.co/blog/VirgileBatto/lerobot-humanoid
- GitHub: https://github.com/Virgileboat/lerobot-humanoid
- Lab / Department: 开源机器人 / LeRobot 生态
- Key Topics: humanoid / biped / open hardware / robot learning / sim-to-real / MJLab
- Notes: 官方博客发布 LeRobot Humanoid：一个低成本、全栈、开源的双足平台，覆盖硬件、runtime、辨识和训练组件。适合持续跟踪开放人形机器人学习基础设施，但平台目前明确是 experimental。

### MARS Lab — Nanyang Technological University
- Institution: Nanyang Technological University
- Homepage: https://arxiv.org/abs/2605.30282
- GitHub: https://github.com/zuo-kuangji/Gaze2Act
- Lab / Department: MARS Lab
- Key Topics: humanoid / VLA / human-robot interaction / gaze-conditioned manipulation / Unitree G1
- Notes: Gaze2Act 标注 MARS Lab, NTU，并在 Unitree G1 人形机器人上评测 gaze-conditioned VLA 策略；适合作为人形交互和操作方向的 watch source。

### EPFL BioRob / Auke Ijspeert
- Institution: EPFL
- Homepage: https://www.epfl.ch/labs/biorob/openings/
- Lab / Department: Biorobotics Laboratory
- Key Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Notes: 官方 openings 页面仍列出围绕人形机器人与人类步态神经力学的 Postdoc 和 PhD 机会。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: 官方页面显示 1 个 Postdoc 和 1 个 PhD 机会，项目结合数值神经力学仿真、生物启发人形步态控制器和强化学习；申请从现在开始持续考虑直到招满。

</details>
