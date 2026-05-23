# Legged Daily - 2026-05-23

## Summary
- 今日高信号集中在 humanoid navigation 与 loco-manipulation：MIF、SUGAR、CEER 都面向真实或可部署 humanoid whole-body interaction。
- MIF 已标注 RSS 2026，围绕 Unitree G1 的动态办公室导航、语义 3DGS memory update 与 interaction-pose safety，项目页和代码入口已给出。
- SUGAR 从非结构化人类视频生成 humanoid loco-manipulation skills，强调减少 task-specific reward engineering、reference-motion conditioning 与 teleoperation 依赖。
- CEER 提出 compliant end-effector-root interface，把 locomotion / manipulation / LLM skill manager 通过统一 EE-root 命令连接，是模块化 humanoid loco-manipulation 的强信号。
- GitHub 侧本轮以“新发现/活跃更新”为主：BotBrain 是新近活跃的 ROS2 legged robot web brain；Crocoddyl 与 Upkie 是仍活跃的基础工具/平台参考。
- 招聘信号复核到 EPFL BioRob 官方 open positions 页面：Fall 2026 有 humanoid robots + human locomotion neuromechanics 的 PhD/Postdoc opening。

## New Papers
- [Learning to Evolve: Multi-modal Interactive Fields for Robust Humanoid Navigation in Dynamic Environments](https://arxiv.org/abs/2605.21935)
  Source: arXiv / RSS 2026
  Importance: high
  Summary: MIF 面向 Unitree G1 动态办公室导航，把 confidence-aware semantic 3DGS、局部空间记忆更新和 interaction-pose safety 合成闭环 perception-adaptation pipeline；论文报告 relocation success 从 12% 提升到 94%，并给出 project page / code 入口。

- [SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework](https://arxiv.org/abs/2605.20373)
  Source: arXiv
  Importance: high
  Summary: SUGAR 从非结构化人类视频自动抽取 human-object trajectories 与 contact labels，经 physics-based refiner 转成可部署 humanoid loco-manipulation skills，并报告真实 humanoid zero-shot transfer、failure recovery 与长时稳定执行。

- [CEER: Compliant End-Effector and Root Control as a Unified Interface for Hierarchical Humanoid Loco-Manipulation](https://arxiv.org/abs/2605.19981)
  Source: arXiv / project page
  Importance: high
  Summary: CEER 提出统一的 compliant EE-root 控制抽象，让 high-level planner / LLM skill manager / manipulation modules 通过 root motion 与 end-effector pose targets 接入低层 whole-body policy；项目页展示 Duke University teleoperated demos，并报告 3.3 cm end-effector tracking accuracy。

## New Repos
- [BotBrain](https://github.com/botbotrobotics/BotBrain)
  Topic: ROS2 / web UI / teleoperation / navigation / legged robots
  Importance: medium
  Summary: 2026-01 创建、2026-05 活跃更新的模块化 ROS2 robot brain，面向 quadruped、biped、humanoid 与 wheeled robots，提供 Web UI、teleop、navigation、mapping、monitoring 和 3D-printable hardware；README 明确列出 Jetson / RealSense 取向，GitHub API 显示 2026-05-21 pushed、MIT license。

- [Crocoddyl](https://github.com/loco-3d/crocoddyl)
  Topic: optimal control / DDP / contact dynamics / toolkit
  Importance: medium
  Summary: 经典接触序列最优控制库，提供 DDP-like solvers、Pinocchio dynamics/derivatives、Python bindings 与多种 constraints/costs；GitHub API 显示 2026-05 仍有 push/update，适合作为 legged whole-body control / trajectory optimization 基础工具继续跟踪。

- [Upkie](https://github.com/upkie/upkie)
  Topic: wheeled biped / open hardware / simulation-to-hardware / Gymnasium
  Importance: low
  Summary: 开源 wheeled biped robot 平台，包含硬件构建材料、Python/C++ 控制、PyBullet/Gymnasium 环境以及仿真到实机切换路径；GitHub API 显示 2026-05 仍活跃，适合作为低成本 biped platform reference。

## Lab / Professor Signals
- Name / Lab: Peifeng Jiang et al. / Peking University Shenzhen Graduate School + Oxford Robotics Institute + ETH Zurich
  Source: arXiv / project page
  Update: MIF 把 humanoid navigation、semantic 3DGS memory、dynamic scene updates 与 Unitree G1 real-world demo 串起来，是 perception-aware humanoid navigation 的新 source-network 线索。

- Name / Lab: CFCS, School of Computer Science, Peking University + Beihang University
  Source: arXiv / project page
  Update: SUGAR 显示 PKU/Beihang 在 human-video-driven humanoid loco-manipulation 方向有连续产出潜力，值得后续追踪作者组、项目页和潜在代码释放。

- Name / Lab: Duke University humanoid loco-manipulation group
  Source: CEER project page / arXiv
  Update: CEER 项目页展示 compliant end-effector-root interface、LLM skill manager、teleoperated demos 与 room-scene long-horizon tasks，是 modular humanoid loco-manipulation 的值得跟踪信号。

## Job Signals
- Institution / Company / Lab / Team: EPFL Biorobotics Laboratory / Auke Ijspeert
  Type: PhD / Postdoc
  Source: official BioRob open positions page
  Deadline: Fall 2026 / EPFL doctoral program deadlines typically April 15 and December 15
  Summary: 官方页面列出 1 个 Postdoc 和 1 个 PhD opening，项目方向是用 humanoid robots 研究并利用 human locomotion neuromechanics，结合 numerical neuromechanical simulations、bio-inspired humanoid locomotion controllers 与 reinforcement learning；这是可写入 jobs.md 的高相关 active signal。
