[English](../../drafts/legged-daily-2026-10-28.md) | **中文**
# Legged Daily - 2026-10-28

## 摘要
- KAIST 提出摩擦接触的平滑解析梯度：正向仍使用硬接触求解，反向传播才使用松弛梯度。作者报告四足策略使用 10 万样本、桌面电脑约 108 秒完成训练，并直接迁移至 45 kg 实机；论文投稿 T-RO，尚未确认接收（arXiv:2610.35852，10 月 26 日）。
- Amazon FAR 的 FLoRe 使用带力传感的双手持夹爪收集无需机器人参与的示范，学习可感知接触力的人形移动操作；三项真实机器人任务成功率为 80%，仅位置策略基线为 26.7%（arXiv:2610.35862）。
- 《Continuous-Time Safe Planning for Agile Quadrupeds》使用 Bernstein 多项式对整个轨迹时域的避障与运动输入约束进行验证，而非只在离散节点检查；包含四足机器人动态障碍实机测试（arXiv:2610.35670）。
- 新发现值得参考的 Go2 项目：支持独立步长指令及 ROS 2 实机部署的 SLR 分支，以及支持 Isaac Lab / MuJoCo sim-to-sim 的 HimLoco-AMP-Lab；MIRRORME BPX 的 Isaac Lab 基线另提供平地和楼梯预训练权重。
- PHUMA（CoRL 2026 Spotlight）已提供 G1/H1-2 动作数据下载，但 Hugging Face 公共包不包含受上游许可证限制的部分；论文所称完整数据集约 73 小时，须按脚本另行补全。FLoRe 力标注示范仍未公开，应仅作数据候选跟踪。
- 今日未发现新的高置信度招聘。此前草稿中的奥胡斯大学 Physical AI 博士截止 2026-11-01 23:59 CET；TUM AVS 人形移动操作博士截止 2026-11-15。

<details>
<summary><strong>新论文</strong></summary>

### Differentiable Contact Dynamics for Legged Locomotion: Policy Learning and Contact-Implicit Trajectory Optimization
- Link: https://arxiv.org/abs/2610.35852
- Source: arXiv 预印本；已投稿 IEEE Transactions on Robotics (T-RO)，尚未注明接收
- Date: 2026-10-26
- Authors: Gijeong Kim, Seungbin Oh, Dongyun Kang, Hae-Won Park
- Topics: 四足 / 摩擦接触 / 可微物理 / 策略学习 / BPTT / 接触隐式轨迹优化 / 实机
- Summary: 对 de Saxcé 修正的库仑摩擦锥互补条件进行松弛，仅替换反向传播中的接触灵敏度，正向仍按原硬接触模型执行。所得平滑梯度可跨越粘着、滑动、分离等接触模式边界，用于 BPTT 策略训练与接触隐式轨迹优化。
- Notes: 项目 https://diffcontact.github.io/ 。作者报告桌面计算机上 10 万样本、108 秒完成 Trot/Pace 训练，未经实机微调部署至 45 kg 四足机器人，并展示抗扰和低摩擦测试。结果依赖论文实验条件；尚未核实代码公开。

### Learning Force-Reactive Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.35862
- Source: arXiv 预印本；未注明已接收会议或期刊
- Date: 2026-10-26
- Authors: Sihang Li, Xiaofeng Guo, Jinkun Cao, Charlie Cheng, Ruihan Yang, Chen Feng, Guanya Shi, Haozhi Qi
- Topics: 人形 / 移动操作 / 力感知 / 混合柔顺控制 / 全身控制 / 扩散策略 / 实机
- Summary: FLoRe 使用两只带力传感的 UMI 式手持夹爪和身体追踪器采集无需实机参与的动作与接触力示范，训练融合视觉、本体状态与接触力的 Diffusion Policy；全身控制器通过力误差反馈修正手部位置目标，同时保持平衡与其他方向的柔顺性。
- Notes: 项目 https://louis-leee.github.io/FLoRe/ 。作者在擦白板、双手转动箱体、推动龙门架三项真实机器人任务中报告成功率 80%，位置策略对照为 26.7%。项目页仍标注代码 coming soon，未发现示范数据公开下载。

### Continuous-Time Safe Planning and Control for Agile Quadrupeds
- Link: https://arxiv.org/abs/2610.35670
- Source: arXiv 预印本；未注明已接收会议或期刊
- Date: 2026-10-26
- Authors: Gage MacLin, Mason Peterson, Camilla Tabasso, Venanzio Cichella, Joshua Migdal, Tye Brady, Taskin Padir
- Topics: 四足 / 安全导航 / 在线规划 / Bernstein 多项式 / 连续时间避障 / 实机
- Summary: 保留机器人航向相关、带各向异性速度约束的全驱动 SE(2) 模型，用复合 Bernstein 多项式规划轨迹，借助凸包性质在完整时间区间内验证碰撞避免和控制输入界限，而非仅检查离散采样点。
- Notes: 包含四足机器人在未知移动障碍环境中的闭环实机导航及仿真消融；未确认开源代码或正式录用信息。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Yoshifumi-Masuya/slr-stride
- Link: https://github.com/Yoshifumi-Masuya/slr-stride
- Category: 控制 / 强化学习 / 四足运动 / sim-to-real
- Robot Type: 四足（Unitree Go2）
- Simulator: Isaac Lab；原始 SLR 项目仿真环境
- Deploy: 仿真与实机（作者报告通过 ROS 2 在真实 Go2 运行）
- Summary: 基于 CoRL 2024 SLR 本体感知策略，增加可独立于速度指定的 0.1–0.4 m 步长指令，通过落足接触事件测量真实步长、步长奖励课程、零速度停止逻辑，并提供 Isaac Lab 和 ROS 2 实机接口。
- Notes: 非官方 SLR 分支，并非新的同行评审论文。README 提醒遵守上游非商业许可证；API 未找到根目录 LICENSE。适合研究 gait command、步长可控性及零速度奖励漏洞。

### ultimate-max/HimLoco-AMP-Lab
- Link: https://github.com/ultimate-max/HimLoco-AMP-Lab
- Category: 强化学习 / AMP / 四足运动 / sim-to-sim
- Robot Type: 四足（Unitree Go2）；ChituMax 腿足平台
- Simulator: Isaac Lab（Isaac Sim 5.1）；MuJoCo sim-to-sim
- Deploy: 仿真
- Summary: 基于 Isaac Lab 提供 PPO 与 AMP 速度控制、六帧历史观测、地形课程、域随机化、示范动作回放、TorchScript/ONNX 导出及 MuJoCo sim-to-sim。
- Notes: 项目代码 BSD-3-Clause。AMP 专家动作数据因许可原因不随仓库发布，需要用户合法自备；纯 PPO 模式不需要该数据。sim-to-sim 跑通不代表实机安全可用。

### Ryon-droid/bpx-rl-train
- Link: https://github.com/Ryon-droid/bpx-rl-train
- Category: 强化学习 / 训练框架 / 评测工具
- Robot Type: 四足（MIRRORME BPX）
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.1；RSL-RL PPO
- Deploy: 仿真
- Summary: 面向 MIRRORME BPX 的独立 Isaac Lab 项目，提供平地、混合地形及楼梯速度跟踪任务，使用 45 维 Actor 观测、12 维动作接口；公开平地与楼梯训练 Checkpoint、TorchScript/ONNX 策略、训练配置和评测报告。
- Notes: BSD-3-Clause；明确不包含 SDK 集成或实机部署。主要价值是可复现训练与评测工程，而非新型运动算法。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### PHUMA: Physically Reliable Humanoid Locomotion Dataset
- Link: https://huggingface.co/datasets/DAVIAN-Robotics/PHUMA
- Category: 机器人动作 / 视频来源动作 / 动作重定向
- Subject: Unitree G1 和 H1-2 人形；源数据来自人体动捕和互联网视频
- Content: 论文报告完整动作库约 73 小时；目前 Hugging Face 公共仓库约 3.42 GB，明确排除了 LAFAN1 与 LocoMuJoCo 来源片段，需要遵守上游许可证并按脚本另行补齐。
- Format: 压缩包内的逐动作 .npy，包含根部平移、四元数、关节位置和采样帧率
- Access: 公共子集可下载；完整部分需按上游数据授权及预处理说明获取
- License: Hugging Face 数据卡标注 Apache-2.0；源数据独立许可证限制仍适用
- Summary: 通过物理约束数据筛选和重定向生成适合机器人动作跟踪的训练参考，论文展示了在真实 G1 上的动作跟踪迁移。
- Notes: CoRL 2026 Spotlight；论文 https://arxiv.org/abs/2510.26236 ，代码 https://github.com/DAVIAN-Robotics/PHUMA 。这是旧数据集的今日补充发现，非 10 月 28 日新发布；不能将公共子集等同于完整 73 小时数据。

### FLoRe Force-Annotated Demonstrations（未发布，仅跟踪）
- Link: https://louis-leee.github.io/FLoRe/
- Category: 机器人动作 / 接触力示范
- Subject: 带力传感的双手持 UMI 式夹爪、人体追踪器；面向人形移动操作
- Content: 论文使用手部运动、接触力/力矩和身体、足部运动训练 FLoRe，项目未公开具体示范数量
- Access: 尚未开放；仅作待跟踪候选
- License: 未注明
- Summary: 可为力反馈人形移动操作策略提供示范，但尚无法找到可下载的数据资源。
- Notes: 不应在确认文件可下载且许可证明确前合并到正式 datasets.md；项目当前显示代码即将发布。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Hae-Won Park / KAIST（新论文信号）
- Institution: KAIST
- Homepage: https://diffcontact.github.io/
- Lab / Department: 腿足运动与可微接触研究团队
- Key Topics: 四足 / 摩擦接触 / 可微动力学 / 最优控制 / sim-to-real
- Notes: Gijeong Kim、Seungbin Oh、Dongyun Kang、Hae-Won Park 提出面向策略训练和 CITO 的平滑接触梯度（arXiv:2610.35852），提供详细项目页与实机视频。状态为 T-RO 投稿，尚非正式接收。

### Amazon Frontier AI & Robotics（已有研究网络更新）
- Institution: Amazon FAR；与 NYU、Carnegie Mellon University、University of Chicago 合作
- Homepage: https://louis-leee.github.io/FLoRe/
- Lab / Department: Frontier AI & Robotics
- Key Topics: 人形 / 移动操作 / 接触力 / 从示范学习 / 全身控制
- Notes: FLoRe（arXiv:2610.35862）展示了该研究网络在 RPL 感知运动之外的力传感示教与混合柔顺控制方向；官网已展示三项真实机器人实验，代码仍标注 coming soon。

### DAVIAN Robotics / KAIST AI（数据集信号）
- Institution: KAIST AI；合作机构 KRAFTON、Holiday Robotics
- Homepage: https://davian-robotics.github.io/PHUMA/
- GitHub: https://github.com/DAVIAN-Robotics/PHUMA
- Lab / Department: DAVIAN Robotics
- Key Topics: 人形 / 动作数据 / 物理约束重定向 / 模仿学习 / sim-to-real
- Notes: PHUMA 已获 CoRL 2026 Spotlight，公开 G1/H1-2 动作数据处理流程及可下载公共子集；完整数据需补充上游受限来源。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Aarhus University / A3 Lab（之前草稿已记录，仅更新临近截止状态）
- Type: PhD
- Location: 丹麦奥胡斯
- Source: 官方大学招聘 — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: Physical AI / VLA / 世界模型 / 机器人学习 / 测试时适应 / 边缘推理
- Status: active
- Notes: 2026-10-28 官方页面仍可访问；为 Behzad Bozorgtabar 和 Qi Zhang 指导的三年博士岗位，已出现在 10 月 26 日草稿。方向与腿足机器人相邻但非腿足专项；不重复作为今日新岗位。

### TUM / Autonomous Vehicle Systems Lab（之前草稿已记录，仅更新临近截止状态）
- Type: PhD / Research Associate
- Location: 德国 Garching
- Source: 官方实验室招聘 — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: 人形 / 全身控制 / 感知 / 移动操作 / VLM / VLA
- Status: active
- Notes: 官方页面仍列出三年、100% TV-L E13 职位，要求熟练使用德语和英语；10 月 25 日草稿已收录。网页标注的星期与具体截止日期不符，以 2026-11-15 日期为准；不重复记为今日新岗位。

</details>
