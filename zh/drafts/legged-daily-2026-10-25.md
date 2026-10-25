[English](../../drafts/legged-daily-2026-10-25.md) | **中文**
# Legged Daily - 2026-10-25

## 摘要
- STAMP（2026-10-22，arXiv）学习动作片段之间的位置、朝向和时长对齐，合成可衔接的长时序人形动作；作者展示 G1/K1 跟踪测试及实机演示。
- STR（2026-10-21，arXiv）将动作重定向的计算资源重点分配给物体交互关键帧及身体部位，在 G1 仿真和 R1 实机上评估。
- MPBRS（2026-10-21，arXiv）以统一的势函数奖励结构和权重训练九种人形机器人，减少逐机型手动调参。
- GitHub API 检索发现包含人形/四足/双足策略权重导出的 Isaac Lab 工程，以及两个轮足强化学习与 MuJoCo sim2sim 仓库。
- 昨日尚无法确认文件是否可用的 HuMeGo FlashPad 子集，今天已核实公开 Hugging Face 数据及许可；ETH RSL 的 HOI-Retarget 提供 13,904 条 G1/H2 交互动作轨迹。
- 慕尼黑工业大学 AVS Lab 招聘人形移动操作方向博士研究员，官方截止日期为 2026-11-15。

<details>
<summary><strong>新论文</strong></summary>

### Robot Motion Transition with Human Motion Prior (STAMP)
- Link: https://arxiv.org/abs/2610.30817
- Source: arXiv 预印本；尚未确认正式会议或期刊接收
- Date: 2026-10-22
- Authors: Taehyun Byun, Taemoon Jeong, Yoonbyung Chai, Woojin Wie, Insu Park, Kyungjae Lee, Sungjoon Choi
- Topics: 人形机器人 / 动作生成 / 动作跟踪 / 动作衔接 / 重定向
- Summary: 通过 Robot-to-Human-to-Robot 流程，在人类动作先验生成过渡之前，学习相邻动作片段的位置、朝向和过渡时间配置，再重定向回机器人并训练动作跟踪策略。
- Notes: 在 Unitree G1、ROBOTIS K1 上测试，作者报告实机长时序动作衔接演示。项目：https://childtoy.github.io/STAMP-project/；代码是否开放尚未核实。

### Motion Retargeting with Spatiotemporal Preferences for Humanoid Loco-Manipulation (STR)
- Link: https://arxiv.org/abs/2610.30540
- Source: arXiv 预印本；未注明正式接收会议或期刊
- Date: 2026-10-21
- Authors: Xiongbo Shi, Shihang Du, Zongyou Yu, Ao Zhou, Xudong Zhang, Ziyu Lin, Haodong Zhang, Junqiao Zhao, Guang Chen
- Topics: 人形机器人 / 动作重定向 / 视觉语言模型 / 接触 / 全身强化学习
- Summary: 利用 VLM 识别任务关键帧和关键身体部位，重点分配重定向优化迭代；再以力学感知的接触锚定提高身体与物体的接触准确性，并结合时空强化学习训练下游控制器。
- Notes: 作者在 G1 仿真、R1 实机上实验，报告改善物体接触覆盖率和任务执行；代码是否开放及性能复现尚未独立核查。

### MPBRS: Multi-Potential-Based Reward Shaping for Unified Reward Configuration in Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.30334
- Source: arXiv 预印本；未注明正式接收会议或期刊
- Date: 2026-10-21
- Authors: Van Chung Nguyen, Hung Manh La
- Topics: 人形机器人 / 强化学习 / 奖励塑形 / 运动控制 / 跨本体
- Summary: 将多种势函数奖励组合成统一结构和共享权重，在九种人形机器人上仅通过关节映射、默认姿态等机器人元数据适配，而非重新设计奖励配置。
- Notes: 作者报告奖励权重敏感度下降；摘要未确认真实机器人验证。本次为 10 月 25 日新筛选的前几日论文，并非周日当天新投稿。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### rjdelgadoq/h1v3-robotpolicies
- Link: https://github.com/rjdelgadoq/h1v3-robotpolicies
- Category: RL / locomotion / control / toolkit
- Robot Type: humanoid（asimov-1）/ quadruped（v1x1）/ biped（BDX-R）
- Simulator: NVIDIA Isaac Lab（v3.0.0-beta2.patch1）
- Deploy: sim / ROS2 遥控接口（未确认实体硬件部署）
- Summary: 提供 Isaac Lab PPO/AMP 行走任务、ROS2 速度指令遥控桥、训练脚本，以及 PyTorch、safetensors、ONNX 三种格式的策略权重导出。
- Notes: 作者声明已验证 ONNX 与 PyTorch 输出一致，并包含示例 checkpoint；ROS2 遥控演示不能直接视为完成真实机器人验证。

### Eriwdz/LocoWheeledLegged
- Link: https://github.com/Eriwdz/LocoWheeledLegged
- Category: RL / control / toolkit
- Robot Type: wheeled-legged quadruped（Unitree Go2W）
- Simulator: NVIDIA Isaac Lab
- Deploy: sim / sim-to-real 接口（实际硬件测试未核实）
- Summary: 面向 Go2W 的运动强化学习工程，优化奖励设计和 PPO 训练稳定性，包括动作变化率裁剪、高度观测稳健性以及部署配置。
- Notes: 属于借鉴 DreamWaQ/IsaacGym 代码的工程衍生项目；仓库作者描述不等同于独立性能评测。

### liu-big/wheeled-dog-sim2sim
- Link: https://github.com/liu-big/wheeled-dog-sim2sim
- Category: RL / control / simulator / toolkit
- Robot Type: 自研轮足四足 WheeledDogV2（12 个腿关节、4 个驱动轮）
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.1；MuJoCo
- Deploy: sim（Isaac 训练与 MuJoCo sim2sim）
- Summary: 提供 WheeledDogV2 URDF、复杂地形及楼梯 RL 任务、训练脚本，以及 57 维观测、16 维动作的 MuJoCo 策略部署。
- Notes: 包含 15 cm / 20 cm 台阶场景；未核实实机部署。训练框架存在不同的第三方许可。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### HOI-Retarget — Humanoid Human–Object Interaction Motion
- 链接： https://huggingface.co/datasets/leggedrobotics/hoi-retarget
- 类别： 机器人动作 / 优化生成 / 评测基准
- 对象： Unitree G1（29 DoF）/ Unitree H2（31 DoF）
- 内容： 来源于 5 个动捕数据源的 6,952 个不同交互动作，共 13,904 条机器人动作轨迹；75 类物体、每种机器人约 828.1 分钟，包含逐帧足部/手部接触及物体位姿。
- 格式： Hugging Face Parquet，包含机器人根部及关节轨迹、接触标签、物体位姿和预览视频
- 获取方式： 数据表和轨迹公开；除 OMOMO 外的部分物体网格需要从上游单独申请授权，未随数据一起分发
- 许可： CC BY-NC-SA 4.0（衍生数据受上游许可约束；代码另有独立许可）
- 摘要： ETH RSL 提供的接触中心人形 HOI 动作重定向数据，支持物体交互与移动操作，并带有机器人特定的质量检查标记。
- 备注： 官网数据卡注明 13,904 条轨迹，其中 13,018 条通过 QC；OMOMO 物体网格随数据提供，而 ParaHome、NeuralDome、CoRoleHOI、IMHD2 网格需另行从上游获取。

### HuMeGo — Sim FlashPad（可用性确认更新）
- 链接： https://huggingface.co/datasets/ChenyuanC/HuMeGo-Sim-FlashPad
- 类别： 评测基准 / 机器人动作
- 对象： Unitree G1 + Dex3 灵巧手（仿真）
- 内容： 100 条专家示范、115,336 帧、50 Hz；灯光闪烁计数记忆与物体放置任务。
- 格式： LeRobot v2.1 / Parquet + 640 x 360 头部相机 H.264 视频
- 获取方式： 公开；2026-10-25 已独立访问 Hugging Face 数据集介绍、Data Studio 和文件浏览入口
- 许可： CC BY 4.0（Hugging Face 数据卡）
- 摘要： HuMeGo 中可直接核验的一个子集，测试机器人在执行物体操作前是否保留短暂出现的视觉计数线索。
- 备注： 相比 2026-10-24 的 HuMeGo 待核实条目，今天确认 FlashPad 子集可访问；未逐一核实所有 HuMeGo 子集的文件可用性。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 同济大学 Physical Intelligence Lab — STR 合作研究
- Institution: 同济大学 / 上海创智学院及合作团队
- Homepage: https://arxiv.org/abs/2610.30540
- Lab / Department: Physical Intelligence Lab / STR 跨机构作者合作网络
- Key Topics: 人形机器人 / 重定向 / VLM / 接触感知控制 / 移动操作
- Notes: STR（arXiv:2610.30540，2026-10-21）将 VLM 关键阶段识别、接触约束和 RL 结合，在 G1 与 R1 平台测试；持续关注项目及代码是否发布。当前链接是可核验的论文来源，并非已确认的实验室独立官网。

### ETH Zurich Robotic Systems Lab — HOI-Retarget 数据集
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: 人形机器人 / 接触式动作重定向 / 人与物体交互 / 运动数据
- Notes: 已有实验室跟踪源的新进展，并非新增实验室。HOI-Retarget 公开了 13,904 条 G1/H2 交互轨迹与接触标签：https://huggingface.co/datasets/leggedrobotics/hoi-retarget 。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 慕尼黑工业大学 TUM AVS Lab — 人形机器人移动操作博士研究员（新发现）
- Type: 博士 / Research Associate（全职 TV-L E13，三年合同）
- Location: 德国慕尼黑附近 Garching
- Source: TUM AVS 官方招聘 — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: 人形机器人 / 移动操作 / 全身控制 / 环境感知 / 轨迹规划 / VLM / VLA
- Status: active
- Notes: 官方岗位要求理工硕士毕业、德语和英语均达到熟练工作交流水平，研究将使用真实人形及四足硬件；预定 2027-02-01 入职。官网的 11 月 15 日星期标签与实际日历不一致，宜以日期为主并投递前复核。

</details>
