[English](../../drafts/legged-daily-2026-09-13.md) | **中文**
# 腿足机器人日报 - 2026-09-13

## 摘要
- Actuator Dynamics Curricula 将仿真关节刚度作为课程变量，使 Spot 四足机器人策略学会可行域狭窄的“四足站立到手倒立”转换，并迁移到实机。
- 一套形态感知重定向流程将通用 SMPL-X 人体动作映射到轮式 Galaxea R1 Pro，联合处理平面底盘运动、躯干替代、手臂跟踪和车轮指令解码。
- Frame-Coded Legged Locomotion 从理论上连接粗糙地形接触丢失与有限帧擦除编码，推导多足步态的冗余、重建与机械刚度极限。
- 两个新仓库覆盖互补入口：带 CAD/URDF/Isaac Sim 资产的低成本 12 自由度四足平台，以及带 ONNX 和 ROS 2 推理脚手架的 MuJoCo PPO 原型。两者均处早期阶段，且尚未选择许可证。
- Humanoid 新发布温哥华 Senior Low-Level Control Engineer 岗位，聚焦执行器/关节控制、实时 C++、ROS 2、EtherCAT/CAN、系统辨识和实机调试。

<details>
<summary><strong>新论文</strong></summary>

### Actuator Dynamics Curricula for Narrow-Viability Tasks in Legged Robot Learning
- 链接：https://arxiv.org/abs/2609.09492
- 来源：arXiv / CoRL 2026
- 日期：2026-09-08
- 作者：Kousheek Chakraborty、Chandan K. Rajendra、Ayham Alharbat、Abeje Y. Mersha
- 主题：四足机器人学习 / 强化学习 / 执行器动力学 / 课程学习 / 仿真到现实
- 摘要：提出执行器动力学课程：先以较高仿真关节刚度开始训练，再随回合完成度提升逐步退火到系统辨识得到的实机数值，从而扩大易因早期终止而难以探索的任务初始可行域。
- 备注：作者通过倒立摆可行域分析和 Boston Dynamics Spot 的“四足站立到手倒立”转换验证该机制，报告 10 个仿真种子均成功并迁移到实机。这些是作者报告结果，本次未独立复现。

### Morphology-Aware Human Motion Retargeting for Wheeled-Humanoid Loco-Manipulation
- 链接：https://arxiv.org/abs/2609.11357
- 来源：arXiv
- 日期：2026-09-10
- 作者：Chenbo Xia、Chao Ye
- 主题：轮式人形机器人 / 动作重定向 / 移动操作 / 微分逆运动学 / 强化学习
- 摘要：将多数据集 SMPL-X 动作转换为 Galaxea R1 Pro 可执行行为，把人体下肢运动重新分配到平面轮式底盘与串联躯干，同时保留与操作任务相关的手臂几何关系。
- 备注：流程结合形态感知微分 IK、以肩部为根的分层手臂重定向、躯干替代、连续车轮转向/滚动解码，以及 Isaac Lab 中的 BaseDecode 策略。作者明确将定量策略比较推迟到后续版本，因此当前应视为可复现流程，而非完整基准结果。

### Frame-Coded Legged Locomotion over Noisy Terrain
- 链接：https://arxiv.org/abs/2609.10273
- 来源：arXiv
- 日期：2026-09-09
- 作者：Lav R. Varshney
- 主题：多足运动 / 粗糙地形 / 接触鲁棒性 / 帧理论 / 信息论
- 摘要：将异构腿—地接触建模为受地形擦除和扰动的有限帧展开系数，并让顺应性形态充当接触门控解码器，以恢复机器人本体层面的运动指令。
- 备注：论文推导了缺失接触下的极小极大最优帧、速率与重建阈值、噪声放大、刚度裕度和增量冗余规则。这是一项基于解析与线性高斯模型的基础理论工作，未报告实体机器人验证。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### hp0303/low-cost-quadruped-platform
- 链接：https://github.com/hp0303/low-cost-quadruped-platform
- 类别：硬件平台 / 机器人描述 / 确定性控制
- 机器人类型：四足机器人 / 自定义 12 自由度平台
- 仿真器：NVIDIA Isaac Sim 5.1
- 部署：提供仿真资产和已组装硬件原型；实机控制验证仍属路线图内容
- 摘要：围绕通用 RC 舵机构建可入门的四足平台，提供完整 STEP 装配、URDF 与网格、关节映射审计、配置文件、Isaac Sim 导入/验证脚本和确定性爬行控制器。
- 备注：创建于 2026-09-11。README 明确区分模型标称值、仿真假设和未验证的硬件限制；BOM、可打印制造文件、校准、IMU 辅助步态和学习控制仍待完成。项目尚未选择许可证，因此源码可见不代表获得复用授权。

### hasankara80/NeuroQuad-RL
- 链接：https://github.com/hasankara80/NeuroQuad-RL
- 类别：强化学习 / 运动控制 / 部署脚手架
- 机器人类型：四足机器人 / 自定义 8 自由度模型
- 仿真器：MuJoCo
- 部署：仿真；含 ONNX 导出和 ROS 2 Humble 推理脚手架，未验证实机迁移
- 摘要：实现紧凑的端到端 PPO 运动原型，包括自定义 Gymnasium 环境、质量和摩擦随机化、确定性评估、检查点、ONNX actor 导出、Docker 打包和 Python ROS 2 推理接口。
- 备注：创建于 2026-09-10。仓库记录了一次早期奖励投机失败及后续终止条件/奖励修正，适合教学检查；但当前没有实机部署证据，检查时 0 星，且未检测到许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Saxion 牵头的执行器动力学课程合作
- 机构：Saxion University of Applied Sciences / University of Groningen / University of Twente
- 主页：https://arxiv.org/abs/2609.09492
- 关键主题：腿足机器人学习 / 执行器建模 / 课程学习 / 仿真到现实 / 动态技能
- 备注：Kousheek Chakraborty、Chandan K. Rajendra、Ayham Alharbat 和 Abeje Y. Mersha 将可行域分析与 Spot 手倒立转换的实机迁移结合起来，是欧洲应用研究中连接执行器辨识与强化学习课程设计的一个值得跟踪的新信号。

### 哈尔滨工业大学轮式人形动作重定向团队
- 机构：哈尔滨工业大学
- 主页：https://arxiv.org/abs/2609.11357
- 关键主题：轮式人形机器人 / 人体动作重定向 / 移动操作 / 微分逆运动学 / Isaac Lab
- 备注：Chenbo Xia 和 Chao Ye 发布了面向 Galaxea R1 Pro 的完整“动作到策略”流程。该工作没有直接套用腿式人形重定向器，而是将轮式底盘与串联躯干视为人体下肢运动的形态感知替代，具有鲜明的平台适配特征。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Humanoid — Controls Team
- 类型：Senior Control Engineer / Research Engineer
- 地点：加拿大不列颠哥伦比亚省 Vancouver / Burnaby；现场办公
- 来源：官方 Ashby 招聘页 — https://jobs.ashbyhq.com/humanoid/80880185-8453-4bcd-9677-9d7c04ac7514
- 截止时间：未知
- 主题：底层控制 / 执行器与关节控制 / ROS 2 / 实时 C++ / EtherCAT 与 CAN / 系统辨识 / 机器人硬件
- 状态：招聘中
- 备注：发布于 2026-09-10。岗位负责面向人形机器人肢体与末端执行器的关节级、执行器级控制器设计与验证，覆盖 PID、前馈、阻抗/导纳、观测器、多自由度建模、传感器集成、安全处理和硬件调试；要求控制/机器人等相关硕博或同等经验，并具备 5 年以上机器人或机电系统经验。检查时官方职位 API 标记为仍在展示。

</details>
