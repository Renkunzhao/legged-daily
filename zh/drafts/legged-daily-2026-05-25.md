[English](../../drafts/legged-daily-2026-05-25.md) | **中文**
# 腿足机器人日报 - 2026-05-25

## 摘要
- 今天最强的论文信号是 Any2Any：面向人形机器人全身跟踪的低成本跨本体迁移，从 Unitree G1 预训练模型迁移到 LimX 平台。
- Direct Dynamic Retargeting 是高信号的人形模仿学习论文：绕过中间几何重定向，直接从单目视频优化动态可行的参考轨迹。
- Four Simple Proprioceptive Estimators for Legged Robots 是实用基础设施工作：对比接触辅助 EKF、因子图和固定滞后平滑等估计器，并声明提供 GTSAM 与 ROS 2 兼容实现。
- Unitree 的 `unitree_rl_mjlab` 是 MuJoCo 后端的机器人强化学习栈，覆盖 Go2、A2、AS2、G1、R1、H1_2、H2，并包含 Train → Play → Sim2Real 流程。
- `AMP_Running_baseline` 是聚焦 Unitree G1 跑步 / 模仿学习的 Isaac Lab + AMP 基线，包含运动数据、执行器建模和硬件部署路径。
- CUHK Legged Robot Lab 同时出现 2026 RSS 论文信号，以及 Fall 2027 PhD、RA、工程师机会。

<details>
<summary><strong>新论文</strong></summary>

### Any2Any: Efficient Cross-Embodiment Transfer for Humanoid Whole-Body Tracking
- Link: https://arxiv.org/abs/2605.23733
- Source: arXiv
- Date: 2026-05-22
- Authors: Ming Yang, Tao Yu, Feng Li, Hua Chen
- Topics: humanoid / whole-body tracking / cross-embodiment transfer / parameter-efficient fine-tuning / imitation learning
- Summary: 面向人形全身跟踪预训练策略的跨机器人迁移框架，结合运动学对齐与轻量动力学适配；论文报告用约 1% 的完整训练数据和计算量，将 Unitree G1 上预训练的 Sonic 模型迁移到 LimX Oli 和 LimX Luna。
- Notes: 对可复用人形 WBT 策略和快速平台适配很有长期价值；根据 arXiv 摘要和搜索结果，代码尚未验证为公开。

### Direct Dynamic Retargeting for Humanoid Imitation Learning from Videos
- Link: https://arxiv.org/abs/2605.23762
- Source: arXiv
- Date: 2026-05-22
- Authors: Constant Roux, Ludovic De Matteïs, Armand Jordana, Valentin Guillet, Nicolas Mansard, Olivier Stasse, Philippe Souères
- Topics: humanoid / imitation learning / video demonstrations / motion retargeting / model predictive control / physics simulation
- Summary: 单阶段动态重定向方法，直接从单目专家视频生成物理可行的人形参考轨迹；方法在任务空间中建模，并在物理仿真器内使用采样式 MPC 求解。
- Notes: 对人形技能获取管线很相关，因为它把几何 / 间接重定向视为 RL 前参考生成的瓶颈；论文称代码会公开，但当前未验证到公开仓库。

### Four Simple Proprioceptive Estimators for Legged Robots
- Link: https://arxiv.org/abs/2605.23100
- Source: arXiv
- Date: 2026-05-21
- Authors: Frank Dellaert, Chiyun Noh, Varun Agrawal, Ayoung Kim
- Topics: legged robots / state estimation / proprioceptive odometry / contact-aided estimation / GTSAM / ROS 2
- Summary: 比较四种接触辅助腿足状态估计器，从 invariant EKF 到小型因子图、再到带接触片段落脚点的固定滞后平滑，目标是用 IMU 和间歇足端接触构建可复现实用的本体里程计。
- Notes: 是值得跟踪的腿足状态估计基础设施论文；摘要声明四个变体均已在 GTSAM 中可用，并提供 ROS 2 兼容实现。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### unitree_rl_mjlab
- Link: https://github.com/unitreerobotics/unitree_rl_mjlab
- Category: RL / simulator / toolkit
- Robot Type: humanoid / quadruped / general Unitree platforms
- Simulator: MuJoCo
- Deploy: both
- Summary: Unitree 官方 MuJoCo 强化学习项目，基于 mjlab，支持 Unitree Go2、A2、AS2、G1、R1、H1_2、H2，包含速度跟踪、G1 动作模仿、ONNX 导出和 sim-to-real 部署路径。
- Notes: README 描述 Train → Play → Sim2Real 流程、多 GPU 训练、Unitree SDK2 / CycloneDDS 部署，以及在上真机前使用 `unitree_mujoco` 做仿真部署验证。

### AMP_Running_baseline
- Link: https://github.com/Jiarui-Xie/AMP_Running_baseline
- Category: RL / imitation learning / deployment baseline
- Robot Type: humanoid
- Simulator: Isaac Lab
- Deploy: both
- Summary: 面向 2026 北京亦庄人形机器人半程马拉松的 Unitree G1 运动训练代码库，扩展 legged_lab，加入 AMP、BASE 走 / 跑运动片段、执行器建模、动作延迟随机化、奖励调参和检查点。
- Notes: 是 G1 跑步和动作模仿实验的实用基线；README 区分了已硬件测试的 BASE checkpoint 和后续仅仿真验证 checkpoint。

### sfg-ros
- Link: https://github.com/iis-esslingen/sfg-ros
- Category: toolkit / perception middleware
- Robot Type: general / legged fleets
- Simulator: none
- Deploy: hardware / field software
- Summary: 面向密集多机器人感知的 ROS 2 资源感知框架，使用基于 schema 的 Fast DDS 路由、按需集中解码和硬件无关容器；评估包含搭载 LiDAR 与双目深度相机的轮式和腿足机器人队列。
- Notes: 属于相邻但有价值的腿足野外机器人 / 多机器人感知基础设施；项目页报告相比标准 ROS 2 降低了每订阅者 CPU 扩展惩罚。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### CUHK Legged Robot Lab / Yun-Hui Liu
- Institution: The Chinese University of Hong Kong
- Homepage: https://cuhkleggedrobotlab.github.io/
- Lab / Department: Department of Mechanical and Automation Engineering, CUHK
- Key Topics: quadruped / locomotion / loco-manipulation / perception and navigation / actuator and mechanical system design
- Notes: 官方实验室页面显示 Zhang Linwei 的 “VRA: Grounding Discrete-Time Joint Acceleration in Voltage-Constrained Actuation” 已被 RSS 2026 接收；同时页面说明实验室正在招收 Fall 2027 PhD，并有多个 RA 和工程师岗位。

### LAAS-CNRS / Gepetto 人形控制网络
- Institution: LAAS-CNRS / 相关法国人形机器人网络；加入主列表前需逐一核验作者单位
- arXiv: https://arxiv.org/abs/2605.23762
- Key Topics: humanoid / dynamic retargeting / MPC / imitation learning / physics simulation
- Notes: DDR 的作者网络中包括 Nicolas Mansard、Olivier Stasse、Philippe Souères，是动态人形运动生成和重定向方向值得跟踪的来源。

### Frank Dellaert / Georgia Tech Borg Lab 与 GTSAM 网络
- Institution: Georgia Institute of Technology / GTSAM ecosystem；加入学生信息前需核验共同作者单位
- arXiv: https://arxiv.org/abs/2605.23100
- GitHub: https://github.com/borglab/gtsam
- Key Topics: legged state estimation / factor graphs / smoothing / proprioceptive odometry / ROS 2
- Notes: 新的腿足估计器论文让 GTSAM 网络成为值得跟踪的可复用状态估计工具来源，虽然该实验室并非只做腿足机器人。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### CUHK Legged Robot Lab
- Type: PhD / Research Assistant / Engineer
- Location: Hong Kong
- Source: official lab page
- Deadline: Fall 2027 PhD cycle / RA and engineer timing unknown
- Topics: robust and precise locomotion / whole-body loco-manipulation / traversability-aware perception and navigation / safe actuator and mechanical system design
- Status: active
- Notes: 官方主页说明正在招收 Fall 2027 自驱型 PhD 申请者，并有多个 RA 和工程师岗位；联系邮箱列在实验室页面。

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: 官方页面仍列出多个持续开放岗位，并明确要求腿足机器人相关经验；今天没有发现过期信号。

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: aggregator results pointing to prior official/lab-linked announcement; official page should be rechecked before formal insertion beyond existing master-list entry
- Deadline: Fall 2026 opening; EPFL doctoral program deadlines typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: watching
- Notes: 作为已跟踪机会仍相关；但今天直接抓取旧的 `www.biorob.epfl.ch/openings/` URL 发生 DNS 解析失败，因此正式新增或强化前应从 EPFL / Biorob 官方渠道再次确认。

</details>
