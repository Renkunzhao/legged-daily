[English](../../drafts/legged-daily-2026-07-27.md) | **中文**
# 腿足机器人日报 - 2026-07-27

## 摘要
- 今日有 1 篇此前未跟踪的论文达到收录标准：NCKU 团队使用文本提示生成的人体运动视频、三维姿态重建、动作重定向、片段拼接和 RL 跟踪，让仿真 Unitree G1 学习多样化全身任务。
- 该论文是值得关注的合成数据流水线信号，但公开验证仅包含四个仿真场景；没有展示 sim-to-real 或实体机器人部署。
- 今日有 1 个新发现的官方代码仓库达到收录标准：`mturan33/isaac-g1-ulc` 发布 Unitree G1 loco-manipulation 的 Isaac Lab 训练、评测代码和权重，并提供了少见的详细复现说明与实验局限分析。
- 该仓库对应的是六月已跟踪论文，而不是今日新论文。README 明确记录了 dual-vs-unified critic 对比中的多项混杂因素，因此不宜把结果差距完全归因于 critic 架构。
- Amazon Robotics Compass 新增一个高度相关的 Senior Applied Scientist, Safe Locomotion 岗位，覆盖 RL、形式化安全约束、全身控制、sim-to-real，以及实体四足/人形机器人部署。

<details>
<summary><strong>新论文</strong></summary>

### Learning Diverse Humanoid Tasks via Synthetic Video Scenarios without Real World Data
- 链接: https://arxiv.org/abs/2607.21648
- 来源: arXiv；已被 IEEE/ASME AIM 2026 接收
- 日期: 2026-07-22
- 作者: Yun-Hao Tsai, Cong-Thanh Vu, Yen-Chen Liu
- 主题: humanoid robot learning / synthetic video / motion retargeting / imitation learning / reinforcement learning / Unitree G1
- 摘要: 该框架从文本提示生成多样人体运动视频，重建三维人体动作，将其重定向到人形机器人，拼接独立生成的动作片段，并训练 RL 动作跟踪策略来复现任务级全身行为。
- 备注: 论文在仿真 Unitree G1 上评测四个场景，报告了任务完成和对动作变化的适应能力，但没有实体机器人或 sim-to-real 实验。核验时未发现论文链接专属公开代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### mturan33/isaac-g1-ulc
- 链接: https://github.com/mturan33/isaac-g1-ulc
- 类别: reinforcement learning / locomotion / loco-manipulation / benchmark
- 机器人类型: humanoid；Unitree G1
- 仿真器: NVIDIA Isaac Lab / Isaac Sim
- 部署: 以仿真为主；已公开预训练权重，仓库包含外部 Unitree 硬件桥接，但对应论文报告的是仿真实验
- 摘要: 六月已跟踪的 RL4IL @ ICRA 2026 论文官方代码，比较 G1 全身 loco-manipulation 的 dual 与 unified critic 架构，包含分阶段 PPO 训练、标准化评测工具、预训练权重，以及额外的 29-DoF G1 + DEX3 流水线。
- 备注: MIT 许可证，核验时有 16 个 GitHub stars，并于 2026-07-27 持续更新。README 很坦诚地指出：主要对比仅使用单次训练，且 curriculum、奖励权重和动作维度并未完全受控，因此 checkpoint 间的差距具有参考价值，但不能干净地证明 critic 架构是唯一原因。确认后建议加入 `repos.md`。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Yen-Chen Liu / NCKU 机械工程人形学习团队
- 机构: 台湾成功大学（National Cheng Kung University）
- 主页: https://arxiv.org/abs/2607.21648
- arXiv: https://arxiv.org/abs/2607.21648
- 实验室 / 院系: Department of Mechanical Engineering
- 关键主题: humanoid learning / synthetic demonstrations / motion retargeting / reinforcement learning / passive-dynamics-inspired locomotion
- 备注: Yun-Hao Tsai、Cong-Thanh Vu 与 Yen-Chen Liu 发布了面向仿真 Unitree G1 全身任务的 prompt-to-video-to-policy 流水线，论文已被 IEEE/ASME AIM 2026 接收。这是论文动态信号，不是已核验的招生或招聘公告；本轮未确认独立的官方实验室主页。
- 学生与代表作:
  - Yun-Hao Tsai、Cong-Thanh Vu — [Learning Diverse Humanoid Tasks via Synthetic Video Scenarios without Real World Data](https://arxiv.org/abs/2607.21648)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型: Senior Applied Scientist
- 地点: 美国加州 Pasadena
- 来源: https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止日期: rolling / unknown
- 主题: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- 状态: active；2026-07-27 已核验官方职位页
- 备注: 该岗位负责实体四足和人形平台上的学习式运动算法，包括行走、奔跑、爬楼梯与跌倒恢复；明确要求将 RL 策略与形式化安全机制、模型式全身控制结合，并进行硬件评测和失效模式分析。确认后建议加入或更新 `jobs.md`。

</details>
