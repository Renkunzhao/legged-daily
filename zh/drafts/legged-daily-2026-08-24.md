[English](../../drafts/legged-daily-2026-08-24.md) | **中文**
# 腿足机器人日报 - 2026-08-24

## 摘要
- `DECOWAM` 在全身 world-action model 中解耦相机自运动、腿足底盘运动和机械臂运动；同时引入真机 ARMDOG 数据集，并为每种方法报告 79 次闭环试验。
- 一套分层模仿学习 / 强化学习系统让四足机器人依据视觉选择动态技能，自主腾空穿越狭窄门洞；论文提供真机视频，但今日未核验到代码发布。
- Unitree G1 起身策略通过分阶段微调和显式恢复奖励，把硬地人类示范适配到 MuJoCo 软接触；配套仓库已发布评测代码、训练后策略、参考动作和机器人资产。
- 另有两个实质代码发布达到收录门槛：ETH RSL PACE 系统辨识流程的实验性 mjlab / MuJoCo-Warp 移植版，以及 KAIST DRCD 的 C++ / RaiSim `DC-PBTO` 轨迹优化器。
- 今日未选入新的高置信度、可操作腿足机器人招聘机会；实验室信号来自 KAIST DRCD 的代码发布，以及 IIT Kanpur 新增的人形恢复论文与仓库组合。

<details>
<summary><strong>新论文</strong></summary>

### DECOWAM: Decoupled Whole-Body World-Action Model for Legged Mobile Manipulation
- 链接：https://arxiv.org/abs/2608.20114
- 来源：arXiv
- 日期：2026-08-20；v2 更新于 2026-08-21
- 作者：Siyuan Ma、Boshi Zhang、Yutian Zhang、Qinglian Wu、Jiaqi Zhai、Dong Wei、Qiaojun Yu
- 主题：legged mobile manipulation / world-action model / whole-body coordination / video prediction / robot dataset
- 摘要：通过专用条件通路解耦相机自运动、底盘动作和机械臂动作，以参数高效方式学习 whole-body world-action model，并引入同步视频、全身状态/动作和语言的 ARMDOG 数据集。
- 备注：论文报告使用 25.95M 个可训练适配参数，相比 FastWAM 将动作 MSE 降低 21.7%。每种方法 79 次闭环试验中，DECOWAM 的全身协调与底盘位移鲁棒性表现最佳，同时任务完成率与最强基线相当。今日未核验到官方项目页或代码发布。

### Learning Highly Dynamic Skills Transition for Quadruped Jumping Through Constrained Space
- 链接：[arXiv](https://arxiv.org/abs/2608.19977) · [视频](https://youtu.be/_VexqlQd-t4)
- 来源：arXiv；期刊信息为 Advanced Robotics Research (2025)
- 日期：2026-08-20
- 作者：Zeren Luo、Jiahui Zhang、Yimin Han、Ji Ma、Minghao Lu、Ioannis Havoutis、Peng Lu
- 主题：quadruped / dynamic locomotion / hierarchical reinforcement learning / imitation learning / vision / obstacle traversal
- 摘要：通过模仿学习训练动物启发的底层技能库，再由视觉条件高层控制器根据技能能力选择无碰撞转换，实现自主腾空穿越狭窄门洞。
- 备注：作者将其定位为地面行走机器人较早的自主敏捷门洞穿越工作之一，并报告框架可扩展到其他动态任务。论文源文件链接了真机视频；今日未核验到官方代码仓库。

### Demonstration-Guided Humanoid Stand-Up on an Emulated Deformable Surface
- 链接：[arXiv](https://arxiv.org/abs/2608.20852) · [代码](https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid) · [视频](https://youtu.be/c04fnMCDdd8)
- 来源：arXiv / 官方代码仓库
- 日期：2026-08-21
- 作者：Aniruddh Kushwah、Vyankatesh Ashtekar、Ashish Dutta
- 主题：humanoid / Unitree G1 / stand-up recovery / reinforcement learning / deformable terrain / reference tracking
- 摘要：结合残差关节位置控制、参考动作跟踪和显式恢复目标，将硬地人类起身示范适配到 MuJoCo 模拟的柔顺接触模型。
- 备注：仿真策略达到目标直立姿态，最大接触穿透约 40 mm；消融表明仅做参考跟踪不足以完成恢复。发布版是确定性、纯仿真的评测，地面也只是软接触近似，并非完整可变形材料模型。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### fan-ziqi/pace-sim2real-mjlab
- 链接：https://github.com/fan-ziqi/pace-sim2real-mjlab
- 类别：sim-to-real / system identification / toolkit
- 机器人类型：quadruped — 内置 ANYmal-D 流程，并为其他机器人和执行器提供扩展点
- 仿真器：mjlab / MuJoCo-Warp
- 部署：在仿真中拟合真实激励数据，目标是提升后续真机策略迁移质量
- 摘要：把 ETH RSL 的 PACE 执行器/关节动力学辨识流程从 Isaac Lab 移植到 mjlab，同时尽量保持任务 ID、包导入、数据产物、CMA-ES 日志和 runner 接口兼容。
- 备注：创建于 2026-08-24，维护者明确标记为实验项目。可估计 armature、阻尼、库仑摩擦、编码器偏差和指令延迟；仓库含静态/API 测试及集成测试，但大规模有效拟合仍以 GPU 为主。README 声明 Apache-2.0，而核验时 GitHub API 将许可证分类为非标准类型。

### DrcdKAIST/DC-PBTO
- 链接：https://github.com/DrcdKAIST/DC-PBTO
- 类别：trajectory optimization / control / toolkit
- 机器人类型：quadruped — 内置 Hound 配置
- 仿真器：RaiSim；MATLAB 生成解析动力学；C++ 在线求解器
- 部署：仿真 / 轨迹生成
- 摘要：发布基于相位的 C++ 轨迹优化器，使用降阶刚体模型、Bezier 参数化和 SQP，联合优化机身运动、足端轨迹、接触力与相位时长。
- 备注：由 KAIST Dynamic Robot Control and Design Lab 于 2026-08-20 创建，采用 MIT 许可；支持多类解析地形并固定 qpSWIFT 版本，但依赖 RaiSim，缺少已生成接触力库时还需要 MATLAB、Symbolic Math Toolbox 与 MATLAB Coder。

### andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- 链接：https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- 类别：reinforcement learning / evaluation / dataset
- 机器人类型：humanoid — Unitree G1
- 仿真器：MuJoCo
- 部署：仿真评测
- 摘要：为柔顺地面跌倒起身恢复提供评测代码、训练后 PPO 策略、归一化统计、重定向人类参考动作、Unitree G1 XML/资产和媒体文件。
- 备注：MIT 许可，创建于 2026-07-14，相关论文于 2026-08-21 提交。当前发布用于复现确定性评测而非完整训练课程；大型资产可能需要 Git LFS，MuJoCo passive viewer 需要图形桌面和 OpenGL 环境。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Hae-Won Park / Dynamic Robot Control and Design Lab
- 机构：Korea Advanced Institute of Science and Technology (KAIST)
- 主页：https://drcd.kaist.ac.kr/
- GitHub：https://github.com/DrcdKAIST
- 实验室 / 院系：Dynamic Robot Control and Design Lab
- 关键主题：quadruped / trajectory optimization / dynamics / control / locomotion
- 备注：这个已追踪实验室于 2026-08-20 发布 `DC-PBTO`：一套与其接触点分解动态一致轨迹优化 RA-L 论文配套的、采用 MIT 许可的实质 C++ / RaiSim 实现。

### Ashish Dutta / IIT Kanpur Mechanical Engineering
- 机构：Indian Institute of Technology Kanpur
- arXiv：https://arxiv.org/abs/2608.20852
- GitHub：https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- 实验室 / 院系：Department of Mechanical Engineering
- 关键主题：humanoid / stand-up recovery / reinforcement learning / compliant contact / motion retargeting
- 备注：新增 Unitree G1 起身论文与评测仓库构成了值得追踪的接触丰富型人形恢复信号。当前证据仅限仿真，但已发布策略和评测资产，而非只有论文描述。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日未选入新的高置信度、可操作腿足机器人招聘机会。本草稿也没有新增拟删除/过期条目。

</details>
