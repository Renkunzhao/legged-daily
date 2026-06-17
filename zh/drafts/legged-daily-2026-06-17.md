[English](../../drafts/legged-daily-2026-06-17.md) | **中文**
# 腿足机器人日报 - 2026-06-17

## 摘要
- arXiv 近期列表中，6 月 15-16 日出现多篇人形学习 / 控制论文；今天最值得保留的是层级全身学习基准、扰动感知人形步态训练，以及无需显式步态先验的地形自适应四足运动。
- RSS 2026 项目页已能看到多篇高相关腿足 / 人形论文，包括视觉驱动人形运动、Human2LocoMan、PRIME、以及 MoE 四足 sim-to-real 可预测性；建议后续进入主论文队列复核。
- GitHub 信号质量参差，但有 3 个可用条目：IIT DLS 的成熟 IsaacLab 四足运动栈、SRL-Locomotion 的物理引导跳跃框架、以及一个偏复现实验的 Unitree G1 PPO 仓库。
- 实验室 / 机会信号：CUHK Legged Robot Lab 正在招 Fall 2027 PhD、RA 和工程师；EPFL BioRob 有 Fall 2026 人形神经力学 PhD/Postdoc 项目；ETH RSL 继续滚动招 PhD/Postdoc/研究工程师等岗位。

<details>
<summary><strong>新论文</strong></summary>

### HumanoidArena: Benchmarking Egocentric Hierarchical Whole-body Learning
- Link: http://arxiv.org/abs/2606.17833v1
- Source: arXiv cs.RO
- Date: 2026-06-16
- Authors: Taowen Wang, Zikang Xie, Bin Yang, Yunheng Wang, Zizhao Yuan, Yuetong Fang, Yixiao Feng, Yichi Wang, et al.
- Topics: humanoid, whole-body learning, hierarchical control, benchmark, egocentric tasks
- Summary: 提出面向第一视角层级全身人形学习的 benchmark，核心关注高层任务决策与低层动态执行之间的耦合问题。
- Notes: 作为人形策略评测、任务 / 控制层级设计相关基准，长期跟踪价值较高。

### ADAPT: Analytical Disturbance-Aware Policy Training for Humanoid Locomotion
- Link: http://arxiv.org/abs/2606.16542v1
- Source: arXiv cs.RO
- Date: 2026-06-15
- Authors: Bofan Lyu, Jindou Jia, Kuangji Zuo, Yanshuo Lu, Shijia Han, Gen Li, Boyu Ma, Jingliang Li, et al.
- Topics: humanoid, locomotion, disturbance rejection, reinforcement learning, force interaction
- Summary: 面向外部接触和意外扰动下的人形运动控制，提出 analytical disturbance-aware policy training，用于提升步态稳定性和跟踪精度。
- Notes: 对需要处理推拉、接触、力交互的人形部署场景有价值，尤其是在单纯 domain randomization 不够精细时。

### LoComposition: Terrain-Adaptive Energy-Efficient Quadruped Locomotion without Gait Priors
- Link: http://arxiv.org/abs/2606.15896v1
- Source: arXiv cs.RO
- Date: 2026-06-14
- Authors: Loukas Kordos, Leonard T. Franz, Simon Rappenecker, Oliver Hausdoerfer, Angela P. Schoellig, Pavel Kolev, Georg Martius
- Topics: quadruped, locomotion, energy efficiency, terrain adaptation, reinforcement learning
- Summary: 不把任务、约束、地形适应和步态偏好全部塞进同一个 dense reward，而是拆成不同机制，目标是在无显式步态先验下实现节能的地形自适应四足运动。
- Notes: 对 reward decomposition、能耗约束和地形适应设计都有参考价值，可作为主论文列表候选。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / simulator / deployment toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab, MuJoCo
- Deploy: both
- Summary: IIT Dynamic Legged Systems Lab 维护的 IsaacLab 四足运动扩展，覆盖 Aliengo、Go2、B2、HyQReal2，并包含 sim-to-sim 与 ROS2 sim-to-real 部署链路。
- Notes: 相比今天多数 GitHub 搜索结果更成熟；包含 rapid motor adaptation、morphological symmetries、AMP，以及机器人参数识别相关接口。

### Kr1shu01/SRL-Locomotion
- Link: https://github.com/Kr1shu01/SRL-Locomotion
- Category: RL / control
- Robot Type: quadruped / biped
- Simulator: Isaac Gym, MuJoCo, Unity
- Deploy: sim / partial hardware reference
- Summary: SRL 的官方实现；该框架将 SLIP 前馈运动生成、RL 反馈控制、自适应融合和 curriculum learning 结合，用于腿足机器人敏捷跳跃。
- Notes: README 称已在 Unitree Go2 和 X02-lite 的多种跳跃任务上验证；仓库也明确说明未包含部分平台部署基础设施和 pretrained models。

### JJJEEERRR/g1-locomotion-rl
- Link: https://github.com/JJJEEERRR/g1-locomotion-rl
- Category: RL / reproducibility
- Robot Type: humanoid
- Simulator: MuJoCo Playground / MJX / Brax
- Deploy: sim
- Summary: 面向 29-DoF Unitree G1 的可复现 PPO locomotion 项目，包含 YAML 实验配置、reward 条目说明、domain randomization、rollout 渲染，以及 150M steps 训练结果记录。
- Notes: 不是官方实验室发布，规模也较小；但工程透明度不错，适合作为 G1 训练复现参考。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### CUHK Legged Robot Lab
- Institution: The Chinese University of Hong Kong
- Homepage: https://cuhkleggedrobotlab.github.io/
- Lab / Department: Department of Mechanical and Automation Engineering; supervised by Prof. Liu Yun-Hui
- Key Topics: quadruped, locomotion, whole-body loco-manipulation, perception, navigation, safe actuator/system design
- Notes: 实验室主页写明正在招 Fall 2027 PhD，同时有多个 RA 和工程师 opening。2026 年近期新闻包括 Hong Kong Embodied AI Lab 启动，以及一篇关于 voltage-constrained actuation 的 RSS 2026 论文接收。

### RSS 2026 legged / humanoid paper pages
- Institution: Robotics: Science and Systems 2026 program
- Homepage: https://roboticsconference.org/program/papers/
- Key Topics: humanoid, quadruped, locomotion, loco-manipulation, sim-to-real, motion estimation
- Notes: RSS 2026 项目页已出现多篇相关论文，包括 “Now You See That: Learning End-to-End Humanoid Locomotion from Raw Pixels”（Paper 27）、“PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots”（Paper 29）、“Human2LocoMan”（Paper 122），以及 MoE robust quadrupedal locomotion predictability（Paper 156）。这更适合作为后续 master-list 复核来源，而不是单一实验室条目。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL BioRob
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: rolling until filled
- Topics: humanoid, human locomotion neuromechanics, bio-inspired control, reinforcement learning
- Status: active
- Notes: Fall 2026 项目，主题是使用人形机器人研究并利用人类运动神经力学；官方页面写明有 1 个 Postdoc 和 1 个 PhD 位置，持续评审至招满，理想开始时间约为 2026 年 9 月。

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Engineer / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling / unknown
- Topics: legged robots, mobile manipulation, MPC, reinforcement learning, perception, navigation, teleoperation, robotic systems
- Status: active
- Notes: 官方 openings 页面列出多个滚动岗位，其中 research staff / software engineer 明确面向 legged robots、mobile manipulators 和真实场景部署系统。

### CUHK Legged Robot Lab
- Type: PhD / RA / Engineer
- Location: Hong Kong
- Source: official lab page
- Deadline: Fall 2027 PhD cycle / RA and engineer timing unknown
- Topics: legged locomotion, loco-manipulation, perception and navigation, actuator/system design
- Status: active
- Notes: 实验室主页明确说明正在寻找 Fall 2027 PhD 申请者，并有多个 RA / engineer opening。

</details>
