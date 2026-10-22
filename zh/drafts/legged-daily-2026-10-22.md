[English](../../drafts/legged-daily-2026-10-22.md) | **中文**
# Legged Daily - 2026-10-22

## 摘要
- SuperMimic 用一个可微世界模型训练人形动作跟踪器;据称 3 个 GPU 小时即超过 128 卡训练 7 天的基线,并迁移到 Unitree G1 真机。
- "Watch Your Step" 预测未来落脚点,仅在落脚点附近采样高程图,达到同等地形难度所需训练迭代约为原来的三分之一,并零样本迁移到 Unitree G1。
- ETH RSL 团队训练了面向月球重力的端到端四足跳跃策略,在重力卸载条件下完成真机垂直跳跃。
- HoloMotion v2.0(2026-10-12)提供单一的稀疏到全身 G1 控制策略并公开权重;RoboParty 的 RP1 开源人形平台于 2026-10-15 发布,包含硬件、固件与训练仓库。
- 今日未核实到新的实验室/教授信号或招聘;上述三篇论文均未找到代码链接。

<details>
<summary><strong>新论文</strong></summary>

### SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model
- Link: https://arxiv.org/abs/2610.28480
- Source: arXiv
- Date: 2026-10-20
- Authors: Qiayuan Liao, Yiyang Shao, Junfeng Long, Kevin Zakka, Roberto Horowitz, Pieter Abbeel, Koushil Sreenath
- Topics: 人形全身控制 / 动作跟踪 / 可微世界模型 / 规模化 / 仿真到真机
- Summary: 从刚体仿真器的转移日志拟合一个描述共享动力学的可微世界模型,并与跟踪策略联合训练,通过短程想象 rollout 的反向传播获得解析策略梯度。
- Notes: 摘要称单 GPU 3 小时即超过在 128 GPU 上训练 7 天的 SOTA 跟踪器,GPU 小时减少超过 1000 倍;在 129,514 条基准动作中仅失败 25 条(基线 179 条),双 GPU 训练 9.8 小时后零失败。在 Unitree G1 真机上完成多种高难度动作迁移。未找到代码链接;结果未经独立复现。

### Watch Your Step: Anticipated Perception for Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.29612
- Source: arXiv
- Date: 2026-10-21
- Authors: Matthias Heyrman, Chenhao Li, Ioannis Dadiotis, Marco Hutter
- Topics: 感知式步态 / 落脚点预测 / 高程图 / 人形 / 零样本迁移
- Summary: 轻量落脚点预测模型与策略一同训练,仅依据本体感知与速度指令,选出预测落脚点周围的小块高程图,使策略只看到与步伐相关的地形。
- Notes: 摘要称达到给定地形难度所需训练迭代约为完整地图的三分之一,在落脚点稀疏场景和未见地形上更优,并与训练成本数倍的注意力编码器相当。零样本迁移到 Unitree G1,室内外障碍、楼梯、沟隙与下台阶均可通过。未找到代码链接。

### End-to-End Reinforcement Learning for Quadrupedal Jumping in Lunar Gravity
- Link: https://arxiv.org/abs/2610.29586
- Source: arXiv
- Date: 2026-10-21
- Authors: Levin Müller, Oliver Fischer, Marco Trentini, Yusuke Tanaka, Marco Hutter
- Topics: 四足 / 跳跃 / 行星探索 / 强化学习 / 仿真到真机
- Summary: 多阶段强化学习得到单一端到端策略,仅使用任务可用的机载传感即可完成月球重力下的指令式定点跳跃。
- Notes: 仿真中落点误差小于机体尺寸,并分析了力矩/功率需求以及飞行阶段最长 1 秒控制更新冻结下的鲁棒性。真机在月球重力卸载下完成垂直跳跃,力矩与功率曲线与仿真一致;据摘要,定点跳跃仅在仿真中展示。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### HorizonRobotics/HoloMotion
- Link: https://github.com/HorizonRobotics/HoloMotion
- Category: control / motion tracking / retargeting / teleoperation
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo(sim2sim 回放)
- Deploy: both
- Summary: Apache-2.0 的人形全身控制基础模型工具栈,涵盖重定向(HoloRetarget)、动作跟踪策略训练、ONNX 策略包以及 G1 真机部署。
- Notes: 2026-10-12 的 v2.0 更新提供单一的稀疏到全身控制策略,并展示了初步的 1 点和 5 点真机遥操作;v2.0.0 权重已发布在 Hugging Face。README 标注 v2.0 仍为预览版,真机步态与跟踪质量仍在改进;并计划于 2026 年 10 月底发布 HoloMotion-2 技术报告与 v2.1。相关:papers.md 中的 HoloMotion-1 技术报告。

### Roboparty/RP1
- Link: https://github.com/Roboparty/RP1
- Category: toolkit / hardware platform
- Robot Type: humanoid
- Deploy: hardware
- Summary: RoboParty 全开源人形平台的总览仓库,链接机械、电子、固件、机器人描述、部署与训练等子仓库(24/28/30/42 自由度版本)。
- Notes: 总览仓库为 GPL-3.0,各子仓库许可证各自不同(第三方汇总称硬件为 CERN-OHL-W-2.0)。训练代码位于 `roboparty_train`(步态、动作模仿、行为基础模型);README 的演示部分标注为"Coming soon"。2026-10-15 的公开发布日期来自第三方 GitHub issue,而非 README。相关:repos.md 中的 Roboparty/UFO。

### iit-DLSLab/morphosymm-rsl-rl
- Link: https://github.com/iit-DLSLab/morphosymm-rsl-rl
- Category: RL / toolkit
- Robot Type: general / legged
- Simulator: Isaac Lab
- Deploy: sim
- Summary: BSD-3-Clause 的 RSL-RL PPO 扩展,通过对称数据增强与基于 `symmetric_learning` 的显式等变网络,将形态对称性用于足式运动学习。
- Notes: README 徽章显示 Isaac Lab v3.0.0 与 rsl-rl v5.4.2;mjlab 仅作为仓库话题标签出现。GitHub 话题页显示其于 2026-10-09 更新,但未能在仓库页面确认。相关论文:Morphological Symmetries in Robotics(IJRR 2025)与 Leveraging Symmetry in RL-based Legged Locomotion Control(IROS 2024)。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

本次运行未核实到新的实验室或教授信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 暂无新核实的岗位
- Type: PhD / RA / Internship / Research Engineer / Postdoc
- Source: 官方来源复核
- Deadline: unknown
- Topics: humanoid / quadruped / locomotion / robot learning
- Status: watching
- Notes: 未能在官方页面确认任何岗位。现有条目不变;此前提议移除的 LAAS-CNRS 安全强化学习博士岗位(截止 2026-07-31,已过期)仍待确认。

</details>
