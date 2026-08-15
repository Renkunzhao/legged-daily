[English](../../drafts/legged-daily-2026-08-15.md) | **中文**
# 腿足机器人日报 - 2026-08-15

## 摘要
- 在 2026-08-14 之后的检索窗口内，没有筛选出新的高信号腿足机器人论文；运行时对 arXiv `cs.RO` 的 8 月 14-15 日日期查询没有返回新记录。
- 今天有 3 个较值得关注的紧凑型仓库：面向智元 X2 Ultra 的 CPU-only SONIC 全身动作跟踪包、结合 MuJoCo 与 Isaac Lab 两条路线的 Unitree Go2 运动控制栈，以及针对 Go2 冻结运动策略高度扫描输入的对抗基准。
- `go2-mujoco-control` 的可复现性信号最强：同时提供模型控制、Isaac Lab 强化学习、可下载 checkpoint、测试、实验产物和明确的上游/许可证说明。
- 没有发现值得新增的高置信度实验室/教授信号。ETH Zurich RSL 官方页面已重新核验，仍持续开放与腿足机器人相关的滚动制科研和工程岗位。

<details>
<summary><strong>新论文</strong></summary>

今天没有筛选新论文。针对 2026-08-14 至 2026-08-15 提交记录的 arXiv `cs.RO` 定向查询在运行时返回 0 条；更广泛的检索也没有发现时间足够近、与腿足机器人足够直接且通过核验门槛的论文。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### sonic-x2
- 链接：https://github.com/meetsitaram/sonic-x2
- 类别：控制 / 动作跟踪 / 可视化运行器
- 机器人类型：人形机器人 — 智元 AgiBot X2 Ultra，31 自由度
- 仿真器：MuJoCo
- 部署：仿真 / 接近实机部署配置
- 摘要：一个可在 CPU 上直接运行 SONIC 全身动作跟踪策略的 MuJoCo 快速体验包，包含 ONNX 策略、X2 Ultra 模型、行走/站立/舞蹈参考动作、跟踪指标和实机部署调参预设。
- 备注：创建于 2026-08-14。仓库声明策略以 50 Hz 运行，输入为 1670 维观测、输出为 31 维动作；这是社区整理包，未核实为智元官方发布，检查时仓库也未声明顶层许可证。

### go2-mujoco-control
- 链接：https://github.com/kairoi-k/go2-mujoco-control
- 类别：控制 / MPC / 强化学习 / 仿真器
- 机器人类型：四足机器人 — Unitree Go2
- 仿真器：MuJoCo / Isaac Lab
- 部署：仿真
- 摘要：基于 Unitree MuJoCo 的研究分支，将 500 Hz 模型式起立—行走—趴下控制器及对角小跑，与独立的 Isaac Lab 速度强化学习路线放在同一仓库中。
- 备注：包含 Raibert 落足规划、接触力分配、仍在迭代的 18 自由度 ID-WBC + SRBD-MPC 路径、测试、实验产物、RL checkpoint release、复现文档和 BSD-3-Clause 上游许可证说明；仓库未声称已完成硬件部署。

### Go2_heightscan_adversary_retrain
- 链接：https://github.com/JasonSDC/Go2_heightscan_adversary_retrain
- 类别：强化学习 / 鲁棒性基准 / 对抗观测
- 机器人类型：四足机器人 — Unitree Go2
- 仿真器：Isaac Sim / Isaac Lab
- 部署：仿真
- 摘要：一个针对 Go2 冻结运动策略 187 单元地形高度扫描输入进行攻击的可复现实验快照，包含 MLP/LSTM 被攻击策略、对抗策略 checkpoint、评测脚本和跌倒率对比结果。
- 备注：创建于 2026-08-15。当前仓库已经包含攻击与评测资产，但作者明确将“使用对抗样本重新训练被攻击策略”列为下一步，而不是现有完整功能；检查时仓库未声明顶层许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有筛选出新的高置信度实验室或教授信号。新仓库作者公开的机构背景不足以支撑可靠的来源网络新增。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab
- 类型：博士 / 博后 / 研究人员 / 软件工程师 / 机器人设计工程师 / 嵌入式系统工程师 / 电子工程师
- 地点：瑞士苏黎世
- 来源：官方页面 — https://rsl.ethz.ch/the-lab/open-positions.html
- 截止时间：滚动 / 未注明
- 主题：腿足机器人 / 运动规划 / MPC / 强化学习 / 感知 / 导航 / 执行器 / 遥操作 / ROS / C++
- 状态：有效
- 备注：已于 2026-08-15 重新核验。官方页面仍列出滚动制科研和工程岗位，方向覆盖腿足机器人、移动操作、野外部署、控制、学习、规划、感知和机器人硬件。这是对已有跟踪条目的状态更新，不是拟新增的 master-list 条目。

今天没有发现新的高置信度招聘新增项，也没有发现需要提出删除的过期条目。

</details>
