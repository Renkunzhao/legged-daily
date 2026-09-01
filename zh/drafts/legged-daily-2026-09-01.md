[English](../../drafts/legged-daily-2026-09-01.md) | **中文**
# 腿足机器人日报 - 2026-09-01

## 摘要
- SleepWalking（SWAQ）将部分可观测条件下的盲走重新表述为信息保持问题，并报告在降低推理成本的同时取得优于 DWAQ 的地形推进能力。
- IIT 的 HHCM 研究线提出紧凑型 2 自由度人形机器人踝关节执行器，通过两个定制凸轮共享一个气弹簧，为俯仰和横滚提供力矩补偿。
- 三个新 Unitree G1 仓库分别覆盖地形相对的崎岖地形控制与 sim-to-sim、状态估计感知强化学习、面向搜救的风险感知导航；三者仍处早期阶段，当前均未检测到许可证。
- 新论文带来了西北工业大学—上海交通大学—云幕智能的盲走合作网络，以及 IIT HHCM 的新执行器设计信号。
- 两个已跟踪机会需要清理：EPFL BioRob 已将人形运动博士/博士后职位标为 CLOSED，Inria Auctus 四足机器人协同设计博士职位也已过截止日期。

<details>
<summary><strong>新论文</strong></summary>

### SleepWalking: Privileged Representation Shaping for End-to-End Blind Locomotion in Legged Robots
- 链接：https://arxiv.org/abs/2608.30883
- 来源：arXiv
- 日期：2026-08-31
- 作者：Zheng Pan、Tenghui Wang、Peilin Li、Shiyu Zhou、Hao Sun、Yan Ma、Liang Yu、Liang He
- 主题：腿足机器人盲走、强化学习、表征学习、特权信息、部分可观测性
- 摘要：提出 SWAQ，一种单阶段循环 actor-critic；训练时用下一时刻特权物理量重建来塑造历史表征，部署时则直接从本体感知历史输出动作，不把显式估计器输出接入控制通路。
- 备注：在对齐训练设置下，作者报告其峰值平均地形等级比 DWAQ 高 15.0%，每控制步推理 MAC 数少 44.4%。论文还包含逐层表征探针与理论分析，但今天检查到的官方来源尚未给出代码或项目页链接。

### A Dual-Cam Parallel Elastic Actuator with Shared Gas-Spring Compensation for Humanoid Ankles
- 链接：https://arxiv.org/abs/2608.30832
- 来源：IEEE AIM 2026 / arXiv
- 日期：2026-08-31
- 作者：Jingcheng Jiang、Yifang Zhang、Nikos G. Tsagarakis
- 主题：人形机器人、执行器、并联弹性、踝关节、机械优化
- 摘要：提出一种 2 自由度人形机器人踝关节并联弹性执行器，用两个定制凸轮模块和一个共享气弹簧，在紧凑小腿空间内提供耦合的俯仰/横滚力矩补偿。
- 备注：工作建立了耦合模型与由目标力矩曲线合成凸轮轮廓的优化流程，并通过完整小腿 CAD 集成、运动学仿真和静态有限元分析验证概念；当前证据仍是设计与仿真验证，而非实体原型实验。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### humanoid-g1-locomotion
- 链接：https://github.com/hrx2025lucky-lab/humanoid-g1-locomotion
- 类别：强化学习
- 机器人类型：人形机器人
- 仿真器：Isaac / MuJoCo
- 部署：仿真
- 摘要：Unitree G1 运动控制工作区，当前实现了 Isaac Lab 中基于地形相对量的崎岖地形观测/奖励，以及 Isaac Lab 到 MuJoCo 的 sim-to-sim 验证路径，显式对齐关节顺序、观测、PD 参数、动作尺度和控制频率。
- 备注：仓库记录了一个具体问题：世界系根节点高度会在下沉地形上误判机器人跌倒，并改用相对地形高度扫描。更大的 11 项路线图多数尚未完成；未宣称实机结果，截至 2026-09-01 未检测到许可证。

### G1-EKF-Locomotion
- 链接：https://github.com/baodo0710/G1-EKF-Locomotion
- 类别：强化学习
- 机器人类型：人形机器人
- 仿真器：Isaac
- 部署：仿真
- 摘要：一个开发中的 Isaac Lab 扩展，用 IMU 积分与支撑腿里程计融合得到的卡尔曼滤波速度估计替代 Unitree G1 的特权基座线速度，并直接针对传感器估计状态训练 PPO。
- 备注：维护者报告估计器 MAE 为 0.26 m/s，平地策略已收敛；崎岖地形步态问题、ESKF 和 sim-to-real 仍在路线图中。实现刚发布，结果为维护者自报，截至 2026-09-01 未检测到许可证。

### unitree-g1-risk-aware-navigation
- 链接：https://github.com/TFGUnitreeG1/unitree-g1-risk-aware-navigation
- 类别：工具包
- 机器人类型：人形机器人
- 仿真器：Isaac
- 部署：仿真
- 摘要：集成 G1 行走策略检查点、航点导航、RGB-D/YOLO 地形分类、空间风险地图、自适应航点路线、搜救仿真场景和实验后处理工具。
- 备注：仓库包含三个运动策略检查点、USD 场景、路线文件和评测脚本，但 YOLO 权重需外部提供，所查材料也未宣称实机验证。截至 2026-09-01 未检测到许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 西北工业大学 / 上海交通大学盲走合作网络
- 机构：西北工业大学 / 上海交通大学 / 云幕智能制造有限公司
- 主页：https://arxiv.org/html/2608.30883v1
- arXiv：https://arxiv.org/abs/2608.30883
- 实验室 / 院系：论文作者机构网络
- 关键主题：四足机器人、盲走、强化学习、表征学习、部分可观测性
- 备注：SWAQ 将西北工业大学共同通讯作者 Liang Yu、Liang He，与上海交通大学 Tenghui Wang、Shiyu Zhou，以及云幕智能 Peilin Li 连接起来。这是一个值得继续跟踪的本体感知运动和历史表征学习新信源网络。

### Humanoids and Human Centered Mechatronics（HHCM）研究线
- 机构：意大利技术研究院（IIT）
- 主页：https://arxiv.org/html/2608.30832v1
- arXiv：https://arxiv.org/abs/2608.30832
- 实验室 / 院系：Humanoids and Human Centered Mechatronics Research Line
- 关键主题：人形机器人、执行器、并联弹性、机械设计、能效
- 备注：Jingcheng Jiang、Yifang Zhang 和 Nikos G. Tsagarakis 为 IIT 人形机电方向增加了一个紧凑型共享弹簧踝关节设计信号；它与仓库已跟踪的 IIT Dynamic Legged Systems 形成不同的硬件/执行器补充。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 拟删除 / 过期条目 — EPFL BioRob 人形运动博士与博士后
- 当前状态：不再可申请
- 原因：EPFL BioRob 官方招聘页现已将 2026 年秋季人形机器人神经力学博士与博士后职位标为 CLOSED，并明确说明职位已经关闭。
- 已检查来源：EPFL BioRob 官方招聘页 — https://www.epfl.ch/labs/biorob/openings/

### 拟删除 / 过期条目 — Inria Auctus / LAAS-CNRS Gepetto 四足机器人协同设计博士
- 当前状态：已过期
- 原因：官方申请截止日期为 2026-08-31，现已过去；除非官方页面明确延长或重新开放，否则不应继续作为开放职位展示。
- 已检查来源：Inria 官方职位页 — https://jobs.inria.fr/public/classic/en/offres/2026-10319

</details>
