[English](../../drafts/legged-daily-2026-07-28.md) | **中文**
# 腿足机器人日报 - 2026-07-28

## 摘要
- 今天有 3 篇新论文达到收录标准：可复用的离散人形运动先验、用于四足机器人强化学习的 wrench 增强探索，以及显式建模物理变量多项式交互的具身运动策略层。
- Hybrid Motion Prior 是其中最强的硬件信号：一个冻结的 RVQ 技能接口被复用于速度跟踪、点目标导航和跌倒恢复训练，速度跟踪策略还部署到了真实 Unitree G1。
- WARL 在训练早期临时开放虚拟力/力矩动作，再通过基于成功率的课程逐步移除；作者也报告了重要负面结果——这类辅助可能诱导未充分利用机器人本体动力学的动作。
- 两个新仓库达到收录标准：Unitree Go2 上有明确量化结果的 Isaac Lab DreamWaQ 复现，以及用于 G1 行走与参考动作跟踪的实验性 C++17 部署控制器。
- JSK 的 WARL 和密歇根大学的 PRISM 构成值得跟踪的研究网络更新；今天没有核验到足够新且不重复的招聘机会。

<details>
<summary><strong>新论文</strong></summary>

### Learning Reusable Hybrid Motion Priors for Humanoid Locomotion from Motion Imitation
- 链接：https://arxiv.org/abs/2607.24083
- 来源：arXiv
- 日期：2026-07-27
- 作者：Valerio Belli、Valerio Modugno、Enrico Mingo Hoffman、Fabio Amadio
- 主题：人形机器人运动 / 动作模仿 / 强化学习 / 离散运动先验 / 残差向量量化 / Unitree G1
- 摘要：该三阶段流程把动作模仿专家蒸馏为冻结的本体感知编码器、残差向量量化码本和动作解码器，随后让下游运动策略选择离散码本条目，而不是从头重学底层动作。
- 备注：同一个 HMP 在仿真中复用于速度跟踪、点目标导航和跌倒恢复速度跟踪，速度跟踪策略还部署到真实 Unitree G1。作者报告，使用 rotation trick 训练码本可改善潜空间组织，并相较 straight-through estimator 减少下游跌倒。

### WARL: Wrench-Augmented Reinforcement Learning for Task-Agnostic Learning in Legged Robots
- 链接：https://arxiv.org/abs/2607.24036
- 来源：arXiv
- 日期：2026-07-27
- 作者：Keita Yoneda、Kento Kawaharazuka、Kei Okada
- 主题：四足机器人运动 / 强化学习 / 探索 / 力与力矩增强 / 课程学习
- 摘要：WARL 在训练动作空间中加入虚拟力和力矩指令，使困难行为更容易被探索到，再通过基于成功率的 switching curriculum 移除 wrench，最终保留仅使用关节控制的策略。
- 备注：四足实验覆盖多种地形和运动任务，不需要针对地形调整奖励或设计复杂课程。论文也指出局限：wrench 辅助可能产生未充分利用机器人本体物理特性的解，因此如何设计与本体结构一致的增强仍是开放问题。项目页：https://keitayoneda.github.io/kleiyn-warl/

### PRISM: Polynomial Representations for Interaction-Structured Motor Control
- 链接：https://arxiv.org/abs/2607.23473
- 来源：arXiv
- 日期：2026-07-26
- 作者：Seung Hyun Lee、Stella X. Yu
- 主题：人形机器人运动 / 运动策略架构 / 多项式交互 / 强化学习 / 模仿学习 / 柔顺控制
- 摘要：PRISM 增加紧凑的因式分解多项式模块，显式学习可观测物理变量之间的高阶交互，从而暴露标准 MLP 输入中隐含的功率、惯性、接触、打滑和柔顺线索。
- 备注：评测覆盖人形运动和接触丰富的操作任务。作者报告其优于标准 MLP 和参数规模匹配的更大 MLP，并在没有力、wrench、触觉、接触标签或导纳控制输入时实现无力传感柔顺行为。项目页：https://lsh3163.github.io/prism/

</details>

<details>
<summary><strong>新仓库</strong></summary>

### romankalyna/dreamwaq-isaaclab
- 链接：https://github.com/romankalyna/dreamwaq-isaaclab
- 类别：强化学习 / 复现 / 状态估计 / 运动控制
- 机器人类型：四足；Unitree Go2
- 仿真器：NVIDIA Isaac Lab 2.0 / Isaac Sim 4.5
- 部署：仿真；actor 观测按可部署的本体感知设计，但未报告实体机器人运行
- 摘要：一个 MIT 许可证的 DreamWaQ 复现，在 Isaac Lab 中实现非对称 actor-critic 与 CENet，让 Go2 策略从本体感知历史估计速度和潜在地形上下文，而地形扫描和真实速度只供训练阶段组件使用。
- 备注：README 报告 64 维可部署 actor 接近 235 维 privileged baseline，评测速度估计 MSE 为 0.0058 (m/s)^2。作者明确说明这是单随机种子复现，不是有统计支撑的原论文数值 replication，并列出与原方法的差异。仓库创建并最后推送于 2026-07-28；核验时 3 stars。

### M0M0ljh/Beyondmimic_Deploy
- 链接：https://github.com/M0M0ljh/Beyondmimic_Deploy
- 类别：部署 / 行走 / 动作跟踪 / 控制器
- 机器人类型：人形；Unitree G1
- 仿真器：Unitree MuJoCo，用于仿真测试
- 部署：通过 unitree_sdk2 DDS 和 ONNX Runtime 同时支持仿真与 G1 硬件
- 摘要：一个实验性 C++17 有限状态部署控制器，用于摇杆指令 G1 行走和参考动作跟踪，支持 x86_64/aarch64 构建、DDS 接入、ONNX 张量检查，并在多类运行故障下自动切换到 Damping。
- 备注：仓库不包含 ONNX 策略二进制文件，核验时也未检测到仓库许可证。README 明确警告它不是认证安全控制器，测试时必须悬挂机器人并安排操作员随时切换 Damping；当前尚未执行关节限位、目标变化率限制或配置中的力矩限制。仓库创建且最后代码推送于 2026-07-23；核验时 1 star。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### JSK Robotics Laboratory — WARL 作者团队
- 机构：东京大学
- 主页：https://www.jsk.t.u-tokyo.ac.jp/
- arXiv：https://arxiv.org/abs/2607.24036
- 实验室 / 院系：Graduate School of Information Science and Technology, Department of Mechano-Informatics；AI Center
- 关键主题：四足机器人运动 / 强化学习 / 探索 / 课程学习 / 机器人本体
- 备注：Keita Yoneda、Kento Kawaharazuka 和 Kei Okada 发布 WARL，把 JSK 网络的腿足机器人学习信号从任务特定动作生成延伸到更通用的探索机制。其对“不符合本体特性的 wrench 辅助”的明确负面结果尤其值得持续跟踪。
- 学生与代表工作：
  - [Keita Yoneda](https://keitayoneda.github.io/) — [WARL](https://keitayoneda.github.io/kleiyn-warl/)

### Stella X. Yu / 密歇根大学运动控制作者团队
- 机构：University of Michigan, Ann Arbor
- 主页：https://lsh3163.github.io/prism/
- arXiv：https://arxiv.org/abs/2607.23473
- 实验室 / 院系：Computer Science and Engineering
- 关键主题：人形机器人运动 / 具身运动控制 / 多项式策略表示 / 强化学习 / 模仿学习 / 无力传感柔顺
- 备注：Seung Hyun Lee 和 Stella X. Yu 发布 PRISM，这是一个跨任务策略表示信号：通过显式物理变量交互，而不是单纯扩大通用 MLP，把人形运动和接触丰富操作联系起来。
- 学生与代表工作：
  - [Seung Hyun Lee](https://lsh3163.github.io/) — [PRISM](https://lsh3163.github.io/prism/)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今天没有从官方来源核验到足够新且高置信的腿足机器人招聘机会。此前已跟踪且仍有效的岗位，包括截止 2026-07-31 的 LAAS-CNRS Gepetto / CNRS-AIST JRL 人形机器人博士项目，以及 Amazon Robotics Compass 的安全运动岗位，本期不重复包装为新增项。

</details>
