[English](../../drafts/legged-daily-2026-07-31.md) | **中文**
# 腿足机器人日报 - 2026-07-31

## 摘要
- PAC-MAN 是今天最强的论文信号：它把全身控制屏障引导与机载掩码深度感知结合，并将轻量策略零样本迁移到 Unitree G1，真机 20 次投球成功躲避 19 次且没有摔倒。
- 论文最重要的系统结论是：更强的安全结构只有在感知持续观察到威胁时才有价值。固定相机下 Joint-CBF 引导会退化，主动跟踪或特权状态可恢复优势；更简单的 Link-CBF 则能依靠机载感知直接部署。
- 3 个有实质内容的实现仓库达到收录标准：G1 行走/平衡/安全摔倒 Isaac Lab 任务集、记录 18 个 checkpoint 演进过程的 SpotMicro 强化学习项目，以及带公开 checkpoint 的 Apache-2.0 轮腿平衡与跳跃课程项目。
- PAC-MAN 延续了 Caltech AMBER Lab 近期 HANDOFF、MPC-RL 之后的人形安全与控制研究，使其继续成为高优先级来源。无需仅因本论文新增实验室条目，但重复出现的 G1 真机部署进一步增强了现有来源信号。
- 今天没有达到“新增”标准的招聘机会。此前已跟踪的 LAAS-CNRS Gepetto 人形机器人安全强化学习博士职位在核验时仍有效，将于今天 2026-07-31 23:59 截止。

<details>
<summary><strong>新论文</strong></summary>

### PAC-MAN: Perception-Aware CBF-RL for Whole-Body Safety in Humanoid Dodgeball
- 链接：https://arxiv.org/abs/2607.28623
- 来源：arXiv / 官方项目页
- 日期：2026-07-30
- 作者：Lizhi Yang、Junheng Li、Aaron D. Ames
- 主题：人形机器人安全 / 控制屏障函数 / 强化学习 / 机载感知 / 全身控制 / sim-to-real / Unitree G1
- 摘要：PAC-MAN 使用逐连杆或关节空间 CBF 引导训练人形机器人全身躲避动作，而部署策略只接收本体感知和头部相机输出的分割掩码深度图。
- 备注：固定相机 Link-CBF 策略无需微调即可迁移到实体 Unitree G1，在 20 次手抛球中成功躲避 19 次、零摔倒，并能在投球间自行走回站位。Joint-CBF 在准确球状态下表现最好，但固定相机丢失威胁目标时效果下降；跟踪云台或特权运行时过滤器可恢复其优势。项目页：https://lzyang2000.github.io/perceptive_cbf_rl/。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### ductnguyen-dtn/g1-humanoid-locomotion
- 链接：https://github.com/ductnguyen-dtn/g1-humanoid-locomotion
- 类别：强化学习 / 运动控制 / 平衡 / 安全摔倒 / 调试记录
- 机器人类型：人形；Unitree G1
- 仿真器：NVIDIA Isaac Lab / Isaac Sim，提供 RSL-RL 训练入口
- 部署：仅提供仿真任务；未展示真机部署
- 摘要：一组紧凑的 G1 Isaac Lab 任务，覆盖平地速度跟踪、带推扰恢复的站立平衡，以及安全摔倒行为，并同时包含官方整理版和自行导入的 29-DoF 资产配置。
- 备注：仓库记录了两个有复用价值的失败模式：导入资产的近零惯量会使 PhysX 失稳；如果推扰几乎不造成摔倒，或 episode 在落地前终止，安全摔倒奖励就无法学习。仓库提供环境配置和使用说明，但没有已训练策略权重或真机结果；核验时未检测到仓库许可证。

### ductnguyen-dtn/spotmicro-locomotion
- 链接：https://github.com/ductnguyen-dtn/spotmicro-locomotion
- 类别：强化学习 / 低成本四足 / 资产调试 / 实验追踪
- 机器人类型：四足；手工搭建的 SpotMicro，使用 12 个 MG996R 舵机
- 仿真器：NVIDIA Isaac Lab / Isaac Sim
- 部署：记录了实体机器人装配、标定与硬件测试，但学习步态目前仍是仿真结果，且未提供策略权重
- 摘要：一个 Isaac Lab SpotMicro 运动项目，完整保留了从 URDF/USD 根关节被焊死导致无法移动，到获得稳定前进行走的演进路径，并记录 18 个正式 checkpoint、被否决的消融实验及其对应配置快照。
- 备注：最值得复用的经验是诊断方法：策略动作非零但基座速度始终精确为零，说明问题是固定根关节而非强化学习失败。当前仿真基线仍有后腿步态不对称，仓库也没有宣称已解决步态或完成学习策略的真机部署。未检测到本仓库许可证；其引用的上游 SpotMicro 固件/ROS 项目采用 MIT 许可证。

### zyicome/Wheel-Legged-Lab
- 链接：https://github.com/zyicome/Wheel-Legged-Lab
- 类别：强化学习 / 轮腿平衡 / 跳跃 / 课程学习 / VMC
- 机器人类型：两轮两腿欠驱动机器人
- 仿真器：NVIDIA Isaac Lab 2.3.2 / Isaac Sim 5.1.0，使用 RSL-RL PPO
- 部署：仅仿真；尚未完成 sim-to-real 验证
- 摘要：一个 Apache-2.0 的 Isaac Lab 项目，通过虚拟模型控制把策略输出映射为实际关节力矩，并逐级训练平衡、速度/航向跟踪、高度控制、分阶段跳跃、空中收腿、移动跳跃、目标落点和 oracle 障碍物跨越。
- 备注：仓库包含公开的移动跳跃 checkpoint、TensorBoard 事件、视频、分阶段训练脚本和机器人资产。README 展示了最高跨越 7 cm 障碍物的仿真结果，并明确说明这是学习/复现项目，尚无实体部署，也没有多随机种子的统计验证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Caltech AMBER Lab / Aaron D. Ames
- 机构：California Institute of Technology
- 主页：https://amber.caltech.edu/
- 来源：https://arxiv.org/abs/2607.28623 和 https://lzyang2000.github.io/perceptive_cbf_rl/
- 关键主题：人形机器人安全 / 控制屏障函数 / 强化学习 / 全身控制 / 机载感知 / sim-to-real
- 备注：PAC-MAN 是已跟踪 AMBER 来源网络的新进展。它把该团队近期的人形控制接口与 MPC 引导强化学习工作，推进到部分机载感知条件下的反应式全身安全，并完成 Unitree G1 零样本真机评测。应将其作为现有实验室条目的更新，而不是新增实验室。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### LAAS-CNRS Gepetto Team — 人形机器人安全强化学习博士职位
- 类型：PhD
- 地点：法国图卢兹，部分研究将在日本筑波 CNRS-AIST JRL 进行
- 来源：官方网站 — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止时间：2026-07-31 23:59
- 主题：人形机器人 / 腿足运动 / 强化学习 / MPC / 全身控制 / 安全控制
- 状态：核验时仍有效；此前已跟踪机会的最后一天提醒
- 备注：官方页面在 2026-07-31 仍可访问。36 个月课题将用 RL 对接触、落脚点、步态和行为切换做离散决策，再由在线 MPC 生成满足约束的连续全身动作，并计划在 PAL Robotics Kangaroo 和/或 Unitree H1/R1 上验证。今天不建议新增招聘条目；若页面在截止后关闭，下一次运行应复核并提出 stale removal。

</details>
