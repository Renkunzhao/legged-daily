[English](../../drafts/legged-daily-2026-08-30.md) | **中文**
# 腿足机器人日报 - 2026-08-30

## 摘要
- 今日未选入新论文。本轮运行时间为周日，未发现同时满足时效性和来源核验要求、且比 2026-08-28 草稿更新的论文。
- `GRIT v0.0.1` 是今日最强发布：一个采用 MIT 许可的 Unitree G1 全身动作跟踪栈，包含 ONNX 策略、MuJoCo sim2sim、PICO 遥操作和原生 Unitree SDK2 bridge。
- `Sprite` 同时开放 31 个驱动关节的人形仿真描述和配套 FreeCAD 硬件源文件，许可证清晰，但尚未提供完整控制器，也未宣称已具备 sim-to-real 条件。
- `go2-pace-sim2real` 发布覆盖 PACE 风格系统辨识、教师—学生行走训练、ONNX 验证、只读 Shadow 模式和 Go2 控制框架的 Isaac Lab 工作流；仓库很新，暂无许可证，且未发布原始辨识数据与策略权重。
- BeijingDynamics 是值得继续观察的新组织级开源人形硬件与运动资产信号。此前追踪的 Inria Auctus / LAAS-CNRS 四足协同设计博士职位仍开放，但将于明日 2026-08-31 截止。

<details>
<summary><strong>新论文</strong></summary>

今日没有论文达到收录标准。本轮为周日运行，未核验到比 2026-08-28 草稿已收录条目更新的腿足机器人论文。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### mrzuang/GRIT_teleop_deploy
- 链接：https://github.com/mrzuang/GRIT_teleop_deploy
- 类别：control / retargeting / teleoperation / toolkit
- 机器人类型：humanoid — Unitree G1
- 仿真器：MuJoCo
- 部署：仿真与硬件
- 摘要：以 GRIT v0.0.1 形式发布全身动作跟踪部署栈，包含 ONNX 策略契约、50 Hz Python runtime、PICO/XRoboToolkit 重定向、MuJoCo sim2sim 和原生 Unitree SDK2 硬件 bridge。
- 备注：仓库创建于 2026-08-29，采用 MIT 许可，包含模型/接口检查、示例动作、部署测试、明确的真机安全警告和陈旧指令 watchdog，但不包含训练与数据生成代码。配套 beta 策略据维护者说明只使用 10 多小时开源数据训练；README 中 9 月和 10 月的发布内容目前仍只是维护者路线图，并非已核验交付物。

### BeijingDynamics/open_sprite
- 链接：https://github.com/BeijingDynamics/open_sprite
- 类别：robot description / simulator asset / open hardware
- 机器人类型：humanoid — Sprite0825，约 0.95 米、31 个驱动关节
- 仿真器：MuJoCo / Isaac Lab 兼容 URDF
- 部署：仿真 / 硬件设计数据
- 摘要：发布 Sprite 人形机器人的网格、经过清理的训练 URDF、已验证可加载的 MuJoCo 可视化模型与 floating-base external-PD 模型，以及复现元数据；另有官方配套 FreeCAD 硬件源文件仓库。
- 备注：仓库创建于 2026-08-28，采用 AGPL-3.0；配套的 [FreeCAD 源文件仓库](https://github.com/BeijingDynamics/sprite_humanoid_freecad) 采用 CERN-OHL-S-2.0。发布方明确说明这不是完整机器人控制器，缺少硬件通信、状态估计、电流限制、急停和联锁；研究 checkpoint 未公开，也未被描述为已具备 sim-to-real 条件。

### godhandcrash/go2-pace-sim2real
- 链接：https://github.com/godhandcrash/go2-pace-sim2real
- 类别：reinforcement learning / system identification / sim-to-real / toolkit
- 机器人类型：quadruped — Unitree Go2
- 仿真器：Isaac Lab
- 部署：仿真与硬件
- 摘要：集成 PACE 风格 49 参数系统辨识、课程与域随机化 PPO 训练、对称增强、教师—学生蒸馏、递归 ONNX 验证、只读真机 Shadow 日志，以及 C++ Go2 控制器框架。
- 备注：仓库创建于 2026-08-29。README 报告已完成仿真和 Go2 部署验证，同时要求分阶段检查和独立物理急停。原始真机辨识数据、CMA-ES checkpoint 和训练后策略权重没有公开，核验时 GitHub 也未检测到仓库级许可证；因此结果与硬件声明在独立复现前应视为维护者自述。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### BeijingDynamics
- 机构：独立 GitHub 组织；未公开说明所属机构
- GitHub：https://github.com/BeijingDynamics
- 实验室 / 院系：未公开说明
- 关键主题：humanoid / open hardware / robot description / MuJoCo / locomotion assets
- 备注：该组织于 2026-08-28 出现，并协调发布两项 Sprite 资产：采用 AGPL-3.0 的仿真/描述资产，以及采用 CERN-OHL-S-2.0 的 FreeCAD 硬件源文件。核验时未显示公开成员或外部机构主页，因此组织身份仍未核实；但其资产级许可证和明确的验证边界使其值得作为后续观察源。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- 类型：博士
- 地点：法国 Talence / Bordeaux，计划赴 Toulouse 交流
- 来源：[Inria 官方职位页](https://jobs.inria.fr/public/classic/en/offres/2026-10319)
- 截止时间：2026-08-31；计划开始时间 2026-10-01
- 主题：quadruped / mechatronic co-design / local compliance / loco-manipulation / reinforcement learning / real-to-sim calibration / prototyping
- 状态：开放中 — 明日截止
- 备注：这是对 2026-08-28 已提示机会的状态更新。今日官方页面仍可访问，继续列出 2026-08-31 截止日期和税前月薪 2,300 欧元。项目联合研究新型四足机器人的架构、驱动、柔顺分布与控制，实验目标包括户外高速奔跑和接取飞行物。

</details>
