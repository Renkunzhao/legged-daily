[English](../../drafts/legged-daily-2026-09-08.md) | **中文**
# Legged Daily - 2026-09-08

## 摘要
- CFAM 提出“冻结的感知—推理—动作主干 + 无梯度 Capsule Field”，用于单样本、端侧、部署后持续适应，并在包括四足和人形在内的五种本体上评估。
- IIT Dynamic Legged Systems Lab 更新了其 BSD-3-Clause 的 Isaac Lab 四足容错运动栈，整合电机故障环境、并发状态估计、快速电机适应、混合专家、对称性处理、MuJoCo 迁移与 ROS 2 部署。
- SimForge 以统一 JAX RL 接口贯通 Genesis、Newton 和 MuJoCo，已给出 30 组机器人—任务—仿真器组合，并展示 Unitree G1/Go2 与 Booster K1 实机部署。
- Rhoyn 步行基准将 29 个开源 Unitree G1 策略接入统一 C++ 接口，在 MuJoCo 和 PhysX 中完成 471,424 次抗扰恢复测试，同时暴露出显著的鲁棒性与许可证差异。
- 今日最强来源信号是面向容错运动的 IIT DLS，以及研究部署后持续学习 Physical AI 的 Skylark Labs–CMU–UC Berkeley 合作；未核验到足够新且来自官方来源的招聘机会。

<details>
<summary><strong>新论文</strong></summary>

### Continual Field-Adaptive Models (CFAMs) for Post-Deployment Physical AI
- Link: https://arxiv.org/abs/2609.04552
- Source: arXiv
- Date: 2026-09-03
- Authors: Amarjot Singh, Tanmay R. Pancholi, Jainam Kothari, Shrirang Mahajan, Ketan Bansal, Zackory Erickson, Giuseppe Loianno, Alexandre M. Bayen, Jeff Schneider, Vince Nakayama
- Topics: physical AI / continual learning / quadruped / humanoid / VLA / on-device adaptation
- Summary: 提出多本体架构，以冻结的 Sensor、Reasoning、Action 模块提供稳定能力，并通过快速 Capsule Field 对已验证的近分布外经验进行单样本、无梯度端侧写入。
- Notes: 评估覆盖机械臂、四足、人形、四旋翼和越野车。论文报告仅用 40% 预训练轨迹即可达到全数据标准策略的工作点；测试时自动捕获近 OOD 成功样本使动作成功率提升 13.9 个百分点；顺序仿真中的 backward transfer 为 -0.5 个百分点，而 LoRA 为 -11.4。作者明确说明开放世界新颖任务不在范围内，本次未核验到公开代码。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### fault-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- Category: RL
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: 提供面向电机故障四足运动的 Isaac Lab Direct 环境与部署路径，包含 Go2 和 Pegasus 的平地/崎岖地形、盲走/视觉策略、sim-to-sim 与 ROS 2 sim-to-real 配置。
- Notes: 该 BSD-3-Clause 仓库于 2026-09-08 更新。文档列出的组件包括并发状态估计、快速电机适应、混合专家策略、形态对称性、实验室的 MUSE 估计器和 Unitree ROS 2 通信；兼容性仍依赖其明确测试过的 Isaac Lab 与 rsl_rl 版本。

### SimForge
- Link: https://github.com/jsw7460/SimForge
- Category: RL
- Robot Type: general
- Simulator: Genesis / Newton / MuJoCo
- Deploy: both
- Summary: 一个基于 JAX、与仿真器解耦的 RL 框架，通过统一接口训练并跨仿真评估，覆盖 Unitree G1/Go2、Booster T1/K1 的运动与动作任务，以及 I2RT YAM 机械臂操作。
- Notes: 项目记录了 10 个任务在三个仿真器中的完整组合、PPO/SAC/TD3 与 Stable-Baselines3 的一致性检查、域随机化、动作跟踪，以及 G1、Go2、K1 的实机演示。总仓库以子模块固定各仿真栈版本；未检测到仓库级许可证，复用前应逐组件核对条款。

### teleop-walking-benchmark
- Link: https://github.com/rhoyn/teleop-walking-benchmark
- Category: toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / PhysX
- Deploy: sim / browser
- Summary: 将 29 个开源 Unitree G1 步行策略移植到统一 C++ 接口，在 MuJoCo 和 PhysX 中使用同一条 60 秒航点路线比较抗扰恢复能力。
- Notes: 当前报告汇总 471,424 次运行，随机冲击最高 600 N，并分别统计完成率、跟踪误差、能耗和振动。最佳策略仍有约五分之一测试失败，部分策略在两种物理引擎间差异明显。Rhoyn 自有测试框架采用 MIT 许可证，但随附或下载的策略保留各自条款，NOTICE 中包含非商业、未声明及仅限仿真的限制。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Dynamic Legged Systems Lab
- Institution: Istituto Italiano di Tecnologia (IIT)
- Homepage: https://www.dls.iit.it/
- GitHub: https://github.com/iit-DLSLab
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: quadruped / locomotion / fault tolerance / RL / MPC / state estimation / sim-to-real
- Notes: 2026-09-08 对 `fault-locomotion-isaaclab` 的更新延伸了该实验室已有的完整开源链条，包括 Isaac Lab 基础运动、Quadruped-PyMPC、JAX MPC、MUSE 状态估计、分布式全身 MPC 和 Unitree 部署工具。维护者 Giulio Turrisi 与实验室负责人 Claudio Semini 是容错运动、模型控制和学习控制方向值得持续跟踪的来源。
- Students and Representative Works:
  - [Giulio Turrisi](https://github.com/giulioturrisi) — [Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion](https://arxiv.org/abs/2606.25965)

### Skylark Labs 主导的 CFAM 合作网络
- Institution: Skylark Labs / Carnegie Mellon University / University of California, Berkeley
- Homepage: https://skylarklabs.ai/cfams.html
- arXiv: https://arxiv.org/abs/2609.04552
- Lab / Department: cross-institution Physical AI collaboration
- Key Topics: continual learning / physical AI / quadruped / humanoid / VLA / edge adaptation
- Notes: CFAM 将 Skylark Labs 与 CMU 的 Zackory Erickson、Jeff Schneider，以及 UC Berkeley 的 Giuseppe Loianno、Alexandre Bayen 连接起来，是跟踪“固定端侧算力下、多本体策略部署后继续适应”方向的有用来源网络；当前证据主要来自论文和项目页，尚未核验到公开实现。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次未从官方来源核验到足够新、仍有效且高置信度的腿足机器人相关机会。

</details>
