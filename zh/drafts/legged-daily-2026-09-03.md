[English](../../drafts/legged-daily-2026-09-03.md) | **中文**
# 腿足机器人日报 - 2026-09-03

## 摘要
- WM-LOCO 用循环世界模型为 Unitree G1 提供面向稀疏落脚点的预测性视觉上下文，并在踏石、楼梯和跨沟三类实机地形上报告 93.3% 的平均成功率。
- Safe-Stop 将紧急停止控制与“当前是否仍可安全停下”的学习决策分离，在 G1 上报告 96.4% 的分布外停止成功率。
- FOCUS 以连续的单足正向运动学可靠度替代二值足接触门控，并在人形机器人仿真和实机试验中报告显著的里程计误差下降。
- 两个值得关注的新代码发布分别覆盖多 IMU 四足状态估计和可复现的 13 策略 G1 行走基准；第三个仓库为桌面六足机器人提供 Apache-2.0 的 Python/MCP 开发栈。
- 新论文带来 D-Robotics，以及 UC Berkeley、CMU、Stanford 的有价值信源网络；今天未核验到足够新且高置信的招聘机会。

<details>
<summary><strong>新论文</strong></summary>

### World-Model-Augmented Visual Locomotion for Humanoids on Foothold-Constrained Terrain
- 链接：https://arxiv.org/abs/2609.02542
- 来源：arXiv
- 日期：2026-09-02
- 作者：Yuxi Liu、Lijun Han、Ziming Wang、Ao Zhang、Cong Yang、Wei Sui
- 主题：人形机器人、视觉运动、世界模型、强化学习、落脚点受限地形
- 摘要：提出 WM-LOCO，联合训练循环状态空间世界模型与 PPO 策略，让由本体感知和单路机载深度图产生的预测特征引导 Unitree G1 穿越稀疏落脚点，且无需显式落脚点标签。
- 备注：同一套全机载策略在实机上通过踏石、楼梯和沟隙，平均成功率为 93.3%。仿真中，对齐基线在沟隙和踏石上的成功率为 0%，而 WM-LOCO 在楼梯上还改善了步幅效率和骨盆加速度。

### Humanoid Safe Stop via Learned Stoppability Value
- 链接：https://arxiv.org/abs/2609.02358
- 来源：arXiv
- 日期：2026-09-02
- 作者：Junfeng Long、Pieter Abbeel、Koushil Sreenath、Roberto Horowitz、Guanya Shi、C. Karen Liu
- 主题：人形机器人、安全、紧急停止、可达-避障、学习价值估计
- 摘要：将紧急停止表述为 reach-avoid 问题，把学习停止策略与停止概率、reach-avoidance 估计器组合起来；仅当两者都判断可恢复时执行停止，否则切换到阻尼倒地策略。
- 备注：项目页报告 Unitree G1 上 96.4% 的分布外停止成功率和 3.89% 的不安全批准率。停止策略与估计器不依赖前序行为，可跨上游任务迁移而无需重新训练。

### FOCUS: Foot Observation Confidence for Robust Humanoid Proprioceptive Odometry
- 链接：https://arxiv.org/abs/2609.02222
- 来源：arXiv
- 日期：2026-09-02
- 作者：Kaixin Feng、Angsong Li、Shaopeng Zhang、Enyu Li、Peiwen Lin、Chuang Wang、You Li、Haiyu Lan
- 主题：人形机器人、本体里程计、状态估计、EKF、足部可靠性、Transformer
- 摘要：提出由自动生成仿真信号训练的连续单足正向运动学可靠度权重，用于融合运动学与 IMU 速度估计并自适应调整 EKF 观测协方差，避免硬切换式接触门控。
- 备注：部署端因果 Transformer 仅使用 IMU 和关节运动学。作者报告仿真行走 ATE 降低 83.7%，19 段实机行走 ATE 降低 70.8%，四套实机动态动作的平均 ATE 降低 42.7%。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### DogLegs
- 链接：https://github.com/YibinWu/DogLegs
- 类别：工具包
- 机器人类型：四足机器人
- 仿真器：无
- 部署：数据
- 摘要：独立 C++17 状态估计器，利用一个机身 IMU、四个腿部 IMU、关节编码器和足端力估计机身位姿、速度及 IMU 误差，并发布了野外数据集和 IROS 2025 论文链接。
- 备注：仓库提供停车场、草地、沥青路、施工现场和越野序列配置，估计器运行时不依赖 ROS。仓库创建于 2026-09-03；未检测到仓库许可证，复用条款尚不明确。

### teleop-walking-benchmark
- 链接：https://github.com/rhoyn/teleop-walking-benchmark
- 类别：工具包
- 机器人类型：人形机器人
- 仿真器：MuJoCo
- 部署：仿真
- 摘要：把 13 个开源 Unitree G1 行走策略接入统一 C++ 接口，并在 MuJoCo 中用相同的随机航点路线和冲击恢复试验进行评测。
- 备注：公开的 100 随机种子测试共含 1,300 次运行；GR00T-WBC 完成 71/100 条路线，没有任何策略完成全部种子。基准代码采用 MIT，但各检查点条款不同，NOTICE 中记录了非商业、未声明和仅限仿真等限制。

### palmimo-devkit
- 链接：https://github.com/Jizai-inc/palmimo-devkit
- 类别：工具包
- 机器人类型：六足机器人
- 仿真器：无
- 部署：实机
- 摘要：面向 Palmimo 的 Apache-2.0 Python SDK、运动引擎、MCP server 和 agent 示例栈；Palmimo 是基于 Raspberry Pi 5、采用 18 舵机三脚架步态的桌面六足机器人，同时支持无需连接硬件的纯计算 dry-run。
- 备注：仓库创建于 2026-09-02，并明确标为 pre-release。当前支持实机操作，但未发布制造设计文件，面向机器人学习的仿真资产仅计划逐步开放。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### D-Robotics 视觉人形运动网络
- 机构：D-Robotics / 北京邮电大学 / 哈尔滨工业大学 / 苏州大学
- 主页：https://arxiv.org/html/2609.02542
- arXiv：https://arxiv.org/abs/2609.02542
- 实验室 / 院系：以 D-Robotics 为主的论文作者机构网络
- 关键主题：人形机器人、视觉运动、世界模型、强化学习、稀疏落脚点
- 备注：WM-LOCO 带来一个围绕 Unitree G1 全机载深度视觉运动的产业主导信源网络。通讯作者和项目负责人 Wei Sui 来自 D-Robotics，合作者网络还连接北京邮电大学、哈尔滨工业大学和苏州大学。

### UC Berkeley / CMU / Stanford 人形安全协作网络
- 机构：加州大学伯克利分校 / 卡内基梅隆大学 / 斯坦福大学
- 主页：https://junfeng-long.github.io/safestop/
- arXiv：https://arxiv.org/abs/2609.02358
- 实验室 / 院系：跨机构论文合作网络
- 关键主题：人形机器人、安全控制、reach-avoid 分析、强化学习、紧急停止
- 备注：Safe-Stop 连接 Junfeng Long、Pieter Abbeel、Koushil Sreenath、Roberto Horowitz、Guanya Shi 和 C. Karen Liu，形成了学习式人形控制与形式化可恢复性推理交叉方向的有价值信号。
- 学生与代表工作：
  - [Junfeng Long](https://junfeng-long.github.io/) — [Humanoid Safe Stop via Learned Stoppability Value](https://junfeng-long.github.io/safestop/)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次运行未从官方来源核验到足够新、仍开放且高置信的腿足机器人职位。通用网页搜索受到 bot challenge 影响，因此没有把未经官方验证的聚合站结果加入草稿。

</details>
