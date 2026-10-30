[English](../../drafts/legged-daily-2026-10-30.md) | **中文**
# 腿足机器人研究日报 - 2026-10-30

## 摘要
- **HC2Robot** 从可部署观测预测下一次足端触地的时间、位置和支撑质量；作者报告多种人形跑酷地形上的仿真平均成功率为 97.60%，尚未核实实机验证。
- **ETH 阶段条件 PPO** 将阶段条件化 Critic、分阶段奖励及重置课程结合起来，在真实 Unitree G1 和带机械臂的 Spot 上展示多阶段移动操作。
- **CPG-ENN** 使用可解释的低维步态控制变量统一控制 Walk、Trot、Pace、Bound 和 Pronk；作者报告仿真步态转换成功率 99.39%，并展示真实 Go2 实验。
- **工程项目**：新检索到 Go2 凸 MPC、ROS 2/Gazebo/MuJoCo 综合训练栈及 G1 AMP 跑步训练工程；它们是本次发现的已有仓库，不代表今天首次开源。
- **数据**：HiPHI 提供 617.5 小时人体动作及物体交互数据，须申请研究许可；G1 Moves 提供公开的 60 段 G1 重定向动作与策略导出。
- **招聘**：TUM 人形移动操作博士岗位 11 月 15 日截止；此前已经跟踪的 Aarhus Physical AI 博士岗位 11 月 1 日截止。

<details>
<summary><strong>新论文</strong></summary>

### HC2Robot: Hyper-Connection Transformers with Predicted Foresight for Multi-Terrain Humanoid Parkour
- Link: https://arxiv.org/abs/2610.36825
- Source: arXiv 预印本（尚未确认会议或期刊接收）
- Date: 2026-10-27
- Authors: Wenhao Xu, Yanheng Mai, Yifei Fu, Nan Zheng, Yanbo Zhou, Zirui Huang, Mingsheng Ling, Xinjue Wang, Renjing Xu
- Topics: 人形机器人 / 感知运动 / 精准落足 / 特权学习 / 时序 Transformer / 强化学习
- Summary: Predicted Foresight Module（PFM）根据部署时可用的观测，预测各足下一次触地事件的时间、位置和支撑质量；Hyper-Connection Transformer 与未来动作预测头结合这些预测接触信息和历史上下文，完成复杂地形跑酷控制。
- Notes: 作者报告楼梯、沟壑、高平台和坡面上的平均仿真通过率 97.60%，且安全落足表现优于所比较的感知运动基线；摘要没有提供可核实的真机结果，因此不能当作已验证的实机跑酷技术。

### Learning Multi-Phase Robot Loco-Manipulation via Phase-Conditioned Policy Optimization
- Link: https://arxiv.org/abs/2610.36270
- Source: arXiv 预印本（尚未确认正式会议或期刊）
- Date: 2026-10-26
- Authors: Simone Manni, Annika Wollschläger, Dario Bellicoso, Abel Gawel, Marco Hutter, Simon Le Cleac'h, Jan Brüdigam
- Topics: 人形机器人 / 四足机器人 / 移动操作 / 阶段条件 PPO / 分层控制 / Sim-to-Real
- Summary: 为蹲下、抓取、行走等多阶段任务扩展 PPO，使用阶段条件化 Critic、阶段门控奖励和多阶段重置课程，将底层平衡控制与高层任务阶段执行分开，不依赖人体参考动作数据。
- Notes: 作者在真实 Unitree G1 和配备机械臂的 Boston Dynamics Spot 上展示多阶段操作，并进行了消融实验；目前论文未明确正式发表会议或期刊。

### A Trainable CPG Framework for Quadruped Locomotion
- Link: https://arxiv.org/abs/2610.36537
- Source: arXiv 预印本（尚未确认正式会议或期刊）
- Date: 2026-10-27
- Authors: Xiyan Liu, Yide Liu, Guoyong Mao, Shaoxing Qu
- Topics: 四足机器人 / 步态控制 / CPG / 强化学习 / 速度跟踪 / Unitree Go2
- Summary: CPG-ENN 将对称八神经元节律发生器与共享执行神经网络结合，通过一个反馈策略调节六个可解释的轨迹变量，实现五种步态及其转换，无需为每种步态训练独立策略或在线求解逆运动学。
- Notes: 作者报告 20 种有向步态转换和四档速度指令组合下的仿真转换成功率为 99.39%，并在真实 Go2 上验证五种步态与转换；暂未确认正式发表或开源代码。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### elijah-waichong-chan/go2-convex-mpc
- Link: https://github.com/elijah-waichong-chan/go2-convex-mpc
- Category: MPC / 控制 / 仿真 / 工具
- Robot Type: 四足机器人（Unitree Go2）
- Simulator: MuJoCo / Pinocchio / CasADi / OSQP
- Deploy: 仿真
- Summary: UC Berkeley MEng 项目，复现基于质心线性化与接触力优化的凸 MPC，提供 Raibert 风格落足规划、五次多项式摆腿轨迹及 Go2 小跑演示。
- Notes: README 报告 MPC 约 30–50 Hz、腿部控制 200 Hz，仿真前后速度最高约 0.8 m/s，特定基准 MPC 周期平均耗时约 2.70 ms；未宣称真实 Go2 部署。属于此次新发现的既有工程仓库。

### darshmenon/quadruped-robotics-stack
- Link: https://github.com/darshmenon/quadruped-robotics-stack
- Category: 强化学习 / MPC / 仿真 / 导航工具
- Robot Type: 四足机器人（Unitree Go2；其他机器人配置为不完整占位项）
- Simulator: MuJoCo 3.1 / Gazebo Harmonic / ROS 2 Humble
- Deploy: 仿真
- Summary: 集成 Go2 PPO Locomotion、CHAMP 运动学步态、Quad-SDK NMPC、粗糙地形课程、3D SLAM 和 Gazebo/MuJoCo 导航演示的工程工作区。
- Notes: README 明确指出只有 Go2 使用完整机器人模型，其余 CHAMP 机器人配置只是占位；仓库标注 MIT 许可，展示仿真 NMPC 行走，不等同于实机验证。

### Jiarui-Xie/AMP_Running_baseline
- Link: https://github.com/Jiarui-Xie/AMP_Running_baseline
- Category: 强化学习 / AMP / Motion Tracking / 训练工具
- Robot Type: 人形机器人（Unitree G1）
- Simulator: Isaac Lab 2.3.1 / Isaac Sim 5.1
- Deploy: 仿真与作者展示的 BASE 版本实机演示；后续高速权重尚未确认实机
- Summary: 为 2026 北京亦庄人形机器人半马扩展 Legged Lab，使用双动作片段 Walk/Run AMP 先验、SONIC 风格执行器模型、逐关节命令延迟随机化，以及考虑能耗的高速微调配置。
- Notes: 作者提供 model_6200.pt 基础权重及 sim-to-real 视频；后续 High-Speed 权重仍只有仿真验证。仓库标注 MIT 许可，动作来源可能另受上游许可限制。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### HiPHI — High-Precision Human Motion and Object Interaction
- 链接： https://huggingface.co/datasets/noitomrobotics/HiPHI
- 类别： 人体动捕 / 机器人可用动作参考 / 人体物体交互
- 对象： 人体（可重定向给人形机器人；作者展示 G1 实验）
- 内容： 包括镜像动作共 617.5 小时；其中纯人体动作 371.8 小时、物体交互 245.7 小时；132 位采集者，90 Hz、2.001 亿帧，40 个标准物体网格。
- 格式： 55 关节 BVH / 物体位姿 CSV / OBJ / 元数据 CSV / 32 个 tar.zst 压缩包
- 获取方式： 需同意许可（Hugging Face 问卷申请，批准后下载）
- 许可： modalitynet-open-research-license（商业使用须另行授权）
- 摘要： 大规模高精度光学动捕数据，包含同步物体轨迹，支持人形动作模仿、生成、重定向及接触感知全身控制；对应论文数据卡标为 CoRL 2026。
- 备注： 已核实实际数据包结构及申请流程；公开数据卡不等于匿名可下载。本次是重新发现 2026 年 8 月已发布的数据，而非声称 10 月 30 日首发。

### exptech/g1-moves — G1 Moves
- 链接： https://huggingface.co/datasets/exptech/g1-moves
- 类别： 机器人动作 / 人体动捕 / 动作重定向
- 对象： Unitree G1 EDU（29 DoF）/ 人体动作
- 内容： 60 段动作（28 段舞蹈、27 段空手道、5 段其他），总计约 29.6 分钟、106,434 帧、60 Hz；数据卡声明每段动作均有训练策略资产。
- 格式： BVH / FBX / PKL / NPZ / ONNX / 视频
- 获取方式： 公开
- 许可： cc-by-4.0（Hugging Face 数据卡标注）
- 摘要： 同时提供原始动捕、G1 重定向关节轨迹、RL 训练数据与导出策略的紧凑数据资源，适合开展动作跟踪复现与格式转换研究。
- 备注： 此前已公开，本次新发现；不同修订版本的帧数记载略有差异，进行严格基准测试时需逐片核验。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Marco Hutter / ETH Zurich Robotic Systems Lab
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: 人形 / 四足 / 移动操作 / 强化学习 / 分层全身控制
- Notes: 新的阶段条件 PPO 论文（https://arxiv.org/abs/2610.36270）包含 Marco Hutter 等作者，并在 G1 与带机械臂的 Spot 上验证分阶段强化学习。继续关注代码发布。

### Shaoxing Qu / 浙江大学四足步态学习
- Institution: 浙江大学工程力学系
- arXiv: https://arxiv.org/abs/2610.36537
- Lab / Department: 流体动力与机电系统国家重点实验室 / X-Mechanics 中心
- Key Topics: 四足机器人 / CPG / 神经运动控制 / 可解释步态指令 / 强化学习
- Notes: CPG-ENN 论文展示以可解释轨迹变量控制五种步态，在真实 Unitree Go2 上验证；值得加入多步态运动方向的作者来源网络。

### He Kong / 南方科技大学 — REACH
- Institution: 南方科技大学；与香港中文大学合作
- Homepage: https://aislab-sustech.github.io/REACH/
- arXiv: https://arxiv.org/abs/2610.36546
- Lab / Department: 自动化与智能制造学院
- Key Topics: 人形机器人 / 爬行 / 可变高度行走 / LiDAR 规划 / 多接触切换
- Notes: REACH 标注将发表于 Humanoids 2026，展示真实 G1 穿越低矮障碍及双足行走与四足爬行之间的切换。虽然 arXiv 摘要声称代码可用，项目页实际标注 Code To be released，因此开源状态仍待核实。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 慕尼黑工业大学 TUM / AVS Lab — 人形移动操作博士岗位（拟新增）
- Type: PhD / Research Associate
- Location: 德国 Garching
- Source: 官方实验室职位 — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: 人形 / 移动操作 / Whole-Body Control / 环境感知 / 规划 / VLM / VLA
- Status: active
- Notes: Johannes Betz 团队三年全职 TV-L E13 职位，实验室有真实人形和四足硬件；要求熟练使用德语、英语进行工作交流。此前草稿已发现，本次重新核实仍可申请，但尚未进入正式 jobs.md。

### Aarhus University / A3 Lab — Physical AI 博士岗位（临近截止，拟新增）
- Type: PhD
- Location: 丹麦奥胡斯
- Source: 大学官方招聘 — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: 机器人基础模型 / VLA / 世界模型 / 测试时适应 / 边缘推理
- Status: active
- Notes: 此前已有跟踪记录，不是今天新增的专门腿足岗位；官方截止日期迫近。三年博士项目，导师 Behzad Bozorgtabar 和 Qi Zhang，评测基于公开数据、仿真及可能的机器人硬件。

</details>
