[English](../../drafts/legged-daily-2026-10-24.md) | **中文**
# Legged Daily - 2026-10-24

## 摘要
- LocoManiLab（2026-10-22，arXiv）提出覆盖 234 个任务、51.5 小时仿真遥操作数据的人形移动操作统一测试平台；代码和数据仍标注即将开放。
- WholeBodyMem（已投稿 RA-L，尚未接收）利用物体事件驱动的历史记忆解决人形机器人执行任务时关键线索消失的问题，并发布 HuMeGo 数据集线索；作者称数据已放到 Hugging Face，但此次无法独立核验文件可下载性。
- PhysibleMDM（2026-10-21，arXiv）在推理阶段对扩散模型的噪声优化加入运动学及动力学可行性约束，无需重新训练生成器。
- GitHub API 发现新的统一人形动作跟踪评测内核、持续更新的 G1/ACP 实验框架，以及支持上肢扰动解耦控制的 G1 仿真项目。
- Angel Robotics 官方招聘索引仍列出大田的腿足机器人强化学习研究岗；招聘发布于 6 月且详情倒计时显示“D-00”，故仅列为待确认岗位。

<details>
<summary><strong>新论文</strong></summary>

### LocoManiLab: A Unified Testbed for Data, Policies, Controllers, and Deployment in Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.30876
- Source: arXiv 预印本（尚未确认正式会议或期刊接收）
- Date: 2026-10-22
- Authors: Dewei Wang, Jinrui Han, Jiyuan Shi, Chenyun Zhang, Xianbo Lu, Jiabao Wu, Jiqin Feng, Jipeng Kong, Ping Luo, Chenjia Bai, Xuelong Li
- Topics: 人形机器人 / 移动操作 / 数据采集 / 评测基准 / 全身控制 / sim-to-real
- Summary: 统一任务定义、遥操作示范、策略训练、控制器对比和实机部署评测；覆盖五类居家场景的 234 个原子及组合任务、51.5 小时仿真数据，并比较 12 种策略及 5 种全身控制器。
- Notes: 项目 https://locomanilab.github.io/ 于 2026-10-24 核验时将代码与数据均标为“Coming soon”，不能视为已开源。项目页标注 2026-10-23 发布，arXiv 首次提交日期为 2026-10-22。

### Memory before Goal: Role of Pre-History Memory for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.31166
- Source: arXiv 预印本；已投稿 IEEE Robotics and Automation Letters (RA-L)，不等于接收
- Date: 2026-10-22
- Authors: Chenyuan Chen, Ran Ding, Lechen Zhang, Zewen He, Yoshihiko Nakamura
- Topics: 人形机器人 / 视觉语言动作策略 / 物体中心记忆 / 移动操作 / Unitree G1
- Summary: WholeBodyMem 使用 SAM3 跟踪目标物体并按事件选择少量关键历史帧，供策略通过交叉注意力读取，从而应对机器人走动、遮挡后任务线索消失的问题；同时提出含 6 个仿真和 6 个真实 G1 任务的 HuMeGo。
- Notes: 作者报告在其评测设置下，仿真成功率由 29.1% 提升到 72.6%，实机由 36.7% 提升到 88.3%。项目 https://memory-before-goal.github.io/；公开说明仓库 https://github.com/crystalccy1/MemoryBeforeGoal 中“代码和模型”仍为 Coming soon。

### PhysibleMDM: Enforcing Inference-Time Physical Feasibility Constraints on Motion Diffusion Models via Noise Optimization
- Link: https://arxiv.org/abs/2610.30500
- Source: arXiv 预印本（未注明已接收会议或期刊）
- Date: 2026-10-21
- Authors: Maximilian Stölzle, David Müller, Agon Serifi, Ruben Grandia, Espen Knoop, Moritz Bächer
- Topics: 人体/人形动作 / 扩散模型 / 物理可行性 / 逆动力学 / 双足机器人
- Summary: 将地面穿透、滑移、自碰撞和基于锥规划逆动力学的可行性测试引入推理阶段，用 Sep-CMA-ES 优化扩散噪声，无需重训练动作生成模型。
- Notes: 作者在 100 种 SMPL 动作风格上分别报告地面穿透减少 75%、自碰撞穿透减少 92%、滑移减少 74%，另有双足机器人动力学评估；这些是论文报告结果，不代表完成实机验证。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### MotionChallenge-Project/MotionChallenge-Core
- Link: https://github.com/MotionChallenge-Project/MotionChallenge-Core
- Category: benchmark / toolkit / evaluation
- Robot Type: humanoid
- Simulator: MuJoCo 3.17（CPU 批量评测）
- Deploy: sim
- Summary: Apache-2.0 开源的统一人形全动作片段跟踪评测内核与控制器适配接口，记录完成率、首次失败、坐标对齐后的误差、可复算运动轨迹和来源信息。
- Notes: 仓库创建于 2026-10-23，2026-10-24 仍有更新；目前列出 GRIT、SONIC v1.1、HoloMotion v1.4.1、PMT Flat 适配器。权重和数据不随核心仓库分发，评测结论仍需独立复核。

### xia112358/somaforge
- Link: https://github.com/xia112358/somaforge
- Category: toolkit / motion tracking / retargeting / RL
- Robot Type: humanoid（Unitree G1）
- Simulator: Isaac Lab 3.0 / Isaac Sim 6.2 / Newton 1.7
- Deploy: sim
- Summary: 该 G1 实验框架在 2026-10-23 继续更新，整合全身动作跟踪、专家到学生蒸馏、接触感知动作编辑、预测模块，并给出 ACP 单任务复现说明。
- Notes: Apache-2.0；仓库最初创建于 2026 年 7 月，本次为已有仓库的新进展。README 说明统一运行环境、训练输入和 checkpoint 需另行下载；不是 ACP 作者的官方实现。

### yezheng04/unitree-g1-23dof-decoupled-control
- Link: https://github.com/yezheng04/unitree-g1-23dof-decoupled-control
- Category: RL / control / evaluation
- Robot Type: humanoid（Unitree G1 23-DoF）
- Simulator: Isaac Lab 2.3.2 / Isaac Sim 5.1 / PhysX
- Deploy: sim
- Summary: 通过 13 维策略动作控制腿部与腰部偏航，并使用独立轨迹驱动 10 个手臂关节，包含渐进式课程、固定工况评估及公开仿真 checkpoint。
- Notes: 2026-10-22 创建，Apache-2.0；作者明确将其定位为仿真工程实现，尚非经过实机验证的 sim-to-real 成果。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### HuMeGo — 人形机器人物体记忆移动操作基准（待核实候选）
- 链接： https://huggingface.co/collections/ChenyuanC/humego-6ada5cbea74d4cc678c91c68
- 类别： 评测基准 / 实机数据 / 机器人动作
- 对象： Unitree G1（仿真与实机）
- 内容： 6 个仿真任务，每任务 100 条训练示范和 90 个测试场景；6 个实机任务，每任务 15 条示范；考查物体的时间、位置、身份及计数记忆。
- 格式： LeRobot v2.1；作者描述仿真头部相机 50 Hz、实机相机 30 fps
- 获取方式： 作者称公开托管于 Hugging Face；截至 2026-10-24 尚无法独立打开数据页面和核验文件下载
- 许可： CC BY 4.0（作者仓库声明，未能从 Hugging Face 独立核对）
- 摘要： 用于检验人形机器人在移动与操作之前能否保留短暂出现的任务关键线索，其中包含 6 个真实 Unitree G1 任务。
- 备注： 仅列入观察候选，确认数据实际可下载及许可条款后才可加入正式 datasets.md；来源说明：https://github.com/crystalccy1/MemoryBeforeGoal 。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### LocoManiLab 合作网络 — 中国电信 TeleAI 及高校团队
- Institution: 中国电信人工智能研究院（TeleAI）、中国科学技术大学、香港大学、浙江大学、上海交通大学、上海科技大学、Gamma Robotics
- Homepage: https://locomanilab.github.io/
- Lab / Department: LocoManiLab 跨机构作者网络
- Key Topics: 人形机器人 / 移动操作 / 评测基准 / 全身控制 / sim-to-real
- Notes: 项目官网核实各参与机构及 2026-10-23 项目页发布信息；继续跟踪尚未开放的代码、任务数据和基准。

### WholeBodyMem / HuMeGo 作者团队 — MBZUAI
- Institution: Mohamed bin Zayed University of Artificial Intelligence（MBZUAI，机构来自作者公开仓库）
- Homepage: https://memory-before-goal.github.io/
- GitHub: https://github.com/crystalccy1/MemoryBeforeGoal
- Lab / Department: WholeBodyMem 作者合作团队
- Key Topics: 人形机器人 / 物体驱动历史记忆 / VLA / 移动操作 / Unitree G1
- Notes: Chenyuan Chen 等人的新论文 arXiv:2610.31166 已投稿 RA-L，并提出 HuMeGo；关注数据可下载性核验以及代码、模型后续发布。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Angel Robotics — 腿足机器人强化学习 Locomotion 研究员（新发现的已有招聘）
- Type: Research Scientist / Research Engineer（合同制）
- Location: 韩国大田（Daejeon）
- Source: 官方招聘页 — https://www.angel-robotics.com/ko/recruit/notice/51
- Deadline: 长期招聘 / 招满为止（官方在招索引）；具体状态需再次核验
- Topics: 四足 / 双足 / 强化学习 / MPC / WBC / sim-to-real / Isaac Sim / MuJoCo
- Status: watching
- Notes: 该岗位最初发布于 2026-06-16，不是 10 月 24 日新开岗。官方“招聘中”索引仍列出该岗位，但详情显示“D-00”，建议投递前确认是否仍收简历。岗位要求博士学位，涉及地形扰动下的 RL 运动控制、仿真到实机部署与实机验证。

</details>
