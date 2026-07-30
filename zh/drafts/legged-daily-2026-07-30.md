[English](../../drafts/legged-daily-2026-07-30.md) | **中文**
# 腿足机器人日报 - 2026-07-30

## 摘要
- 今天有 2 篇新论文达到收录标准：一篇聚焦约 300 美元四足机器人极端执行器延迟的真机研究，以及一个把 VLM 动作决策与底层平衡、运动执行解耦的全身具身基准。
- 低成本四足论文是最直接的腿足机器人信号：它把 Mini Pupper 2 实测 76 ms 传输延迟、缺少速度/力矩反馈的问题建模为 POMDP，并比较时序策略与部署端观测重建方案。
- HumanCLAW 在 41 个室内场景的 1,218 个长时程任务中评估闭环全身动作决策；9 个 VLM 中最佳成功率仅 16.8%，显示目标识别之后的具身自我感知仍很薄弱。
- 3 个实现仓库达到收录标准：与论文配套的 Mini Pupper 2 训练/部署栈、带独立 ONNX 导出的 Unitree G1 sim-to-real 对照实验套件，以及 Apache-2.0 的 Genesis/ROCm Go2 运动与性能基准流水线。
- HumanCLAW 构成 Meta、NTU、UW、Brown、Northwestern 的新合作网络信号，但其官方仓库目前仍是项目说明和发布清单，而非可用代码。此前已跟踪的 LAAS-CNRS Gepetto 人形机器人博士职位仍有效，将于明天 2026-07-31 23:59 截止。

<details>
<summary><strong>新论文</strong></summary>

### Reinforcement Learning on Cost-Constrained Quadrupedal Hardware
- 链接：https://arxiv.org/abs/2607.26434
- 来源：arXiv
- 日期：2026-07-29
- 作者：Javier C. Weddington、Bence P. Ölveczky、Stephen A. Baccus
- 主题：四足机器人运动 / 强化学习 / sim-to-real / 执行器延迟 / 部分可观测 / 低成本硬件 / Mini Pupper 2
- 摘要：论文研究约 300 美元的 Mini Pupper 2，其有刷位置舵机存在实测 76 ms 传输延迟，且不提供速度或力矩反馈；作者将部署建模为部分可观测控制问题，并比较前馈、循环网络与工程化观测桥接方案。
- 备注：时间感知 LSTM 学到自维持的节律步态，据报告可承受额外 320 ms 延迟扰动。开源内容包括 Isaac Lab 训练、已训练策略、舵机模型和 Raspberry Pi 部署控制器；论文与仓库均报告了真机行走。

### HumanCLAW: Can Vision-Language Models Act Through a Body?
- 链接：https://arxiv.org/abs/2607.27180
- 来源：arXiv
- 日期：2026-07-29
- 作者：Siyao Li、Jiawei Gu、Shuai Liu、Kairui Hu、Zekun Li、Linjie Li、Chengcheng Tang、Po-Chen Wu、Ivan Shugurov、Lingni Ma、Michael Zollhoefer、Sizhe An、Abhay Mittal、Amy Zhao、Ranjay Krishna、Manling Li、Ziwei Liu、Chuan Guo
- 主题：人形具身 / 视觉语言模型 / 全身技能 / 具身导航 / 基准 / 动作智能
- 摘要：HumanCLAW 把冻结 VLM 输出的原子技能命令转化为包含接触、碰撞和重力后果的连续人体全身动作，同时排除平衡和电机跟踪故障，从而单独评估 VLM 每一时刻的全身动作决策。
- 备注：HumanCLAW-Bench 包含 41 个室内场景中的 1,218 个长时程“寻找—导航—交互”任务。9 个受测 VLM 中最佳成功率为 16.8%；作者把很多目标识别后的失败归因于薄弱的具身自我感知。这项工作更接近人形机器人邻域基准，而非实体机器人运动结果；承诺的代码、基准和权重尚未发布。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### baccuslab/SpotDMouse — P2-Terrain_Challenge
- 链接：https://github.com/baccuslab/SpotDMouse/tree/main/P2-Terrain_Challenge
- 类别：强化学习 / sim-to-real / 部署 / 执行器建模
- 机器人类型：四足；Mini Pupper 2
- 仿真器：NVIDIA Isaac Lab / Isaac Sim
- 部署：同时支持仿真和实体硬件，通过 Raspberry Pi 4 + ESP32 的 Mini Pupper 栈运行
- 摘要：论文 “Reinforcement Learning on Cost-Constrained Quadrupedal Hardware” 的官方实现，包含 Isaac Lab 环境、PPO 配置、已训练 LSTM/MLP 策略、逐关节舵机模型、诊断工具和真机控制器。
- 备注：这是有实质实现的仓库，不是发布占位页。它显式建模有延迟的有刷舵机，包含可复现舵机模型的训练数据与脚本，并链接仿真和真机视频。项目目录于 2026-07-28 推送；核验时未检测到仓库级许可证。

### Theo-guo00/optimus-loco
- 链接：https://github.com/Theo-guo00/optimus-loco
- 类别：强化学习 / 运动控制 / sim-to-real 对照实验 / 部署导出
- 机器人类型：人形；Unitree G1
- 仿真器：NVIDIA Isaac Lab / Isaac Sim，使用 RSL-RL PPO
- 部署：仿真加独立 ONNX/TorchScript 导出；尚未展示实体 G1 部署
- 摘要：一个受控的 G1 运动研究，覆盖四档域随机化、推扰恢复、0–40 ms 动作延迟建模、感知式崎岖地形运动、行走操作和独立 50 Hz 策略推理。
- 备注：仓库包含任务配置、延迟动作代码、训练/评测/导出脚本、原始评测记录、图表和技术说明。README 报告了三随机种子延迟对照实验，以及在单张 RTX 4060 8 GB GPU 上使用 1,024 个环境训练的配置。它是可用研究代码，但当前“可部署”指运行时导出产物，而非已验证的真机迁移；未检测到仓库许可证。

### himanshu748/chaal
- 链接：https://github.com/himanshu748/chaal
- 类别：强化学习 / 运动控制 / 仿真器性能基准 / ROCm 工具
- 机器人类型：四足；Unitree Go2
- 仿真器：Genesis 的 gs.amdgpu 后端，RSL-RL PPO 运行于 ROCm
- 部署：仅仿真
- 摘要：一个 Apache-2.0 的端到端 Go2 速度跟踪流水线，在单张 AMD Radeon GPU 上从零训练物理仿真和 PPO，并提供环境数量扩展测试、评测、原始 benchmark JSON、诊断和渲染工具。
- 备注：README 报告 4,096 个并行机器人、8 分 41 秒完成 4,920 万环境步，以及 0.096 m/s 的基准速度跟踪误差。仓库还记录了两个影响复现的 Genesis 问题：无头环境 OpenGL 配置与接触双方摩擦系数设置。代码内容完整，但未声称 sim-to-real 或实体机器人部署。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### HumanCLAW 合作网络
- 机构：Meta；Nanyang Technological University；University of Washington；Brown University；Northwestern University
- 主页：https://human-claw.github.io/
- arXiv：https://arxiv.org/abs/2607.27180
- GitHub：https://github.com/Human-CLAW/HumanCLAW
- 实验室 / 院系：跨机构具身 AI 与全身动作合作团队
- 关键主题：人形具身 / VLM 动作智能 / 全身技能 / 具身导航 / 物理交互基准
- 备注：该合作团队发布 HumanCLAW 和公开排行榜，在人形动作生成与通用 VLM 决策的交界处形成值得跟踪的新来源网络。后续应关注官方仓库承诺发布的 harness、动作生成器权重、half-physics 仿真器、基准任务和评测工具；截至 2026-07-30，这些产物仍停留在发布清单中。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### LAAS-CNRS Gepetto Team — 人形机器人安全强化学习博士职位
- 类型：PhD
- 地点：法国图卢兹，部分研究将在日本筑波 CNRS-AIST JRL 进行
- 来源：官方网站 — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止时间：2026-07-31 23:59
- 主题：人形机器人 / 腿足运动 / 强化学习 / MPC / 全身控制 / 安全控制
- 状态：active；此前已跟踪机会的截止提醒
- 备注：2026-07-30 再次核验有效。项目为期 36 个月，计划于 2026-10-01 入职，页面列出的月薪为税前 2,300 欧元。课题以 RL 选择离散接触、落脚点、步态和行为决策，再由在线 MPC 生成满足约束的连续全身动作，并计划在 PAL Robotics Kangaroo 和/或 Unitree H1/R1 上验证。这不是新的 master-list 条目，本期因官方截止时间为明天而提醒。

</details>
