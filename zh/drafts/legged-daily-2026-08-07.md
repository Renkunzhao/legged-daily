[English](../../drafts/legged-daily-2026-08-07.md) | **中文**
# Legged Daily - 2026-08-07

## 摘要
- 今天有 3 篇 arXiv 新论文达到收录门槛：ω-0 将视觉预测与全身动作生成统一用于人形机器人边移动边操作；TRACE 面向接触不可靠条件下的本体感知里程计；KILVO 则融合运动学、IMU、LiDAR 和视觉，实现具备传感器故障韧性的人形状态估计。
- ω-0 是最强的全身学习信号：官方页面报告单一策略覆盖 11 项家庭任务、真机成功率 81.8%，并发布一个包含 40.3 小时、4,827 个 episode 的多模态人形数据集；但今天未核验到代码或公开数据下载。
- KILVO 论文称代码与数据集已经发布，但其链接的 GitHub 仓库仍只有 209 字节占位 README，写明“即将开放”；因此收录论文，但不把该仓库计为可用发布。
- IIT DLSLab 的四足自主起身栈获得实质部署更新；另一个新 H1 Isaac Lab 仓库公开了较详细的评测与消融结果，但后者是独立、无许可证且尚无真机验证的发布。
- NTU MARS Lab 借 ω-0 将具身智能研究推进到真实人形并发移动操作，值得提升跟踪优先级。Amazon Robotics Compass 的官方 Safe Locomotion 岗位仍有效。

<details>
<summary><strong>新论文</strong></summary>

### ω-0: A Latent Predictive World Action Model for Concurrent Humanoid Loco-Manipulation
- 链接: https://arxiv.org/abs/2608.06375
- 来源: arXiv / 官方项目页
- 日期: 2026-08-07
- 作者: Zhe Li, Zhenzhe Zhang, Yangyang Wei, Wenjie Zhang, Xichen Yuan, Peiyuan Zhi, Gen Li, Xinying Guo, Fengjie Gao, Jianfei Yang, Shanghang Zhang
- 主题: 人形机器人 / 并发移动操作 / world-action model / 视觉-语言-动作学习 / 扩散策略 / 全身控制 / 真机数据集
- 摘要: ω-0 以语言、视觉观测和本体状态为条件，同时预测紧凑的未来视觉表征与可由控制器执行的全身动作潜变量，使单一策略能在家庭操作过程中协调行走、姿态、平衡、双臂和双手。
- 备注: 官方页面报告在 11 项真机任务上达到 81.8% 成功率和 90.3% 任务进度，并介绍 ω-HOME：40.3 小时、24 类任务、4,827 个 episode、6 种同步模态。这些仍是作者报告的预印本结果；今天未核验到代码或可下载数据。项目页: https://gentlefress.github.io/OMEGA-0_page/

### Learned Proprioceptive Odometry for Legged Robots under Unreliable Contact Conditions
- 链接: https://arxiv.org/abs/2608.05975
- 来源: arXiv
- 日期: 2026-08-07
- 作者: Taehyeon Kong, Woojin Kim, Jemin Hwangbo
- 主题: 腿足机器人 / 本体感知里程计 / 接触感知估计 / 注意力 / sim-to-real / 传感器融合
- 摘要: TRACE 从 IMU 与关节历史直接预测相对位姿和机体系速度，通过足端感知交叉注意力自适应融合惯性与逐腿运动学 token，无需人工设置接触或打滑阈值。
- 备注: 方法加入运动学一致性辅助损失、仿真中的策略随机化和部分真机微调。作者报告在接触不可靠的室内外地形上，相比滤波、混合和学习基线具有更低的位置漂移；今天未核验到公开代码，论文已投稿 RA-L。

### Kinematic-Inertial-LiDAR-Visual Odometry with Robust Multimodal Adaptation for Humanoid Robots
- 链接: https://arxiv.org/abs/2608.05647
- 来源: arXiv / IEEE/ASME Transactions on Mechatronics
- 日期: 2026-08-07
- 作者: Jixin Gao, Fucheng Liu, Teng Zhang, Fusheng Zha
- 主题: 人形机器人 / 状态估计 / 里程计 / 传感器融合 / 接触估计 / LiDAR / 视觉 / 传感器故障鲁棒性
- 摘要: KILVO 在混合误差状态迭代卡尔曼滤波器中整合 IMU 预测、高频异步腿部运动学约束、依次进行的 LiDAR 与视觉更新，以及紧凑接触估计，面向人形机器人常用传感器和模态退化场景设计。
- 备注: 论文报告了公开数据集和多款真实人形机器人的实验，并已被 IEEE/ASME Transactions on Mechatronics 接收。尽管摘要称代码与数据已发布，链接仓库目前仍只有“即将开放”的占位内容: https://github.com/JixinGao/KILVO

</details>

<details>
<summary><strong>新仓库</strong></summary>

### iit-DLSLab/get-up-isaaclab
- 链接: https://github.com/iit-DLSLab/get-up-isaaclab
- 类别: 强化学习 / 控制 / 部署
- 机器人类型: 四足机器人
- 仿真器: Isaac Lab / MuJoCo
- 部署: 仿真与真机
- 摘要: BSD-3-Clause 许可的 Unitree Go2 四足自主起身实现，包含 Isaac Lab 与 RSL-RL 训练、Rapid Motor Adaptation、参数辨识、MuJoCo sim-to-sim 评测以及 ROS 2 真机部署。
- 备注: 2026-08-07 更新加入 Pegasus 策略和部署修复，承接 8 月 6 日新增的 PD 随机化比例与质心偏移事件。README 对应 Isaac Lab 2.3.2、RSL-RL 3.3.0 和 MuJoCo 3.7.0，并展示训练、sim-to-sim 与 sim-to-real 效果。

### HaoZiOwO/rl-h1-locomotion
- 链接: https://github.com/HaoZiOwO/rl-h1-locomotion
- 类别: 强化学习 / 评测 / 工具包
- 机器人类型: 人形机器人
- 仿真器: Isaac Lab / MuJoCo
- 部署: 仿真
- 摘要: 新发布的 Unitree H1 速度跟踪实验项目，基于 Isaac Lab 与 RSL-RL，覆盖平地和崎岖地形训练、负载测试、奖励消融、多随机种子评测、检查点分析以及 PPO/BC/SAC 样本效率对比。
- 备注: 创建于 2026-08-07。README 提供详细数值结果、复现命令，并记录 Isaac Sim 5.1 渲染故障；但核验时仓库无许可证、无 star、无真机部署证据，应将其视为独立实验产物，而非已验证的参考实现。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### MARS Lab — Nanyang Technological University
- 机构: 新加坡南洋理工大学
- 主页: https://marslab.tech/
- arXiv: https://arxiv.org/abs/2608.06375
- 实验室 / 部门: Multimodal embodied AI and Robotic Systems Lab
- 关键主题: 人形机器人 / 移动操作 / 世界模型 / 多模态具身智能 / 机器人学习 / 真机部署
- 备注: ω-0 显著增强了这一已跟踪来源：实验室把多模态具身智能推进到统一的真实人形 world-action model、40.3 小时家庭数据集和 11 项任务部署。后续重点跟踪官方项目页的代码、ω-HOME 下载入口和独立评测细节。
- 学生及代表工作:
  - [Zhe Li 等](https://arxiv.org/abs/2608.06375) — [ω-0: A Latent Predictive World Action Model for Concurrent Humanoid Loco-Manipulation](https://gentlefress.github.io/OMEGA-0_page/)

### Jemin Hwangbo 及合作者 — KAIST
- 机构: 韩国科学技术院
- arXiv: https://arxiv.org/abs/2608.05975
- 实验室 / 部门: 腿足机器人学习与状态估计合作网络
- 关键主题: 腿足机器人 / 学习式状态估计 / 本体感知里程计 / 接触鲁棒性 / sim-to-real
- 备注: TRACE 为已有 KAIST / Jemin Hwangbo 来源网络新增状态估计方向：将学习式注意力、物理启发一致性损失、策略随机化仿真和部分真机微调结合，用于接触退化条件下的腿足里程计。
- 学生及代表工作:
  - [Taehyeon Kong 等](https://arxiv.org/abs/2608.05975) — [Learned Proprioceptive Odometry for Legged Robots under Unreliable Contact Conditions](https://arxiv.org/abs/2608.05975)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型: Senior Applied Scientist
- 地点: 美国加利福尼亚州帕萨迪纳
- 来源: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止时间: rolling / 未知
- 主题: 安全腿足运动 / 强化学习 / 控制屏障函数 / 全身控制 / sim-to-real / 四足机器人 / 人形机器人 / 真机部署
- 状态: 2026-08-07 复核仍有效；已于 2026-07-27 提议，继续等待确认是否加入 master list
- 备注: 该岗位开发并部署真实四足和人形平台上的行走、跑步、爬楼与跌倒恢复强化学习控制器，结合形式化安全机制、sim-to-real 和基于模型的全身控制。今天没有置信度更高的新发布机会超过这一有效信号。

</details>
