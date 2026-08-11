[English](../../drafts/legged-daily-2026-08-11.md) | **中文**
# Legged Daily - 2026-08-11

## 摘要
- LUCID 是今日最强论文信号：它以学习得到的宏观动力学模型和想象中的技能转移规划，替代脚本化的人形机器人技能交接；但目前仅有仿真评估，今日未核验到公开代码。
- `madderscientist/g1_rl_mjlab` 是一个内容较完整的新 Unitree G1 强化学习代码库，覆盖下肢运动、站立、全身动作跟踪、课程状态持久化、镜像增强、ONNX 导出和 CPU 部署链路检查；但没有明确许可证或实机结果。
- `Baoshang-Zhou/Go1-MPC-WBC` 提供面向 Unitree Go1 的紧凑型仿真优先 SRB-MPC + QP-WBC 行走控制器，但仓库当前只有一个 Python 实现文件和简短演示，没有许可证或硬件验证。
- 今日没有新的高置信度实验室/教授来源入选。LUCID 作者网络连接了人形技能学习与长时程移动操作，但未核验到足够完整、可用于新增 master list 条目的官方实验室来源。
- Amazon Robotics Compass 官方 Safe Locomotion 职位今日复核仍有效；它是持续等待确认的提议，不是今日新发现职位。

<details>
<summary><strong>新论文</strong></summary>

### LUCID: Latent-Skill Unified Control via Imagined Dynamics for Long-Horizon Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2608.07746
- Source: arXiv
- Date: 2026-08-07
- Authors: Cheng Guo, Mingzhe Ni, Angelo Cangelosi, Arash Ajoudani
- Topics: humanoid / loco-manipulation / hierarchical reinforcement learning / world models / latent skills
- Summary: LUCID 固定一个潜变量条件全身技能策略，再联合学习高层控制器与宏观动力学世界模型，使长时程人形机器人整理任务可通过想象中的技能级转移优化，而不依赖脚本化交接。
- Notes: 该论文出现在 2026-08-11 arXiv robotics 更新中。论文在多个仿真多物体整理场景中报告了高于对比基线的完整任务成功率和部分完成率。目前证据仅来自仿真，今日未核验到官方公开代码或项目仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### madderscientist/g1_rl_mjlab
- Link: https://github.com/madderscientist/g1_rl_mjlab
- Category: RL / control / motion tracking / deployment toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: sim / deployment-path check
- Summary: 面向 Unitree G1 与双 Gloria-M 夹爪的强化学习包，覆盖下肢速度控制、最小站立和 29 自由度动作跟踪，并提供课程状态持久化、镜像增强、评估、ONNX 导出及 CPU 闭环部署检查。
- Notes: 创建于 2026-08-11，并迁移到 mjlab 1.5.3。仓库包含 104 个已跟踪文件及详细任务/奖励实现；动作数据需另行下载。它记录了 ONNX 部署契约，但没有经核验的实体机器人结果、明确许可证或社区验证；核验时为 0 star。

### Baoshang-Zhou/Go1-MPC-WBC
- Link: https://github.com/Baoshang-Zhou/Go1-MPC-WBC
- Category: MPC / whole-body control
- Robot Type: quadruped
- Simulator: custom Python simulation / unspecified backend
- Deploy: sim
- Summary: 面向 Unitree Go1 的紧凑型行走控制器原型，以单刚体模型预测控制规划接触力，再由 QP 全身控制实现较低层运动。
- Notes: 创建于 2026-08-11。仓库目前只有简短 README、一个 `mpc_wbc_walk.py` 实现文件和演示视频，因此更适合作为早期原型，而不是可复用框架。未核验到明确许可证、安装文档、基准、硬件部署或社区验证；核验时为 0 star。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今日没有新的高置信度实验室或教授来源入选。LUCID 提供了围绕人形潜变量技能控制、世界模型和长时程移动操作的有用作者与合作信号，但未核验到足够完整的官方实验室主页或新来源渠道，暂不建议插入 master list。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: 2026-08-11 核验时仍有效；曾于 2026-07-27 提议，仍等待确认加入 master list
- Notes: 该职位负责四足和人形实体平台上的行走、奔跑、爬楼梯与跌倒恢复强化学习控制器，并整合形式化安全机制、sim-to-real 流程及基于模型的全身控制。官方页面仍可访问，列出的 Pasadena 基础年薪范围为 167,100-226,100 美元。

</details>
