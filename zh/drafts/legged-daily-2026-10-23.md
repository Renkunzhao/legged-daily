[English](../../drafts/legged-daily-2026-10-23.md) | **中文**
# Legged Daily - 2026-10-23

## 摘要
- 按用户要求补充：LOAD 将显式惯参估计与隐式动力学特征用于窄桥通过；SuperMimic 用可微世界模型训练人形动作跟踪（CoRL 2026 Oral）；FIBER 学习统一潜空间移动操作规划。
- PRISM 将深度缺测与测量不准分开建模（ICML 2026）；A2I-Calib++ 关注全身多 IMU 的抗噪主动标定。
- RangeNav 用重建、语义分割和 BEV 预测联合预训练一个仅约 18.3 万参数的 LiDAR range-image 编码器；论文已投稿 ICRA 2027，目前仍在审稿。
- Amazon FAR 已放出 RPL 感知式人形运动训练栈（地形专家 RL、多深度蒸馏、随仓库提供的 teacher、MuJoCo sim2sim）；IIT DLSLab 已有的四足框架在 2026-10-22 有提交开始加入更真实的 D435 噪声模型，仍在开发中。
- 刷新（北京时间 10:00）：SuperMimic 官方尚未放出代码，但一天内已出现多个独立复现：zita-ch/supermimic_vibed（Isaac Lab 3 kit-less + MuJoCo-Warp）报告约 1.5 GPU 小时内 LAFAN1 回报 0.829、40 条 clip 0 失败；基于 UniLab 和 mjlab 的复现也报告了相近的 LAFAN1 结果。
- ETH Zurich RobotX 正在招募 2027 年博士及博士后 Fellowship（均截止 2026-11-27），明确涵盖腿足运动和人形机器人；RSL 长期岗位仍在招聘，而 LAAS-CNRS 安全强化学习 PhD 官方招聘已经失效。

<details>
<summary><strong>新论文</strong></summary>

### LOAD: Locomotion with Online Awareness of Dynamics for Precision Footholds
- Link: https://arxiv.org/abs/2610.17930
- Source: arXiv
- Date: 2026-10-13
- Authors: Kunzhao Ren, Zhishuo Zhu, Xiaobin Xiong
- Topics: 显式惯性参数估计 / 隐式动力学适应 / 窄桥通过 / 感知运动
- Summary: 结合显式躯干惯性参数估计与隐式动力学历史特征，并将高程图教师蒸馏为深度图学生，实现未知负载下的精准落足与窄桥通过。
- Notes: arXiv 预印本；公开 arXiv 页面未注明已接收的会议或期刊。真机实验包括单侧 6 kg 负载通过 10 cm 桥、单侧 9 kg 负载通过 15 cm 桥，以及均匀分布 11 kg 负载通过 15 cm 桥。按用户要求补充收录，并非今日新发布。

### SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model
- Link: https://arxiv.org/abs/2610.28480
- Source: arXiv
- Date: 2026-10-20
- Authors: Qiayuan Liao, Yiyang Shao, Junfeng Long, Kevin Zakka, Roberto Horowitz, Pieter Abbeel, Koushil Sreenath
- Topics: 人形机器人 / 可微世界模型 / 基于模型的学习 / 动作跟踪 / 仿真到真机
- Summary: 利用刚体仿真器的状态转移训练统一可微世界模型，再通过短时想象轨迹的解析梯度训练通用动作跟踪策略，并迁移到真实 Unitree G1。
- Notes: arXiv 明确注明已被 CoRL 2026 接收为 Oral；尚未核实正式论文集出版。论文报告单 GPU 训练 3 小时超过 SONIC 基线回报，在 129,514 段测试动作中失败 25 段；这些数字为论文报告的特定基准结果。项目：https://supermimic.github.io/。已出现在 2026-10-22 草稿中，本次按用户要求补充保留。

### FIBER: Action-Aligned Latent Planning for Versatile Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.24675
- Source: arXiv
- Date: 2026-10-17
- Authors: Yutang Lin, Guanya Shi, C. Karen Liu
- Topics: 人形机器人 / 移动操作 / 行为基础模型 / 潜空间规划 / 离线学习
- Summary: 通过匹配局部控制响应，将任务专家投影到冻结行为基础模型的可执行潜空间，再离线训练统一的感知流匹配规划器，执行搬箱、开门和抓取。
- Notes: arXiv 预印本；v2 更新于 2026-10-20，arXiv 未注明已接收的会议或期刊。论文报告仿真平均成功率 42.0%，投影潜轨迹回放与运动学规划基线分别为 11.6% 和 3.5%，并展示真实 Unitree G1 实验。项目：https://fiberaa.github.io/；代码链接仍标注 coming soon。本次按用户要求补充收录。

### PRISM: Learning Realistic Depth via Physics-Grounded Noise Disentanglement with Semantic-Geometric Collaboration
- Link: https://proceedings.mlr.press/v306/liang26n.html
- Source: ICML 2026
- Date: 2026-10-21
- Authors: Xiujian Liang, Jiacheng Liu, Mingyang Sun, Qichen He, Anda Cheng, Cewu Lu, Jianhua Sun
- Topics: 深度感知 / 传感器噪声 / 仿真到真机 / 感知 / 机器人学习
- Summary: 将真实深度损坏拆分为“测量失效”和“测量不准确”，再结合物理驱动噪声生成与语义-几何先验，使仿真深度数据更接近真实传感器。
- Notes: 已于 2026 年 7 月正式发表于第 43 届 ICML 论文集（PMLR 306）；上述 2026-10-21 是后续 arXiv 版本上线日期（2610.29432），并非会议出版日期。论文报告真实机器人下游任务平均成功率 92.1%。对 D435i 的无效区域和边缘损坏尤其有参考价值，因为它把“缺测”和“有值但错误”明确分开建模。

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
- Notes: 首次公开提交为 2026-10-16，README 更新到 2026-10-20。基于 Holosoma，仓库包含 PPO-MA / DAgger-MA、深度渲染、地形专家以及可直接用于 sim2sim 的 Student。README 将对应论文标注为 CoRL 2026。这是研究代码发布：训练目前采用 Isaac Gym，因为 Isaac Sim 的外力扰动尚未支持；并入 Holosoma 主线是独立工作。许可证为 Apache-2.0。

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / 控制 / 仿真到真机 / 工具包
- Robot Type: 四足
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: DLSLab 已有的四足运动栈，支持 Aliengo、Go2、B2、A2、HyQReal2，覆盖 RL 训练、状态估计、动力学适应、MuJoCo sim2sim 和 ROS 2 真机部署。
- Notes: 对 repos.md 已有条目的更新：2026-10-22 的提交 [92687729](https://github.com/iit-DLSLab/basic-locomotion-isaaclab/commit/92687729f3b85ca4c88f87d075f64c1ff99a0777) 标题为“start to adding better d435 model noise”，因此它成为一个值得继续跟踪的 RealSense 真实深度损坏建模信号。README 同时把 DAgger depth-to-action 蒸馏、Depth-to-Heightmap 和 Lidar-to-Heightmap 标为“已做但尚未测试”的 WIP；目前不能把新的 D435 模型当作已完成方案。

### zita-ch/supermimic_vibed
- Link: https://github.com/zita-ch/supermimic_vibed
- Category: RL / 基于模型的学习 / 动作跟踪 / 世界模型
- Robot Type: 人形
- Simulator: Isaac Lab / MuJoCo-Warp
- Deploy: sim
- Summary: 依据论文从零实现的 SuperMimic 非官方复现，基于 Isaac Lab 3 kit-less 与 Newton MuJoCo-Warp 求解器：学习可微世界模型，再用短视野 BPTT 训练策略，让 Unitree G1 跟踪 40 条 LAFAN1 动作。
- Notes: 2026-10-21 创建，README 署名 Chong Zhang（ETH Zurich）；MIT 许可。README 报告在单张 RTX PRO 6000 上训练 1.47 小时后评测回报 0.829、40 条 clip 0 失败，对照论文中 H100 上 1.2 小时达到 0.82。作者明确说明该仓库是借助 AI 编程助手“1 小时速写”的未审查代码，并说明 SuperMimic 官方代码尚未发布。通过 GitHub API 找到的其他独立复现：[Motphys/Uni-SuperMimic](https://github.com/Motphys/Uni-SuperMimic)（基于 UniLab 1.5.0，支持 mjwarp / MuJoCo / Motrix 后端，README 报告 12k 迭代时回报 0.827、40 条 0 失败；Apache-2.0）和 [CuboiLeo/SuperMimic-Reproduced](https://github.com/CuboiLeo/SuperMimic-Reproduced)（基于 mjlab，包含 BONES-SEED 12.99 万条 clip 的数据管线和多卡训练；README 说明其最佳 LAFAN1 结果额外加入了论文中没有的锚点相对观测；MIT）。以上数字均为 README 自报，未独立验证。

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

### ETH Zurich RobotX — PhD Fellowship 2027
- Type: PhD
- Location: 瑞士苏黎世
- Source: ETH Zurich 官方招聘页 — https://jobs.ethz.ch/job/view/JOPG_ethz_zBtPwWHnM0fumyTFso
- Deadline: 2026-11-27
- Topics: 腿足运动 / 人形机器人 / 全身控制 / 强化学习 / 感知 / 机器人学习 / 操作
- Status: active
- Notes: ETH RobotX 面向 2027 年入学的资助博士岗位，一次申请可以填写最多三位意向教授；研究方向明确包括腿足运动与操作、人形全身控制和安全机器人等。要求在 2027 年 8 月前取得相关硕士学位，只接受官方在线系统申请。这与 RSL 长期公开招聘是两个不同的渠道。

### ETH Zurich RobotX — Postdoctoral Fellowship（博士后）
- Type: Postdoc
- Location: 瑞士苏黎世
- Source: ETH Zurich 官方招聘页 — https://jobs.ethz.ch/job/view/JOPG_ethz_58u057ys6BxuEciK5P
- Deadline: 2026-11-27
- Topics: 腿足运动 / 人形机器人 / 全身控制 / 强化学习 / 感知 / 操作 / 运动规划
- Status: active
- Notes: 与 RobotX 博士 Fellowship 分开招聘。申请人可选最多三位意向教授；博士学位须在 2027 年 8 月前取得，预计 2027 年入职。官方岗位说明初始聘期一年、通常可延长，只接受官方在线系统申请，不接受邮件申请。

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: 官方网站 — https://rsl.ethz.ch/the-lab/open-positions.html
- Deadline: rolling / unknown
- Topics: 腿足机器人 / 运动控制 / MPC / 强化学习 / 感知 / 导航 / 机器人系统
- Status: active
- Notes: 今日重新核验，RSL 官方岗位页仍列出上述类别，因此 jobs.md 中现有条目应继续保持 active；这不是一个新发现的岗位。

### Proposed Removal / Stale Item
- Current Status: expired / no longer actionable
- Reason: LAAS-CNRS Gepetto Team 的安全强化学习人形机器人 PhD 截止日期为 2026-07-31，CNRS 官方页面现在明确显示该岗位“不再可用”。
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
