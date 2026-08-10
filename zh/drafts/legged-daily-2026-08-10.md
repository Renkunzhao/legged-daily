[English](../../drafts/legged-daily-2026-08-10.md) | **中文**
# Legged Daily - 2026-08-10

## 摘要
- 今日有两篇新 arXiv 论文达到收录标准：一篇打通多相机感知到控制的严格时限四足接球闭环，另一篇在执行器断电故障下学习自适应步态时序，并在 IIT 的 68 kg KYON 四足机器人上完成零样本迁移验证。
- `ductnguyen-dtn/g1-humanoid-locomotion` 为 Unitree G1 提供四种 Isaac Lab 行走、抗推恢复和安全倒地任务，失败分析尤其有参考价值，但没有许可证或训练检查点。
- `ductnguyen-dtn/spotmicro-locomotion` 记录自制 SpotMicro 的 18 个强化学习检查点演进，并保存精确配置快照；仓库不含策略权重，报告的步态仍有不对称问题。
- Berkeley Humanoids 发布 ROS Jazzy Conda buildfarm，用于打包 RoboStack 缺失的软件包和维护分支，是面向其人形机器人软件栈的窄而可复现的基础设施发布。
- 今日没有新的实验室/教授来源超过现有 master list 覆盖。Amazon Robotics Compass 官方 Safe Locomotion 职位仍然有效，继续等待确认加入 master list。

<details>
<summary><strong>新论文</strong></summary>

### Spatiotemporal Agility: Time-Constrained Reinforcement Learning for Vision-Guided Dynamic Quadrupedal Interception
- Link: https://arxiv.org/abs/2608.06907
- Source: arXiv
- Date: 2026-08-10
- Authors: Yidong Zhu, Zibo Dai, Tongning Zhang, Leixin Chang, Hua Chen
- Topics: quadruped / reinforcement learning / vision-guided locomotion / dynamic interception / sim-to-real
- Summary: 一套完整的四足机器人接球系统通过多相机预测目标落点和到达时间，并将两者直接输入位置与时间条件运动策略，而不是先转换成速度指令。
- Notes: 浙江大学与逐际动力报告了完整的低延迟硬件闭环；在测试范围内，对 2 m 内落点和 0.8-1.2 s 飞行时间，其接球成功率高于速度跟踪及瞬时球状态基线。论文包含真机实验，但今日未核验到公开代码仓库。

### Learning Fault-Tolerant Locomotion with Adaptive Gait Timing
- Link: https://arxiv.org/abs/2608.07328
- Source: arXiv / IROS 2026
- Date: 2026-08-10
- Authors: Giovanbattista Gravina, Luca Rossini, Carlo Rizzardo, Arturo Laurenzi, Nikos Tsagarakis
- Topics: quadruped / fault-tolerant locomotion / reinforcement learning / adaptive gait timing / sim-to-real
- Summary: 非对称 actor-critic 策略从本体感知历史中重建特权故障信息，并将步态频率纳入动作，使单一控制器能在执行器断电后自行重组时序，而无需预定义故障腿策略。
- Notes: IIT 在高保真崎岖地形仿真中评估该方法，并在 68 kg KYON 四足机器人平地实验中完成零样本实机验证。官方项目页提供架构、仿真和硬件视频；论文注明已被 IROS 2026 接收，但未核验到公开训练代码。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### ductnguyen-dtn/g1-humanoid-locomotion
- Link: https://github.com/ductnguyen-dtn/g1-humanoid-locomotion
- Category: RL / control / simulator
- Robot Type: humanoid
- Simulator: Isaac Lab / PhysX
- Deploy: sim
- Summary: 面向 Unitree G1 的任务集合，覆盖平地速度跟踪、带抗推恢复的站立平衡和安全倒地训练，兼容 NVIDIA 官方整理资产与自行导入的 29 自由度资产。
- Notes: 创建于 2026-08-10。仓库解释了为何需要更强推力并让 episode 延续整个下降过程，才能真正激活倒地塑形奖励；还记录了近零导入惯量、随机化目标 body 名错误和接触传感器层级问题的修复。包含任务配置，但没有训练检查点、明确许可证、硬件部署或社区验证；核验时为 0 star。

### ductnguyen-dtn/spotmicro-locomotion
- Link: https://github.com/ductnguyen-dtn/spotmicro-locomotion
- Category: RL / control / hardware integration
- Robot Type: quadruped
- Simulator: Isaac Lab / PhysX
- Deploy: both
- Summary: 面向自制 12 舵机 SpotMicro 的可复现 Isaac Lab 运动任务与训练记录，追踪策略从资产底座被焊死的失败状态，经站立稳定到前进行走的 18 个入选检查点。
- Notes: 创建于 2026-08-10。仓库包含适配后的 URDF、任务与奖励补丁、精确配置快照和按顺序记录的 35 条实验笔记；硬件固件和 ROS 来自上游 `mike4192/spotMicro` 项目。未提供策略权重，当前步态仍存在后腿不对称，没有明确仓库许可证，核验时为 0 star。

### Berkeley-Humanoids/Berkeley-Humanoids-Buildfarm
- Link: https://github.com/Berkeley-Humanoids/Berkeley-Humanoids-Buildfarm
- Category: toolkit / infrastructure
- Robot Type: humanoid / general
- Simulator: none
- Deploy: both
- Summary: Berkeley Humanoids 的 Conda buildfarm 将 RoboStack 缺失的 ROS Jazzy 依赖打包并发布到 `berkeley-humanoids` prefix.dev channel，供下游人形机器人仓库直接使用二进制包。
- Notes: 创建于 2026-08-09，更新于 2026-08-10。pixi/rattler 工作流固定源码与工具链版本，支持 linux-64 和 linux-aarch64，并通过临时本地 channel 处理 EtherCAT、MuJoCo ROS 2 等依赖链。它属于基础设施而非运动控制器；没有明确许可证，核验时为 0 star。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今日没有新的高置信度实验室或教授来源入选。KYON 容错运动论文是 IIT Humanoids and Human-Centered Mechatronics Research Line 的一项值得跟踪的新成果，但 IIT 腿足机器人团队与 Nikos Tsagarakis 已在来源网络中，因此将其视为研究更新，而不是新的 master-list 候选。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: 2026-08-10 核验时仍有效；曾于 2026-07-27 提议，仍等待确认加入 master list
- Notes: 该职位负责四足和人形实体平台上的行走、奔跑、爬楼梯与跌倒恢复强化学习控制器，并结合形式化安全机制、sim-to-real 流程及基于模型的全身控制。官方页面仍可访问，列出的 Pasadena 基础年薪范围为 167,100-226,100 美元。

</details>
