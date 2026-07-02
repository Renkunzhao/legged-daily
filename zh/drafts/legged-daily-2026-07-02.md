[English](../../drafts/legged-daily-2026-07-02.md) | **中文**
# 腿足机器人日报 - 2026-07-02

## 摘要
- 今天最高信号的新 arXiv 条目是 7 月 1 日的四足运动论文：用 Signal Temporal Logic（STL）规格生成更可解释的步态奖励，并接入 PPO。
- 6 月 30 日两篇人形运动论文值得跟踪：ETH 相关作者的人形被动轮滑控制，以及面向可扩展人形运动的 FastDSAC 离策略强化学习。
- FastDSAC 已有公开实现，支持 HumanoidBench 和 MuJoCo Playground，是今天最强的仓库信号。
- 仓库扫描还发现一个面向电机故障四足运动的 Isaac Lab 环境，以及一个 manager-based Isaac Gym 腿足训练框架。
- 招聘检查：ETH RSL 滚动机会仍 active；EPFL BioRob PhD 信号仍相关，但同一官方页面注明对应 Postdoc 已关闭。

<details>
<summary><strong>新论文</strong></summary>

### Learning Gait-Aware Quadruped Locomotion with Temporal Logic Specifications
- 链接: https://arxiv.org/abs/2607.00442
- 来源: arXiv
- 日期: 2026-07-01
- 作者: Merve Atasever, Cagan Bakirci, Alfredo Reina Corona, Keyan Azbijari, Jyotirmoy V. Deshmukh
- 主题: 四足运动、强化学习、Signal Temporal Logic、步态规格、PPO、可解释奖励
- 摘要: 用参数化 Signal Temporal Logic 约束描述不同四足步态区间，并把平滑 STL robustness 转成 PPO 可用的稠密 reward shaping，从而学习 gait-aware locomotion。
- 备注: 适合作为 specification-driven RL 参考：它显式编码安全边界、步态同步、命令跟踪和驱动约束，而不是只依赖手工 Markovian reward。

### Reinforcement Learning-Based Control for an Inline Skating Humanoid Robot
- 链接: https://arxiv.org/abs/2606.31807
- 来源: arXiv
- 日期: 2026-06-30
- 作者: Ethan Marot, Thomas Bi, Clemens Schwarke, Victor Klemm, Marco Hutter, Raffaello D'Andrea
- 主题: 人形运动、强化学习、被动直排轮、欠驱动运动、动态平衡
- 摘要: 为一台把传统足端改成被动直排轮的人形机器人训练并部署 RL policy，在不使用人类运动数据、模仿学习或运动学先验的情况下学出 edge-driven skating 策略。
- 备注: arXiv 列表注明 Accepted at IROS 2026。它连接 Marco Hutter / Raffaello D'Andrea 作者网络，是动态人形运动方向的强实验信号。

### FastDSAC: Enhancing Policy Plasticity via Constrained Exploration for Scalable Humanoid Locomotion
- 链接: https://arxiv.org/abs/2606.31691
- 来源: arXiv
- 日期: 2026-06-30
- 作者: Guanchen Lu, Yajuan Dun, Yi Zhou, Letian Tao, Jingliang Duan, Jie Li, Guofa Li
- 主题: 人形运动、离策略强化学习、distributional actor-critic、受约束探索、MuJoCo Playground、HumanoidBench
- 摘要: 提出 FastDSAC：在高吞吐并行采样下，用截断 Gaussian target action 约束探索，降低异常动作对 value estimation 的影响，并保持 policy plasticity。
- 备注: 公开仓库显示支持 HumanoidBench 与 MuJoCo Playground，包括 G1/T1 joystick 任务。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### luge66/FastDSAC
- 链接: https://github.com/luge66/FastDSAC
- 类别: RL / 人形运动 / 算法实现
- 机器人类型: humanoid
- 仿真器: MuJoCo Playground / HumanoidBench
- 部署: sim
- 摘要: FastDSAC 与 DSAC 的公开实现，面向可扩展人形运动，包含 distributional twin critics、GPU replay buffer、mixed precision、可选 torch.compile、checkpoint、评估、日志和 rollout rendering。
- 备注: README 列出 HumanoidBench 的 H1 hand run/walk/stand/pole/slide/hurdle，以及 MuJoCo Playground 的 G1/T1 joystick terrain 任务；这是今天 arXiv 条目中最直接的代码信号。

### iit-DLSLab/fault-locomotion-isaaclab
- 链接: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- 类别: RL / fault-tolerant locomotion / Isaac Lab environment
- 机器人类型: quadruped
- 仿真器: Isaac Lab
- 部署: sim-to-sim / sim-to-real / hardware deployment notes
- 摘要: 面向电机故障下四足运动的 Isaac Lab DirectEnv，支持多个四足机器人，并通过相关 state-estimation 与 Unitree ROS2 通信工具给出部署路径说明。
- 备注: README 写明完整代码 will be released soon；目前更适合作为 watchlist 项，而不是已完整可用的工具包。

### x714543179/legged-manager
- 链接: https://github.com/x714543179/legged-manager
- 类别: RL / Isaac Gym / manager-based training framework
- 机器人类型: legged / wheel-legged；当前任务表包含 Go2W
- 仿真器: Isaac Gym
- 部署: sim
- 摘要: 把 legged_gym + rsl_rl 训练栈改造成 IsaacLab 风格的 manager 架构，拆分 action、command、observation、reward、termination、event、terrain curriculum 和任务复用逻辑。
- 备注: 对 Isaac Gym 研究迭代和 ablation 管理有用，尤其适合 reward / observation / randomization 逻辑在经典 legged_gym 环境中高度耦合的场景。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### ETH Zurich dynamic humanoid / legged locomotion author network
- 机构: ETH Zurich 相关作者网络
- arXiv: https://arxiv.org/abs/2606.31807
- 关键主题: 人形运动、强化学习、被动轮滑、动态平衡、腿足机器人控制
- 备注: 人形轮滑论文连接 Marco Hutter 与 Raffaello D'Andrea 作者网络，是标准 walking / running benchmark 之外的高动态人形运动信号，值得继续跟踪。

### ETH Zurich Robotic Systems Lab
- 机构: ETH Zurich
- 主页: https://rsl.ethz.ch/
- 关键主题: 腿足机器人、移动操作、MPC、强化学习、感知、规划、驱动、遥操作
- 备注: RSL 官方 openings 页面仍列出滚动 PhD、Postdoc、Research Staff / Software Engineer、Robot Design、Embedded Systems、Electronic Engineer 等机会；仍是研究与机会追踪的优先来源。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab
- 类型: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- 地点: Zurich, Switzerland
- 来源: 官方实验室页面
- 截止时间: rolling / unknown
- 主题: 腿足机器人、移动操作、MPC、强化学习、感知、规划、驱动、遥操作
- 状态: active
- 备注: 官方页面继续列出多个滚动机会。PhD 和 Postdoc 方向明确包括 motion planning and MPC、reinforcement learning for robot control、perception / navigation planning、actuation / system design、teleoperation / telemanipulation，并要求 legged robots / mobile manipulation 等相关经验。

### EPFL BioRobotics Laboratory — Auke Ijspeert group
- 类型: PhD
- 地点: Lausanne, Switzerland
- 来源: 官方实验室页面
- 截止时间: EPFL doctoral school cycle / 页面注明通常 April 15 和 December 15
- 主题: 人形机器人、人类运动神经力学、生物启发控制、强化学习、数值神经力学仿真
- 状态: active / narrowed
- 备注: 官方页面仍列出 Fall 2026 项目，并说明 PhD 路径需先通过 EPFL doctoral school；同一页面现注明相关 Postdoc position is now closed，因此除非官方后续重新开放，主列表里应只保留 PhD 信号为 active。

### Proposed Removal / Stale Item
- 当前状态: stale / no longer actionable as listed
- 原因: EPFL BioRob 官方 openings 页面注明 humanoid neuromechanics 项目的 postdoc position is now closed。
- 已检查来源: https://www.epfl.ch/labs/biorob/openings/

</details>
