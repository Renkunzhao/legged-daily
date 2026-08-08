[English](../../drafts/legged-daily-2026-08-08.md) | **中文**
# Legged Daily - 2026-08-08

## 摘要
- 今天没有新论文达到收录门槛。周六的 arXiv robotics 列表仍止于 2026-08-07 批次，其中最强的腿足与人形论文已经收录在昨天的草稿中。
- 一个新建仓库值得谨慎跟踪：`ROS2-Quadruped-Locomotion-Control` 发布了较完整的 MIT 许可 Unitree Go2 模型控制栈，采用 ROS 2 Jazzy 与 Gazebo Harmonic。
- 该仓库对验证边界说明得较透明：稳定站立与四接触点力矩分配已验证，但重复静态换腿仍在开发，前向行走尚被该里程碑阻塞，真机部署属于未来工作。
- 今天没有选出新的高置信度实验室或教授动态。Amazon Robotics Compass 的官方 Safe Locomotion 岗位仍有效，仍是等待确认加入 master list 的最强已核验机会信号。

<details>
<summary><strong>新论文</strong></summary>

今天没有新论文达到收录门槛。arXiv `cs.RO` 最新批次仍为 2026-08-07，其中入选的腿足与人形论文已经收录在 2026-08-07 草稿中。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### AREIVAN/ROS2-Quadruped-Locomotion-Control
- 链接: https://github.com/AREIVAN/ROS2-Quadruped-Locomotion-Control
- 类别: 控制 / 工具包
- 机器人类型: 四足机器人
- 仿真器: Gazebo Harmonic
- 部署: 仿真
- 摘要: MIT 许可的 ROS 2 Jazzy 四足模型控制框架，以 Unitree Go2 为参考平台，将速度命令依次连接到步态/接触调度、支撑几何、机体力矩控制、接触力分配、支撑腿与摆动腿规划、逆运动学以及 `ros2_control` 关节命令。
- 备注: 创建于 2026-08-07。仓库包含机器人描述、仿真包、控制文档和测试，但明确说明项目尚未完成：稳定站立与四接触点力矩分配已验证，单腿离地仅部分验证，重复静态换腿仍在开发，前向行走受这一里程碑阻塞，真机部署属于未来工作。核验时为 0 star，且没有独立验证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有选出新的高置信度实验室或教授信号。对于已识别的来源网络，如无实质新论文、发布、人员动态或官方公告，本次不重复收录。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型: Senior Applied Scientist
- 地点: 美国加利福尼亚州帕萨迪纳
- 来源: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止时间: rolling / 未知
- 主题: 安全腿足运动 / 强化学习 / 控制屏障函数 / 全身控制 / sim-to-real / 四足机器人 / 人形机器人 / 真机部署
- 状态: 2026-08-08 复核仍有效；已于 2026-07-27 提议，继续等待确认是否加入 master list
- 备注: 该岗位开发并部署真实四足和人形平台上的行走、跑步、爬楼与跌倒恢复强化学习控制器，结合形式化安全机制、sim-to-real 流程和基于模型的全身控制。今天没有新发布且置信度更高的机会超过这一已核验有效信号。

</details>
