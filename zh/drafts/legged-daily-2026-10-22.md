[English](../../drafts/legged-daily-2026-10-22.md) | **中文**
# Legged Daily - 2026-10-22

## 摘要
- SuperMimic 用一个可微世界模型训练人形动作跟踪器;据称 3 个 GPU 小时即超过 128 卡训练 7 天的基线,并迁移到 Unitree G1 真机。
- "Watch Your Step" 预测未来落脚点,仅在落脚点附近采样高程图,达到同等地形难度所需训练迭代约为原来的三分之一,并零样本迁移到 Unitree G1。
- ETH RSL 团队训练了面向月球重力的端到端四足跳跃策略,在重力卸载条件下完成真机垂直跳跃。
- 今日未核实到新的仓库、实验室/教授信号或招聘(本次会话无法使用 GitHub 搜索,上述论文也未找到项目/代码链接)。

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

本次运行未核实到新的仓库。

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
