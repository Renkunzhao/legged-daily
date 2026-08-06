[English](../../drafts/legged-daily-2026-08-06.md) | **中文**
# Legged Daily - 2026-08-06

## 摘要
- 2 篇近期论文新达到收录门槛：LightParkour 用单一可部署深度策略统一感知运动与接触丰富的人形跑酷，FDDC 则提出可由机载观测计算的动态质心状态和可复现的单腿平衡基准。
- FDDC 是今天最强的可复现性信号：新发布的 Apache-2.0 仓库包含训练与评测代码、适配 8 个已发布策略的跨仿真器基准、数据、训练后策略、Unitree G1 资产和真机部署说明。
- EngineAI 发布官方 MIT 许可 GMR 适配，面向 PM01 与 T800，支持 BVH、SMPL-X、AMASS 和 OMOMO 工作流，并提供 MuJoCo 可视化及标准 GMR 轨迹格式导出。
- 对 2026-08-06 的 cs.RO / cs.LG arXiv 新投稿筛选后，没有条目明确超过相关性门槛；下列 2 篇是 8 月 1—3 日发布、此前日报草稿尚未收录的高信号近期工作。
- Light Origins 是值得新增跟踪的真机人形学习来源。Amazon Robotics Compass 的 Safe Locomotion 岗位在官方招聘页仍有效。

<details>
<summary><strong>新论文</strong></summary>

### Growing Humanoid Parkour Skills through Real2Sim2Real
- 链接: https://light-loco-parkour.github.io/
- 来源: 官方项目页 / 论文 PDF
- 日期: 2026-08-03
- 作者: Hongming Chen, Zhuoran Li, Hongxi Wang, Jiangpeng Hu, Ziliang Li, Peize Liu, QingRui Zhao, Xuhao Liu, Liang Pan, Ximin Lyu, Yuntao Ma, Tingxiang Fan
- 主题: 人形跑酷 / 感知运动 / 全身控制 / 技能蒸馏 / real-to-sim-to-real / 深度策略
- 摘要: LightParkour 将短人类动作片段在物理环境中落地，把每个种子技能扩展到不同地形变化，再将普通运动与接触丰富的全身跑酷蒸馏为一个由机载深度感知驱动的可部署策略。
- 备注: 官方页面报告同一策略可在 Lightbot 0 上执行普通运动和跑酷，并展示攀爬、跳跃、翻越及障碍通过等真机行为。目前证据来自作者项目页与论文 PDF；今天未核验到 arXiv 记录，新建的第三方 GitHub 实现也只有极简占位内容，尚非可用发布。

### First Deployable Dynamic-CoM: A Unified Policy and Method-Agnostic Benchmark for Humanoid Single-Leg Balance
- 链接: https://arxiv.org/abs/2608.00500
- 来源: arXiv
- 日期: 2026-08-01
- 作者: Yikai Zhou, Xingyun Wang, Jieming Cui, Bozhou Chen, Yikai Fan, Yixin Zhu, Wenxin Li
- 主题: 人形平衡 / 动态质心 / 捕获点 / 强化学习 / sim-to-sim 基准 / sim-to-real / Unitree G1
- 摘要: FDDC 利用编码器和 IMU 重建相对支撑脚的动态质心观测，无需机载系统难以直接提供的基座线速度，再结合源自人体姿态控制的奖励训练可部署到硬件的单腿平衡策略。
- 备注: 作者报告该策略在 9 类姿态的 90 个留出动作中实现 86 个干净单腿平衡，并迁移到真实 Unitree G1；8 个已发布通用策略在该基准的严格标准下均为 0/90。结果仍是作者报告的预印本结论，但完整基准与策略栈已于 2026-08-06 发布。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### FDDC
- 链接: https://github.com/zhouyikai888/FDDC
- 类别: 强化学习 / 基准 / 数据集 / 部署
- 机器人类型: 人形
- 仿真器: MuJoCo，并使用不同环境进行 sim-to-sim 评测
- 部署: 仿真与真机
- 摘要: First Deployable Dynamic-CoM 的官方 Apache-2.0 实现，包含训练和评测代码、与方法无关的单腿平衡基准、8 个已发布人形策略适配器、分层动作数据、训练后策略、Unitree G1 资产及真机部署支持。
- 备注: 创建于 2026-08-06。这是内容完整的发布，而非只有论文链接的空仓库；其基准分数和真机性能仍需独立复现。

### EngineAI GMR
- 链接: https://github.com/engineai-robotics/GMR
- 类别: 动作重定向 / 工具包 / 可视化器
- 机器人类型: 人形
- 仿真器: MuJoCo
- 部署: 数据 / 仿真
- 摘要: EngineAI 官方发布的 MIT 许可 General Motion Retargeting 适配，可将 BVH 和 SMPL-X 系人类动作转换为 PM01、T800 人形机器人轨迹，并提供 MuJoCo 可视化与标准 GMR PKL 导出。
- 备注: 创建于 2026-08-05。支持 LAFAN1 BVH、SMPL-X、AMASS 和 OMOMO 工作流，并包含两款机器人模型资产；SMPL-X 人体模型及部分动作数据集需按各自许可单独下载。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Light Origins Robotics Team
- 机构: Light Origins
- 主页: https://light-loco-parkour.github.io/
- YouTube: https://youtu.be/96Rfm7OmHjY
- 实验室 / 部门: Robotics team
- 关键主题: 人形跑酷 / 感知运动 / 全身控制 / 动作学习 / 技能蒸馏 / real-to-sim-to-real
- 备注: LightParkour 是一个很强的新真机信号：团队展示了在 Lightbot 0 人形机器人上统一普通运动和接触丰富跑酷的机载深度策略。后续重点跟踪公开论文索引、官方代码和技术报告；今天发现的唯一 GitHub 实现来自第三方且尚不完整。
- 学生及代表工作:
  - [Hongming Chen 等](https://light-loco-parkour.github.io/) — [Growing Humanoid Parkour Skills through Real2Sim2Real](https://light-loco-parkour.github.io/)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型: Senior Applied Scientist
- 地点: 美国加利福尼亚州帕萨迪纳
- 来源: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止时间: rolling / 未知
- 主题: 安全腿足运动 / 强化学习 / 控制屏障函数 / 全身控制 / sim-to-real / 四足机器人 / 人形机器人 / 真机部署
- 状态: 2026-08-06 复核仍有效；已于 2026-07-27 提议，继续等待确认是否加入 master list
- 备注: 该岗位负责在真实四足和人形平台上开发步行、跑步、爬楼和跌倒恢复学习控制器，明确结合强化学习、sim-to-real、形式化安全机制与基于模型的全身控制；今天官方页面仍可访问。

</details>
