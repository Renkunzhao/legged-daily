[English](../../drafts/legged-daily-2026-09-11.md) | **中文**
# 腿足机器人日报 - 2026-09-11

## 摘要
- CAP 训练单一 Unitree G1 运动策略，在深度信息正常、受污染、部分遮挡乃至缺失时连续适应，而不是在人形感知控制器与盲行控制器之间硬切换。
- Harness Robotic OS 展示了一个已部署的具身智能体运行时，将四足机器人感知与导航、巡检推理、语音交互、告警和企业结构化报告连成闭环。
- IIT Dynamic Legged Systems 团队研究四足机器人通过被动机械接口负载运输时，步态、负载、刚度与阻尼之间的耦合关系。
- 仓库信号包括 CAP 官方项目占位仓库、面向 IROS 2026 的折纸启发人形机器人描述资产，以及当天实质更新的 Unitree Go2 多后端仿真与运动控制栈。
- 今日检查的官方来源中，未筛选到信息足够具体、置信度高的新腿足机器人招聘岗位。

<details>
<summary><strong>新论文</strong></summary>

### CAP: Continuously Adaptive Perception-Blind Humanoid Locomotion via Learned Denoising
- 链接：https://arxiv.org/abs/2609.11553
- 来源：arXiv / CoRL 2026
- 日期：2026-09-10
- 作者：Hongjin Chen、Zijun Xu、Shihao Ma、Yi Zhao、Xilai Liu、Ke Ma、Wei Zhang、Chunyang Xie、Pengfei Li、Jieru Zhao、Wenchao Ding
- 主题：人形运动 / 感知式运动 / 学习去噪 / 传感器失效 / 仿真到现实
- 摘要：通过去噪式感知世界模型、并行工作的本体感知编码器、深度噪声课程和特征丢弃训练单一运动策略，使控制性能随深度质量恶化而平滑退化，并在 Unitree G1 上验证遮挡、传感器污染和室外深度伪影条件下的鲁棒运动。
- 备注：[项目主页](https://hoshi-no-ai.github.io/CAP/)。项目报告在正常或部分遮挡感知条件下的受控实验中成功 39/40 次；完全遮住相机时，沟槽和平台等需要前视深度的地形仍是局限。

### Harness Robotic OS: A Unified Embodied-Agent Runtime for Closed-Loop Quadruped Inspection
- 链接：https://arxiv.org/abs/2609.11225
- 来源：arXiv
- 日期：2026-09-10
- 作者：Yaoyuan Yan、Zhiyou Heng、Haoxiang Jie、Gang Liu、Hongjie Yan、Wei Zhou
- 主题：四足巡检 / 具身智能体 / 自主系统栈 / 多模态感知 / 人机交互
- 摘要：提出 HROS 及其 Argos 部署，将机器人运行时、自主技能、认知智能体的上下文与记忆、语音交互和带安全门控的改进机制，统一为可追踪的住宅社区巡检闭环。
- 备注：原型集成 Vbot 四足机器人、Fast-LIO2、Hobot-Stereo、PCT-Planner、EGO-Planner，以及由 OpenClaw 编排的 Qwen3-VL 巡检分析。论文报告 100% 航点到达率和 99% 告警/报告成功率；这些是作者报告的部署结果，本次未独立复现。

### Gait-Dependent Effects on Quadruped Locomotion for Load-Carrying using Passive Mechanism
- 链接：https://arxiv.org/abs/2609.11059
- 来源：arXiv
- 日期：2026-09-10
- 作者：Giovanni B. Dessy、Claudio Semini、Victor Barasuol
- 主题：四足运动 / 负载运输 / 被动机构 / 步态分析 / 稳定性
- 摘要：研究不同步态和负载条件下被动臂的刚度与阻尼选择，结果表明欠阻尼配置会增加被动关节振荡，并可能缩小爬行步态的 ZMP 裕度；小跑步态仅作为动态激励工况，不用于直接比较 ZMP 稳定裕度。
- 备注：论文用“步态—负载—刚度—阻尼”图总结设计空间；当前证据来自平地仿真分析，尚非实机验证。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Hoshi-No-Ai/CAP
- 链接：https://github.com/Hoshi-No-Ai/CAP
- 类别：项目主页 / 待发布运动控制代码
- 机器人类型：人形机器人 / Unitree G1
- 仿真器：尚未发布
- 部署：已提供实机演示资料，代码待发布
- 摘要：CAP 的官方配套仓库，汇集论文、项目网站和视频，展示一个能随深度感知质量变化而连续适应的鲁棒人形运动策略。
- 备注：创建于 2026-09-11。README 明确说明训练与部署代码仍在准备中；当前 `main` 分支只是后续代码发布的占位，不能视为可用的代码开源。

### sattwik-sahu/iros2026-origami-robot
- 链接：https://github.com/sattwik-sahu/iros2026-origami-robot
- 类别：机器人描述 / 仿真资产
- 机器人类型：折纸启发人形机器人
- 仿真器：RViz / Gazebo Sim / NVIDIA Isaac Sim
- 部署：仿真与可视化资产
- 摘要：发布 NORTH POC2.2 人形平台的 URDF、超过 100 个连杆与 118 个 STL 网格、USD/PhysX 资产、ROS 2 Jazzy 启动文件和 Docker 工作流，作为 IROS 2026 投稿的配套材料。
- 备注：创建于 2026-09-10，检查时 0 星。这是机器人描述与可视化/仿真包，不是已发布的运动控制器或经过验证的仿真到现实栈；GitHub API 未检测到标准 SPDX 许可证。

### darshmenon/quadruped-robotics-stack
- 链接：https://github.com/darshmenon/quadruped-robotics-stack
- 类别：运动控制 / 强化学习 / 经典控制 / 自主系统栈
- 机器人类型：四足机器人 / Unitree Go2
- 仿真器：MuJoCo / Gazebo Harmonic / Isaac 训练路径
- 部署：仿真；未核验实机部署
- 摘要：在一个以 Go2 为中心的工作区内组合 PPO 运动控制、CHAMP、Quad-SDK NMPC、ROS 2、地形世界、SLAM/导航演示、恢复策略训练和预训练策略接入流程。
- 备注：2026-09-11 更新，新增仅腿部 MuJoCo 模式，旨在让检查点维度与 Gazebo 环境对齐。README 区分了可工作的 Go2 路径和占位配置，并记录多个已知训练问题；检查时 18 星，未检测到仓库许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### CAP 合作网络
- 机构：复旦大学 / TARS Robotics / 上海创新研究院 / 哈尔滨工业大学 / 上海交通大学
- 主页：https://hoshi-no-ai.github.io/CAP/
- GitHub：https://github.com/Hoshi-No-Ai/CAP
- 关键主题：人形运动 / 感知鲁棒性 / 学习式世界模型 / 仿真到现实
- 备注：CoRL 2026 CAP 项目是一个围绕 Unitree G1 感知鲁棒运动的新多机构信号，通过具体论文、项目主页、实机视频和计划发布的代码，将复旦与 TARS Robotics、上海创新研究院、哈工大和上交连接起来。

### Dynamic Legged Systems Lab / IIT
- 机构：意大利理工学院（Istituto Italiano di Tecnologia）
- 主页：https://dls.iit.it/
- 实验室 / 部门：Dynamic Legged Systems Lab
- 关键主题：四足控制 / 负载运输 / 被动机构 / 全身动力学
- 备注：Giovanni B. Dessy、Claudio Semini 和 Victor Barasuol 发布了步态相关的被动负载运输研究，将该实验室的近期信号从运动控制进一步延伸到步态与机械负载接口的协同设计。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日检查的官方招聘来源中，没有筛选到信息足够具体且当前可行动的新腿足机器人岗位。对于通用招聘页面、转发信息，以及无法核验仍在招聘或与腿足机器人直接相关的职位，本次不作推断、不予收录。今日也不提出过期条目删除建议。

</details>
