[English](../../drafts/legged-daily-2026-08-13.md) | **中文**
# 腿足机器人日报 - 2026-08-13

状态：仅草稿；等待确认后才能正式发布并合并到主列表。

## 摘要
- SMPC 示范可用于启动稀疏奖励的 offline-to-online RL，完成复杂移动操作；项目报告已迁移到带机械臂的 Spot 与 Unitree G1 真机。
- ContactIPM 将面向接触的内点松弛与最优控制分阶段结构结合；官方实现提供可复现实验和闭环接触验证。
- AWS 当日发布一套 VLA 样例栈，覆盖 Unitree Go2 四足加 6-DoF 机械臂的数据采集、标注、微调、评估和部署。
- RAI Institute、ETH Zurich 与 TUM 围绕规划器生成数据和跨机器人形态学习形成值得跟踪的合作信号。
- Flexion Robotics 在苏黎世新增两个生成式人形全身运动岗位；此前跟踪的 Amazon Safe Locomotion 页面现已失效。

<details>
<summary><strong>新论文</strong></summary>

### Learning Loco-Manipulation From SMPC Demonstrations With Sparse Offline-to-Online RL
- 链接：[arXiv](https://arxiv.org/abs/2608.12063) · [项目页](https://pages.rai-inst.com/smpc2rl/)
- 来源：arXiv
- 日期：2026-08-12
- 作者：Martin Schuck, Maks Sorokin, Simone Manni, Duy Ta, Angela P. Schoellig, Marco Hutter, Simon Le Cleac'h, Jan Brüdigam
- 主题：移动操作 / 稀疏奖励 RL / offline-to-online RL / 采样式 MPC / sim-to-real
- 摘要：方法在仿真中用可快速调节的采样式 MPC 专家生成离线示范，先启动只使用稀疏任务奖励的 off-policy agent，再逐步退出专家数据并转为在线 RL；项目报告已在带机械臂的 Spot 四足和 Unitree G1 人形机器人上部署推、滚、抬举及导航相关技能。
- 备注：项目报告加入专家数据后仿真成功率接近 100%，没有专家数据时无法学会，并在局部数据分布附近比 SMPC 教师更快完成任务；论文当前标注为 under submission，本轮未找到该论文专属的官方代码仓库。

### ContactIPM: A Structure-Exploiting Interior-Point Solver for Contact-Implicit Trajectory Optimization
- 链接：[arXiv](https://arxiv.org/abs/2608.11731) · [官方代码](https://github.com/chenyucheng2016/ContactIPM)
- 来源：arXiv
- 日期：2026-08-12
- 作者：Yucheng Chen
- 主题：接触隐式轨迹优化 / MPCC / 最优控制 / NMPC / 接触规划
- 摘要：论文提出一种原始—对偶求解器，把互补约束对嵌入障碍耦合的 elastic interior 松弛，按阶段消去松弛变量和对偶变量，并用 Riccati 递推求解降维 Newton 系统，目标是提高接触丰富轨迹优化的鲁棒性和效率。
- 备注：匹配基准中，相比 IMPACT 的速度优势随任务而异，相比 CRISP 则在四个固定案例上均更快；公开验证主要是操作与准静态接触，并非已展示的腿足真机控制器，因此其腿足价值主要在方法和基础设施层面。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### aws-samples/sample-vla-mobile-manipulation-on-aws
- 链接：https://github.com/aws-samples/sample-vla-mobile-manipulation-on-aws
- 类别：机器人学习 / VLA / 移动操作 / 工具链
- 机器人类型：四足
- 仿真器：自定义工具链 / 未指定唯一标准仿真器
- 部署：仿真与真机
- 摘要：AWS 的自带 VLA 开发样例，面向 Unitree Go2 与 D1 6-DoF 机械臂，覆盖任务定义、遥操作数据采集、Bedrock 辅助标注、在 EC2 上微调 openpi 或 OpenVLA-OFT、滚动窗口评估，以及按任务阶段路由模型的部署，用于导航、抓取、搬运和放置。
- 备注：创建于 2026-08-13；Python、MIT-0，核验时 1 star。它是集成样例，不是经过独立基准验证的运动或操作新算法，并需要较多云端与机器人专用配置。

### chenyucheng2016/ContactIPM
- 链接：https://github.com/chenyucheng2016/ContactIPM
- 类别：最优控制 / MPC / 求解器
- 机器人类型：通用
- 仿真器：自定义基准模型 / CasADi 接口
- 部署：仿真
- 摘要：ContactIPM 的 Apache-2.0 C++ 实现，支持含动力学、边界、非线性不等式和互补约束的直接转录 NMPC 与最优控制问题；仓库包含固定版本的竞品代码、审计过的基准产物、复现说明和闭环接触测试。
- 备注：创建于 2026-06-09，更新于 2026-08-11；核验时 0 stars。当前公开示例以小车、箱体和 T 形物推动为主，未包含腿足模型，适合按接触优化基础设施跟踪。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### RAI Institute / ETH Zurich / Technical University of Munich 合作
- 机构：RAI Institute；ETH Zurich；Technical University of Munich
- 主页：https://pages.rai-inst.com/smpc2rl/
- arXiv：https://arxiv.org/abs/2608.12063
- GitHub：https://github.com/rai-opensource/judo
- 实验室 / 部门：RAI Institute；ETH Robotic Systems Lab 研究网络；TUM 学习系统合作
- 关键主题：四足 / 人形 / 移动操作 / RL / MPC / sim-to-real
- 备注：新的 SMPC-to-RL 工作把 Martin Schuck、Angela P. Schoellig、Marco Hutter 与 RAI 研究者连接起来，研究规划器生成的离线数据、稀疏奖励学习和跨机器人形态真机部署。项目还把 RAI 已有的 Judo 采样式 MPC 工具箱列为相关基础设施。

### Flexion Robotics 运动生成与人形自主系统团队
- 机构：Flexion Robotics
- 主页：https://flexion.ai/about
- LinkedIn：https://www.linkedin.com/company/flexion-robotics
- X：https://x.com/FlexionAI
- YouTube：https://www.youtube.com/@Flexion-AI
- 实验室 / 部门：Motion Generation / Control / AI Engineering
- 关键主题：人形 / 全身运动 / 生成模型 / RL / 运动控制 / 操作
- 备注：Flexion 将自身描述为覆盖指令、控制、操作与运动的跨人形硬件自主系统栈。团队页显示 ETH Zurich 与前 NVIDIA 机器人研究者——包括 Nikita Rudin 以及顾问兼联合创始人 Marco Hutter——参与建设运动生成、控制、感知与 VLA 团队；两个同日岗位使其成为明确的团队扩张信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Flexion Robotics — Research Engineer, Generative Humanoid Motion Generation
- 类型：研究工程师
- 地点：瑞士苏黎世
- 来源：[官方招聘页](https://flexion.ai/careers/525e50)
- 截止时间：未知
- 主题：人形 / 全身运动 / diffusion / flow matching / 多模态生成模型 / 机器人轨迹生成
- 状态：有效
- 备注：2026-08-13 发布的 AI Engineering 全职岗位，要求生成式或视觉条件运动模型经验，以及将学习式机器人轨迹部署到系统的能力；Omniverse 或 Genesis 和基础模型微调经验也被列为相关能力。

### Flexion Robotics — Internship, Humanoid Motion Generation (Diffusion or Flow Matching)
- 类型：实习
- 地点：瑞士苏黎世
- 来源：[官方招聘页](https://flexion.ai/careers/526f62)
- 截止时间：未知
- 主题：人形 / diffusion / flow matching / 自回归模型 / 3D 感知 / 模仿学习
- 状态：有效
- 备注：2026-08-13 发布的 AI Engineering 实习岗位，面向在读硕士或博士，将生成式全身轨迹生成与三维环境感知结合。

### 建议移除 / 失效条目
- 当前状态：不再可申请
- 原因：此前跟踪的 Amazon Robotics Compass “Senior Applied Scientist, Safe Locomotion” 官方页面现已显示岗位不可用，不应继续作为有效职位展示。
- 已检查来源：https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass

</details>
