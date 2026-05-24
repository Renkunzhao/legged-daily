[English](../../drafts/legged-daily-2026-05-24.md) | **中文**
# Legged Daily - 2026-05-24

## 摘要
- 今天最强论文信号是 PRIME：RSS 2026 工作，面向腿足和人形机器人的物理一致惯性与运动估计，在四足机器人和 Unitree G1 上验证。
- MUJICA 给轮足机器人提供统一的本体感知多技能控制器，把全向移动、高台攀爬、摔倒恢复合在一个策略中，并在 Unitree Go2-W 上做了真实实验。
- X2-N 是一个硬件与控制结合的信号：可在人形和轮足形态之间切换，用 RL 全身控制覆盖变形、混合移动和操作。
- DreamWaQ++ 是 T-RO 2026 四足运动项目，使用多模态 RL，展示了楼梯、坡面、障碍、负载和多平台鲁棒性。
- 仓库信号实用但整体低于论文信号：`g1_locomotion` 提供 Unitree G1 的 MPC/WBID 仿真栈；`awesome-unitree-humanoid-papers` 更适合作为 Unitree 人形方向的来源 watchlist，而不是研究代码库。
- 招聘信号来自官方页面：ETH RSL 有滚动 PhD/PostDoc/Research Engineer 等岗位；NC State HIER Lab 预计有 2027 PhD/PostDoc 机会，方向是人形机器人全身控制。

## 新论文
- [PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots](https://arxiv.org/abs/2605.17681)
  Source: arXiv / RSS 2026
  Importance: high
  Summary: PRIME 把运动估计建模为 MAP 优化，把运动学测量和执行器命令修正为动力学一致轨迹，同时估计接触力和惯性参数；它在四足机器人和 Unitree G1 上验证，重要性在于可生成带力/接触标注的真实机器人运动重建数据，服务反馈控制和后续机器人学习数据集。

- [MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots](https://arxiv.org/abs/2605.13058)
  Source: arXiv
  Importance: medium
  Summary: MUJICA 用技能指示变量训练一个全本体感知策略，统一全向移动、高台攀爬和摔倒恢复，并加入高层技能选择器；Unitree Go2-W 真实实验使它对轮足机器人鲁棒 sim-to-real 控制很有参考价值。

- [X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation](https://arxiv.org/abs/2604.21541)
  Source: arXiv
  Importance: medium
  Summary: X2-N 提出一种高自由度可变形机器人，可在人形和轮足形态之间切换，并用 RL 全身控制覆盖混合运动、变形、爬楼梯、滑行动作、包裹递送和操作任务。

## 新仓库
- [g1_locomotion](https://github.com/ioloizou/g1_locomotion)
  Topic: humanoid / Unitree G1 / MPC / whole-body inverse dynamics / MuJoCo / ROS
  Importance: medium
  Summary: 一个 Unitree G1 运动控制栈，把 Single Rigid Body Dynamics 和 Whole-Body Inverse Dynamics 组合成级联线性控制流程；README 显示支持 MuJoCo 直线行走实验，但也明确说明尚未在真实机器人上测试。

- [awesome-unitree-humanoid-papers](https://github.com/eai2-repos/awesome-unitree-humanoid-papers)
  Topic: curated list / Unitree humanoids / G1 / H1 / locomotion / manipulation / foundation models
  Importance: low
  Summary: 一个整理 2025-2026 年 Unitree G1/H1/H1-2 人形机器人论文和项目的列表；适合作为来源发现 watchlist，但它本身不是研究实现仓库。

## 实验室 / 教授信号
- Name / Lab: Jiarong Kang, Kunzhao Ren, Tao Pang, Xiaobin Xiong / PRIME author network
  Source: arXiv / RSS 2026
  Update: PRIME 是腿足/人形机器人接触动力学与运动估计方向的高信号工作；建议继续跟踪作者后续是否发布代码、数据或面向 robot foundation models 的物理一致重建数据。

- Name / Lab: DreamWaQ++ team / KAIST + KRAFTON + URobotics + MIT
  Source: project page / IEEE Transactions on Robotics 2026
  Update: DreamWaQ++ 报告了面向四足机器人的鲁棒多模态 RL：挑战楼梯成功率 97.8%、可爬 35° 坡、验证 4 个机器人平台，并以 50 Hz 实时控制运行。

- Name / Lab: HIER Lab / NC State University
  Source: official lab homepage
  Update: HIER Lab 当前方向包括人形和动物型腿足机器人、自主 loco-manipulation、全身控制、遥操作、安全关键控制和生成式 AI for motion；页面还显示 2026 年学生论文提交和 NVIDIA Academic Award 对人形研究的支持。

## 招聘信号
- Institution / Company / Lab / Team: ETH Zurich Robotic Systems Lab
  Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
  Source: official RSL open positions page
  Deadline: rolling / unknown
  Summary: RSL 官方页面列出滚动岗位，方向覆盖腿足机器人、移动操作、大型野外机器人、运动规划、MPC、强化学习、感知、导航、驱动设计、遥操作，以及 ROS/C++ 系统工程。

- Institution / Company / Lab / Team: HIER Lab / NC State University
  Type: PhD / Postdoc
  Source: official lab homepage
  Deadline: 2027 cycle / official admissions required
  Summary: HIER Lab 预计招收 2027 PhD 和 Postdoc，方向包括 hierarchical RL-based whole-body control 与 humanoid tele whole-body control；需要填写 interest form，并仍需走官方研究生申请系统。
