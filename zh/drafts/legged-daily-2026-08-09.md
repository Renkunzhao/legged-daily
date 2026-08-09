[English](../../drafts/legged-daily-2026-08-09.md) | **中文**
# 腿足机器人日报 - 2026-08-09

## 摘要
- 今天没有新论文达到收录门槛。arXiv 官方 `cs.RO` 新提交页面仍停留在 2026-08-07（周五）批次，其中值得收录的腿足/人形论文已在此前草稿覆盖。
- DUET 是今天最强的新发布：这一新公开的 Apache-2.0 Unitree G1 技术栈将下肢行走策略与外部手臂目标解耦，并提供 MuJoCo Warp 训练、消融实验、导出检查点、C++ 真机控制器以及 GR00T N1.7、π0.5 桥接脚本。
- `Livox_MID360_IsaacSim` 是实用的新人形感知仿真资产：面向 Isaac Sim 5.1 提供 MIT 许可的 MID-360 花瓣式/旋转式扫描配置、支持 ROS 2 的 Unitree G1 4010/5010 USD 资产及可复现验证场景。
- 两个仓库都非常新，核验时几乎没有社区验证。今天未选出新的、可确认机构归属的实验室/教授动态；Amazon Robotics Compass 的 Safe Locomotion 官方岗位仍有效，继续等待确认是否加入主列表。

<details>
<summary><strong>新论文</strong></summary>

今天没有新论文达到收录门槛。arXiv 官方 `cs.RO` 新提交页面的最新批次仍为 2026-08-07（周五），其中筛选出的腿足/人形论文已在 2026-08-07 草稿收录。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### bae-air-lab/DUET
- 链接：https://github.com/bae-air-lab/DUET
- 类别：强化学习 / 控制 / 移动操作 / 部署
- 机器人类型：人形
- 仿真器：MuJoCo Warp / mjlab
- 部署：仿真与真机
- 摘要：Apache-2.0 的 Unitree G1 框架，训练一个 13 维动作的下肢策略来跟踪速度、转向和骨盆高度，同时从独立进程接收手臂目标，使单独训练的 VLA 策略无需重训或与行走策略联合协调即可执行操作。
- 备注：2026-08-09 首次公开。仓库包含 DUET 任务、全身基线、消融版本、训练与评测脚本、已部署检查点、带明确部署契约的 ONNX 导出、C++ 真机控制器，以及 GR00T N1.7 和 π0.5 桥接脚本。README 展示了真机演示，但今天未独立核验到对应论文/预印本或机构归属；核验时仓库为 0 star。

### 123tthh/Livox_MID360_IsaacSim
- 链接：https://github.com/123tthh/Livox_MID360_IsaacSim
- 类别：仿真器 / 传感器资产 / 工具包
- 机器人类型：人形
- 仿真器：Isaac Sim 5.1
- 部署：仿真
- 摘要：MIT 许可的 Livox MID-360 仿真与 ROS 2 资产包，分别提供非重复花瓣式和确定性旋转式扫描配置；每种配置都有独立 LiDAR，以及搭载传感器的 Unitree G1 4010、G1 5010 Mode13 和 G1 5010 Mode15 USD 资产。
- 备注：仓库创建于 2026-08-08，并在 2026-08-09 增加了实质性验证。花瓣式配置使用 Livox 官方四秒方向轨迹，通过 ROS 2 发布 20 万点/秒，完整记录安装位姿和外参，并提供可复现的物体场、RViz2 和楼梯场景验证。项目明确不包含行走策略、建图栈或真机部署；核验时为 1 star。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有选出新的高置信度实验室或教授信号。DUET 的技术发布很强，但其 GitHub 所有者未公开可独立核验的机构或实验室归属，因此暂不提升到来源网络部分。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型：高级应用科学家
- 地点：美国加利福尼亚州帕萨迪纳
- 来源：官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止时间：滚动招聘 / 未知
- 主题：安全腿足运动 / 强化学习 / 控制屏障函数 / 全身控制 / sim-to-real / 四足 / 人形 / 真机部署
- 状态：截至 2026-08-09 核验仍有效；最早于 2026-07-27 提议，仍等待确认是否加入主列表
- 备注：岗位负责在真实四足和人形平台上开发与部署行走、奔跑、爬楼梯和跌倒恢复的强化学习控制器，并结合形式化安全机制、sim-to-real 流程和基于模型的全身控制。今天没有发现置信度更高的新岗位信号。

</details>
