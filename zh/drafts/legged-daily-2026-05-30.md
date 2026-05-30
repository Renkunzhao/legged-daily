[English](../../drafts/legged-daily-2026-05-30.md) | **中文**
# Legged Daily - 2026-05-30

## 摘要
- 今天没有额外选入高置信度的新腿足机器人论文；当前 arXiv cs.RO recent 页面中直接命中腿足运动的主要条目仍是 2026-05-29 已草拟的 SPRINT，因此论文部分刻意留空，不凑数。
- 今天仓库信号强于论文信号：`rl_sar` 是较成熟的 simulation-to-real 部署框架，覆盖四足、轮足和人形机器人，并支持 ROS / ROS 2、Gazebo、MuJoCo、IsaacGym、IsaacSim。
- `legged_rl_lab` 是一个有用的 Isaac Lab/RSL-RL 训练栈，覆盖 Unitree Go1/Go2/G1、粗糙地形行走、G1 AMP、深度 parkour 和跨形态实验。
- `BipedRobot` 虽是个人项目，但技术细节较完整：自写 RL 算法、Isaac Lab + MuJoCo 接口一致、动作模仿、domain randomization 和真实双足硬件迭代。
- 实验室与招聘信号活跃：CUHK Legged Robot Lab 列出 Fall 2027 PhD、RA 和工程师机会，并报告一篇 RSS 2026 执行器相关论文；SII 足智实验室说明已从 UW-Madison 整体转入上海创智学院且正在大力招人。
- 值得复核加入 jobs 主列表的机会：Field AI 有明确的 Robotics Autonomy Engineer - Locomotion 岗位，面向腿足/人形机器人的 RL 控制器；RoMI Lab 列出一个 fully funded PhD，方向是腿足机器人、优化、RL 与 MPC。

<details>
<summary><strong>新论文</strong></summary>

2026-05-30 未额外选入高置信度新论文。当前 arXiv cs.RO recent 页面中直接匹配腿足运动的主要条目是 SPRINT，已在 2026-05-29 草稿中记录；本节刻意不填充低相关条目。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### rl_sar
- 链接: https://github.com/fan-ziqi/rl_sar
- 类别: RL / deployment / simulator / toolkit
- 机器人类型: quadruped / wheeled-legged / humanoid
- 仿真器: IsaacGym / IsaacSim / Gazebo / MuJoCo
- 部署: both
- 摘要: 面向机器人强化学习策略的仿真验证与实机部署框架，支持 ROS Noetic、ROS 2 Foxy/Humble、libtorch、onnxruntime、Linux，以及部分 macOS MuJoCo 仿真。
- 备注: 发现时 GitHub API 显示 1321 stars、Apache-2.0 license、2026-05-27 push；README 列出 Unitree A1/Go2/Go2W/B2/B2W/G1、傅利叶 GR1、智脑 L4W4、DeepRobotics Lite3、Agibot D1、DDTRobot Tita 等硬件支持，并包含 G1 运动与舞蹈策略。

### legged_rl_lab
- 链接: https://github.com/zhw0422/legged_rl_lab
- 类别: RL / simulator / toolkit
- 机器人类型: humanoid / quadruped / general
- 仿真器: Isaac Lab / Isaac Sim
- 部署: sim / sim2sim2real
- 摘要: 基于 Isaac Lab 的腿足 RL 训练栈，面向 Unitree Go1、Go2 和 G1，覆盖平地/粗糙地形行走、G1 人形 AMP、基于深度的 parkour，以及程序化人形和四足的跨形态实验。
- 备注: 发现时 GitHub API 显示 21 stars、2026-05-30 push；README 记录 RSL-RL 训练、多 GPU 训练、G1+Go2 cross-embodied 任务、mask / Transformer / GCN 形态编码器、AMASS/LAFAN1 G1 retargeted 运动数据和 skrl AMP 替代实现。

### BipedRobot
- 链接: https://github.com/AsterisCrack/BipedRobot
- 类别: RL / simulator / hardware / imitation learning
- 机器人类型: biped / humanoid-adjacent
- 仿真器: Isaac Lab / MuJoCo
- 部署: both
- 摘要: 自制 12 自由度双足机器人项目，提供共享观测/动作/奖励接口的 Isaac Lab 与 MuJoCo 环境，自写 PPO/SAC/DDPG/D4PG/MPO，实现动作模仿与 sim-to-real randomization。
- 备注: 发现时 GitHub API 显示 15 stars、MIT license、2026-05-29 push；更适合作为技术细节丰富的个人项目跟踪，而不是已广泛采用的实验室框架。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### CUHK Legged Robot Lab / Yunhui Liu
- 机构: The Chinese University of Hong Kong
- 主页: https://cuhkleggedrobotlab.github.io/
- 实验室 / 系: Department of Mechanical and Automation Engineering; CUHK Legged Robot Lab
- 关键主题: quadruped / legged locomotion / loco-manipulation / perception and navigation / actuator and mechanical system design
- 备注: 官方实验室页面显示正在招收 Fall 2027 PhD，并有多个 RA 和工程师开放机会；近期新闻还包括 2026 年 Hong Kong Embodied AI Lab 启动，以及 Zhang Linwei 的 “VRA: Grounding Discrete-Time Joint Acceleration in Voltage-Constrained Actuation” 被 RSS 2026 接收。

### Legged AI Lab / Xiaobin Xiong
- 机构: Shanghai Innovation Institute; formerly University of Wisconsin-Madison
- 主页: https://www.leggedai.com/
- 实验室 / 系: Legged AI Lab
- 关键主题: legged robots / physical AI / locomotion / manipulation / control theory / numerical optimization / machine learning / robot design
- 备注: 官方页面说明实验室 2023 年成立于 UW-Madison，并于 2026 年整体转入上海创智学院；目前经费充足，正在大力招收有博士意向的学生、科研助理和机器人系统工程师。

### RoMI Lab / Carlos Mastalli
- 机构: University of Edinburgh / Edinburgh Centre for Robotics
- 主页: https://www.romilab.org/joining
- 实验室 / 系: Robot Motor Intelligence Lab
- 关键主题: legged robotics / model predictive control / numerical optimization / reinforcement learning / robot control / contact physics
- 备注: joining 页面列出持续 PhD 招募，并说明目前有一个 fully funded PhD position 希望尽快招满；方向包括腿足机器人 MPC、最优控制、机器人控制中的 RL，以及对称性/contact physics。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Field AI
- 类型: Research Engineer / Robotics Autonomy Engineer - Locomotion
- 地点: Mission Viejo / Irvine area, California, USA; US/global team context
- 来源: official Lever careers page
- 截止时间: unknown
- 主题: legged robots / humanoid robots / reinforcement learning / locomotion / manipulation / Isaac Gym / Isaac Lab / MuJoCo / sim-to-real / field deployment
- 状态: active
- 备注: 官方岗位要求负责 RL-based locomotion pipelines，在四足和人形平台上部署敏捷运动行为，建设可扩展仿真基础设施，并与感知、嵌入式、系统团队协作；页面显示薪资范围为 USD 70k-300k。

### RoMI Lab / Carlos Mastalli
- 类型: PhD
- 地点: Edinburgh, United Kingdom
- 来源: official lab joining page
- 截止时间: as soon as possible / rolling
- 主题: legged robotics / MPC / numerical optimization / optimal control / reinforcement learning / robot control / state estimation / perception
- 状态: active
- 备注: 官方 joining 页面显示 RoMI 当前有一个 fully funded PhD position 希望尽快招满，也可通过 D2AIR 和 SPADS 博士路径申请；申请前应与 Carlos Mastalli 讨论项目提案，并在申请中说明希望加入 RoMI Lab。

### CUHK Legged Robot Lab
- 类型: PhD / Research Assistant / Engineer
- 地点: Hong Kong
- 来源: official lab page
- 截止时间: Fall 2027 PhD cycle / rolling for RA and engineer roles
- 主题: robust locomotion / whole-body loco-manipulation / perception and navigation / actuator and mechanical system design
- 状态: active
- 备注: 官方页面显示实验室正在积极寻找 Fall 2027 PhD 申请者，并有多个 RA 和工程师机会；该条与实验室信号重叠，确认后可考虑加入 jobs 主列表。

### Legged AI Lab / Shanghai Innovation Institute
- 类型: PhD / Research Assistant / Robotics Systems Engineer
- 地点: Shanghai, China
- 来源: official lab page
- 截止时间: rolling / SII admissions activities
- 主题: legged robots / physical AI / locomotion / manipulation / control / optimization / machine learning / robot body systems
- 状态: active
- 备注: 官方页面称实验室经费充足并正在大力招人；博士意向学生需参与上海创智学院统一招生活动，科研助理原则上需要线下科研，系统工程师方向聚焦机器人本体系统研发。

</details>
