[English](../../drafts/legged-daily-2026-05-23.md) | **中文**
# Legged Daily - 2026-05-23

## Summary
- 今日高信号集中在 humanoid navigation 与 whole-body loco-manipulation：MIF、SUGAR、WiXus 都有真实系统或部署导向结果。
- MIF 标注 RSS 2026，面向 Unitree G1 在动态办公室中的稳健导航，核心是 semantic 3DGS memory、局部记忆更新与 interaction-pose safety。
- SUGAR 从非结构化人类视频生成可部署 humanoid loco-manipulation skills，目标是减少 task-specific reward、reference-motion conditioning 与高成本遥操作依赖。
- WiXus 是 ICRA 2026 wheeled-legged robot，通过环境钢索驱动让腿从 locomotion 角色切换到 manipulation / tool-use 角色。
- 仓库侧本轮以“新发现 / 活跃更新”的基础设施为主：BotBrain、EgoHumanoid、SIMPLE 分别对应 ROS2 web robot brain、egocentric-demo humanoid loco-manipulation、humanoid loco-manipulation 仿真评测。
- 招聘信号已从 EPFL BioRob 官方 openings 页面复核：Fall 2026 有 humanoid robots + human locomotion neuromechanics 方向 PhD/Postdoc opening。

## New Papers
- [Learning to Evolve: Multi-modal Interactive Fields for Robust Humanoid Navigation in Dynamic Environments](https://arxiv.org/abs/2605.21935)
  Source: arXiv / RSS 2026 / project page
  Importance: high
  Summary: MIF 把 confidence-aware semantic 3D Gaussian Splatting、discrepancy-triggered spatial memory updates 和 task-driven geometry reconstruction 合成面向 Unitree G1 的 manipulation-oriented navigation pipeline；项目页报告动态办公室中 relocation success 从 12% 提升到 94%，semantic memory 减少 91.4%。

- [SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework](https://arxiv.org/abs/2605.20373)
  Source: arXiv / project page
  Importance: high
  Summary: SUGAR 从非结构化人类视频抽取 interaction priors，经物理 refiner 转成可行技能，再蒸馏为 hierarchical policy；论文报告真实 humanoid hardware zero-shot transfer、closed-loop execution 与 autonomous failure recovery。

- [WiXus: A Wheeled-Legged Robot with Wire-Driven Environmental Utilizing to Integrate Mobility and Manipulation](https://arxiv.org/abs/2605.20932)
  Source: arXiv / ICRA 2026 / project page
  Importance: medium
  Summary: WiXus 将 wheeled-legged locomotion 与环境钢索锚定结合，支持平面移动、cliff climbing，以及悬吊后把腿复用为 manipulators / tools；这是 mobility-manipulation integrated hardware design 的有趣信号。

## New Repos
- [BotBrain](https://github.com/botbotrobotics/BotBrain)
  Topic: ROS2 / web UI / teleoperation / navigation / legged robots
  Importance: medium
  Summary: 面向 quadruped、biped、humanoid 与 wheeled ROS2 robots 的模块化开源 robot brain，提供 Web UI、teleoperation、autonomous navigation、mapping、monitoring 与 3D-printable hardware；README 明确针对 Jetson / RealSense 和 Unitree Go2/G1 类平台。

- [EgoHumanoid](https://github.com/OpenDriveLab/EgoHumanoid)
  Topic: humanoid / loco-manipulation / egocentric demos / VLA
  Importance: medium
  Summary: RSS 2026 框架，用 egocentric human demonstrations 加少量 robot data 训练 humanoid whole-body loco-manipulation；包含 view alignment、action alignment，并部署 VLA policy 到 Unitree G1。

- [SIMPLE](https://github.com/physical-superintelligence-lab/SIMPLE)
  Topic: simulator / benchmark / humanoid loco-manipulation / IsaacSim / MuJoCo
  Importance: medium
  Summary: Simulation-based policy learning and evaluation 环境，支持 Unitree G1、1000+ Objaverse assets、50+ Habitat HSSD scenes 与 50+ humanoid whole-body loco-manipulation tasks；适合作为全栈 humanoid manipulation evaluation watchlist。

## Lab / Professor Signals
- Name / Lab: Peifeng Jiang et al. / Peking University Shenzhen Graduate School + Oxford Robotics Institute + ETH Zurich
  Source: MIF arXiv / project page
  Update: MIF 将 humanoid navigation、semantic 3DGS memory、dynamic-scene updates 与 Unitree G1 real-world trials 串起来，是 perception-aware humanoid navigation 的高优先级 source-network 线索。

- Name / Lab: CFCS, School of Computer Science, Peking University + Beihang University
  Source: SUGAR arXiv / project page
  Update: SUGAR 显示该作者网络在 human-video-driven humanoid loco-manipulation 上有活跃产出，后续应追踪项目页、代码/数据释放和 follow-up systems。

- Name / Lab: JSK Robotics Laboratory, The University of Tokyo
  Source: WiXus project page / arXiv
  Update: WiXus 是 JSK 网络的 ICRA 2026 hardware-system 信号，用环境钢索驱动扩展 wheeled-legged robot 的移动、操作和工具使用能力。

## Job Signals
- Institution / Company / Lab / Team: EPFL Biorobotics Laboratory / Auke Ijspeert
  Type: PhD / Postdoc
  Source: official BioRob open positions page
  Deadline: Fall 2026 opening；EPFL doctoral program deadlines 通常为 April 15 和 December 15
  Summary: 官方页面列出 1 个 Postdoc 和 1 个 PhD opening，方向是用 humanoid robots 研究并利用 human locomotion neuromechanics，结合 numerical neuromechanical simulations、bio-inspired humanoid locomotion controllers 与 reinforcement learning。
