[English](../../drafts/legged-daily-2026-08-04.md) | **中文**
# Legged Daily - 2026-08-04

## 摘要
- 3 篇新论文达到收录门槛：StableMimic 在真实 Unitree G1 上统一人形动作跟踪与结构化跌倒恢复；Open-DiffLoco 使用可微 MuJoCo MJX 训练可部署到硬件的盲式四足运动策略；残差自适应 InEKF 则在不依赖足端力传感的情况下改善 Go2 状态估计。
- 2 个仓库达到实现质量门槛。Open-DiffLoco 公开论文对应的可微训练与 C++ 部署栈；此前尚不可访问的 RoboNaldo 官方代码现已公开 Isaac Lab 训练课程、参考动作、部署路径和真实 G1 演示。
- 今天最强的共同主题是可部署性，而非仅报告仿真分数：两个入选学习系统都报告了 Unitree 真机部署，状态估计论文也使用室内和室外 Go2 数据集进行评估。
- 今天没有从第一方来源核验到新的实验室或教授动态；作者机构和仓库归属没有被单独视为机构层面的公告。
- ETH Zurich RSL 的滚动岗位仍有效。LAAS-CNRS 安全强化学习人形博士职位已被官方门户明确标记为不可用，继续作为待确认的过期删除建议。

<details>
<summary><strong>新论文</strong></summary>

### StableMimic: Smooth Human-Like Recovery for Humanoid Motion Tracking - Learning Beyond the Tracking Distribution for Structured Post-Fall Behavior
- 链接: https://arxiv.org/abs/2608.02385
- 来源: arXiv
- 日期: 2026-08-03
- 作者: Weihao Wu, Ming Huang, Ruofei Liu, Jinglei Nie, Shuxiang Guo, Chunying Li
- 主题: 人形动作跟踪 / 跌倒恢复 / 模仿学习 / 专家混合 / 安全 / 真实机器人部署
- 摘要: StableMimic 训练独立的跟踪与恢复专家，并通过本体感知门控连续融合动作，使 Unitree G1 能从接触丰富的跌倒状态自主恢复并继续执行指令，无需外部策略切换。
- 备注: 预印本称其在重定向后的 LAFAN1 舞蹈子集上，五种方法对比中的四项跟踪指标均为最低误差；在每种方法 100 次配对推倒实验中实现 100/100 恢复，并展示了真实 G1 舞蹈和站立参考部署。上述结果来自作者给定协议，尚未经过正式同行评审。

### Open-DiffLoco: Open-Source Differentiable Learning for Deployable Blind Quadruped Locomotion
- 链接: https://arxiv.org/abs/2608.02069
- 来源: arXiv
- 日期: 2026-08-03
- 作者: Martin Opat
- 主题: 四足运动 / 可微仿真 / MJX / SHAC / sim-to-real / 盲式控制
- 摘要: Open-DiffLoco 在 MuJoCo MJX 中实现 SHAC 和带雅可比增强的 critic 目标，训练仅依赖本体感知的盲式运动策略，并迁移到真实 Unitree Go2；部署策略不需要基座线速度、参考轨迹或复杂辅助奖励。
- 备注: 论文报告在 RTX 5080 上使用不到 6 GB 显存、20–60 分钟完成训练，达到低于 0.2 m/s 的全向速度跟踪均方根误差、超过 1 m/s 的速度，并能应对不平地形和侧向推力。关联源码和部署文档已经公开；数值仍属于作者报告的预印本结果。

### Residual-Based Adaptive Kalman Filtering for Legged Robot State Estimation
- 链接: https://arxiv.org/abs/2608.02316
- 来源: arXiv
- 日期: 2026-08-03
- 作者: Mihaela Popescu, Dennis Mronga, Shivesh Kumar, Frank Kirchner
- 主题: 腿足机器人状态估计 / 不变 EKF / 自适应协方差 / 传感器融合 / 四足机器人 / 本体感知
- 摘要: 该方法根据滤波残差和创新量在线调整 InEKF 的过程噪声与测量噪声协方差，降低不同步态和环境下对固定专家调参的依赖。
- 备注: 在 Unitree Go2 室内与室外数据集上，作者报告仅自适应测量协方差即可让小跑步态的精度比固定调参 InEKF 提高 25%，并在无需足端力测量或额外参数调整的情况下达到与足端力方法相当的性能。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### MartinOpat/open-diffloco
- 链接: https://github.com/MartinOpat/open-diffloco
- 类别: 可微强化学习 / 四足运动 / sim-to-real / 部署栈
- 机器人类型: 四足机器人；Unitree Go2
- 仿真器: 使用 MuJoCo MJX 进行可微训练
- 部署: 通过 Unitree SDK 的 C++ 部署路径运行于真实 Unitree Go2，并可选支持 ROS 2
- 摘要: Open-DiffLoco 官方实现提供 SHAC 与 JAVE 训练配置、包含或移除特权观测及运动学参考的多种 actor 变体、checkpoint 导出和 C++ 策略部署工具。
- 备注: 仓库包含可复现的 CLI 配置和详细部署文档，但当前 GitHub 快照没有识别出明确的 SPDX 许可证。硬件指标应结合关联预印本及其报告的实验条件解读。

### OpenDriveLab/RoboNaldo
- 链接: https://github.com/OpenDriveLab/RoboNaldo
- 类别: 强化学习 / 人形全身控制 / 动作引导课程学习 / 足球 / sim-to-real
- 机器人类型: 人形机器人；Unitree G1
- 仿真器: NVIDIA Isaac Lab 2.3.2 / Isaac Sim 5.1.0，采用 RSL-RL PPO
- 部署: 仿真与真实 Unitree G1；配套部署仓库将策略导出为 ONNX 并在硬件上运行
- 摘要: 现已公开的官方代码通过动作跟踪、静止球适配和移动球任务泛化三个阶段训练人形足球射门策略，再结合板载感知部署到真实 G1。
- 备注: 采用 MIT 许可证的仓库包含 Isaac Lab 任务扩展、分阶段课程参数、默认重定向右脚踢球动作、训练与评估脚本，以及固定版本的部署代码和真实机器人演示链接。该项目论文已在 2026-06-10 收录，当时代码链接返回 404；本条跟踪的是后来公开的实现，并非重复收录论文。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有从第一方来源核验到新的实验室或教授动态。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab — 滚动研究与工程岗位
- 类型: PhD / PostDoc / 研究人员或软件工程师 / 机器人设计工程师 / 嵌入式系统工程师 / 电子工程师
- 地点: 瑞士苏黎世
- 来源: 官方网站 — https://rsl.ethz.ch/the-lab/open-positions.html
- 截止时间: rolling / 官方页面未注明
- 主题: 腿足机器人 / 移动操作 / 运动规划 / 模型预测控制 / 强化学习 / 感知 / 导航 / 执行器 / 遥操作 / 嵌入式系统
- 状态: 2026-08-04 复核仍有效；此前已跟踪，不是新的 master-list 条目
- 备注: 官方页面仍提供滚动 PhD 与 PostDoc 申请链接，并继续列出研究、软件、机器人设计、嵌入式和电子工程岗位，工作与腿足机器人和现场部署直接相关。

### 拟删除 / 过期条目 — LAAS-CNRS Gepetto Team 人形机器人安全强化学习博士职位
- 当前状态: 已过期 / 官方职位不可用
- 原因: 所列 2026-07-31 23:59 截止时间已经过去，CNRS 官方门户现已明确显示“The requested offer is no longer available”。确认后应从 active master list 删除或标记为过期。
- 已检查来源: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
