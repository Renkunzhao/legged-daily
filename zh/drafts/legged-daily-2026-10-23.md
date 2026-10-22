[English](../../drafts/legged-daily-2026-10-23.md) | **中文**
# Legged Daily - 2026-10-23

## 摘要
- PRISM 已正式发表于 ICML 2026，并于 2026-10-21 新上线 arXiv；它把深度损坏拆分为“测量失效”和“有效值不准确”两类，真实机器人下游实验报告平均成功率 92.1%。
- A2I-Calib++ 通过主动激励腿足机器人，同时标定全身多 IMU 的时间偏移、外参和偏置，并专门增强对测量噪声的鲁棒性。
- RangeNav 用重建、语义分割和 BEV 预测联合预训练一个仅约 18.3 万参数的 LiDAR range-image 编码器；论文已投稿 ICRA 2027，目前仍在审稿。
- Amazon FAR 已完整放出 RPL 感知式人形运动训练栈，包括地形专家 RL、多深度蒸馏、随仓库提供的 teacher，以及 MuJoCo sim2sim。
- IIT DLSLab 已有的四足运动框架在 2026-10-22 出现明确提交：“start to adding better d435 model noise”；这是正在开发中的更新，不能视为完整 D435 噪声模型已经完成。
- ETH Zurich RSL 官方招聘页仍列出长期开放岗位；LAAS-CNRS 的安全强化学习人形 PhD 已应从 jobs.md 移除，因为 CNRS 官方页现在明确显示该岗位不再可用。

<details>
<summary><strong>新论文</strong></summary>

### PRISM: Learning Realistic Depth via Physics-Grounded Noise Disentanglement with Semantic-Geometric Collaboration
- Link: https://proceedings.mlr.press/v306/liang26n.html
- Source: ICML 2026
- Date: 2026-10-21
- Authors: Xiujian Liang, Jiacheng Liu, Mingyang Sun, Qichen He, Anda Cheng, Cewu Lu, Jianhua Sun
- Topics: 深度感知 / 传感器噪声 / 仿真到真机 / 感知 / 机器人学习
- Summary: 将真实深度损坏拆分为“测量失效”和“测量不准确”，再结合物理驱动噪声生成与语义-几何先验，使仿真深度数据更接近真实传感器。
- Notes: 已正式发表于第 43 届 ICML 论文集（PMLR 306, 2026）；arXiv 版本于 2026-10-21 上线，编号 2610.29432。论文报告真实机器人下游任务平均成功率 92.1%。对 D435i 的无效区域和边缘损坏尤其有参考价值，因为它把“缺测”和“有值但错误”明确分开建模。

### A2I-Calib++: A Kinematics-Driven Anti-noise Active Calibration Framework for Whole-Body Multi-IMU Systems on Legged Robots
- Link: https://arxiv.org/abs/2610.29438
- Source: arXiv
- Date: 2026-10-21
- Authors: Fangyu Jiang, Chaoran Xiong, Kehui Ma, Zhen Sun, Zeyu Zhang, Ling Pei
- Topics: 腿足机器人 / 多 IMU 标定 / 主动激励 / 本体感知 / 状态估计
- Summary: 结合运动学驱动的主动激励、抗噪轨迹设计与接触约束虚拟 IMU 融合，同时估计时间偏移、IMU 外参与惯性偏置。
- Notes: 仿真和真实四足机器人实验均报告了更高的标定精度、噪声鲁棒性和本体里程计表现。本次核验未发现 A2I-Calib++ 的正式会议或期刊信息；其前作 A2I-Calib 已被 IROS 2025 接收。

### RangeNav: Task-Aligned LiDAR Range-Image Pretraining for Robot Navigation
- Link: https://arxiv.org/abs/2610.29845
- Source: arXiv
- Date: 2026-10-21
- Authors: Samuel Foo Enze, Manthan Patel, Fan Yang, Linus Kramer, Pascal Roth, Marco Hutter, Cesar Cadena
- Topics: 腿足机器人 / LiDAR / 导航 / 表征学习 / 仿真到真机
- Summary: 通过重建、语义分割和 BEV 预测预训练轻量 LiDAR range-image 编码器，之后冻结编码器用于下游导航策略学习。
- Notes: 编码器约 18.3 万参数；与仅重建预训练相比，语义+BEV 监督在训练程序化场景上提升 32.03 个百分点，在 OOD 真实感场景上提升 23.73 个百分点。真机零样本演示使用 Unitree B2-W。论文明确写明已投稿 ICRA 2027、正在审稿；作者承诺开源代码和模型，但本次运行尚未找到正式代码发布。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### amazon-far/RPL
- Link: https://github.com/amazon-far/RPL
- Category: RL / 控制 / 感知式运动 / 蒸馏
- Robot Type: 人形
- Simulator: Isaac Gym / MuJoCo
- Deploy: sim
- Summary: RPL 官方研究代码，覆盖分地形专家 RL、多深度 Student 蒸馏、随仓库提供的 Teacher、ONNX 导出和 MuJoCo sim2sim。
- Notes: 首次公开提交为 2026-10-16，README 更新到 2026-10-20。基于 Holosoma，仓库包含 PPO-MA / DAgger-MA、深度渲染、地形专家以及可直接用于 sim2sim 的 Student。README 将对应论文标注为 CoRL 2026。许可证为 Apache-2.0。

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / 控制 / 仿真到真机 / 工具包
- Robot Type: 四足
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: DLSLab 已有的四足运动栈，支持 Aliengo、Go2、B2、A2、HyQReal2，覆盖 RL 训练、状态估计、动力学适应、MuJoCo sim2sim 和 ROS 2 真机部署。
- Notes: 对 repos.md 已有条目的更新：2026-10-22 的提交 92687729 标题为“start to adding better d435 model noise”，因此它成为一个值得继续跟踪的 RealSense 真实深度损坏建模信号。README 同时把 DAgger depth-to-action 蒸馏、Depth-to-Heightmap 和 Lidar-to-Heightmap 标为“已做但尚未测试”的 WIP；目前不能把新的 D435 模型当作已完成方案。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Robotic Systems Lab — ETH Zurich
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: 腿足运动 / 感知 / 导航 / 强化学习 / MPC / 野外机器人
- Notes: RangeNav（arXiv:2610.29845）是来自 Marco Hutter、Cesar Cadena 等作者的新 LiDAR 导航信号。RSL 官方招聘页仍列出长期开放的 PhD、博后、Research Staff/Software、Robot Design、Embedded Systems 和 Electronics 等岗位；这是对已有跟踪源的更新，不是新增实验室条目。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: 官方网站
- Deadline: rolling / unknown
- Topics: 腿足机器人 / 运动控制 / MPC / 强化学习 / 感知 / 导航 / 机器人系统
- Status: active
- Notes: 今日重新核验，RSL 官方岗位页仍列出上述类别，因此 jobs.md 中现有条目应继续保持 active；这不是一个新发现的岗位。

### Proposed Removal / Stale Item
- Current Status: expired / no longer actionable
- Reason: LAAS-CNRS Gepetto Team 的安全强化学习人形机器人 PhD 截止日期为 2026-07-31，CNRS 官方页面现在明确显示该岗位“不再可用”。
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
