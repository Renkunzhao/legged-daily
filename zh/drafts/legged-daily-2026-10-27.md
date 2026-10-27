[English](../../drafts/legged-daily-2026-10-27.md) | **中文**
# Legged Daily - 2026-10-27

## 摘要
- 一项 sim-to-sim 研究（arXiv，2026-10-23）发现，学习得到的人形动作跟踪策略只能承受 20-30 ms 的指令延迟；训练时在 0-50 ms 范围内随机化延迟后，40 ms 延迟下的平均存活率从 15% 提升到 95%。
- IIT 动态腿足系统实验室（DLS）给出在 Unitree Go2 + AgileX Piper 腿足机械臂上微调 VLA 的实用方案，把数据覆盖与模型容量的影响分开研究，并完成实机闭环抓取放置。
- HoloBoxing（arXiv，2026-10-23）在冻结的预训练全身控制器之上加一个紧凑的身体目标点规划器，约 7 分钟单 GPU 任务训练即可学会人形拳击（仅仿真）。
- Menlo Research 的开源框架 Cyclotron 现已公开 Asimov-1 运动策略训练代码（Isaac Lab，PPO + AMP）及 sim-to-real 部署；Hugging Face 上另有一个公开的 65 场景 MuJoCo 运动鲁棒性基准。
- Berkeley Humanoids 发布 Lite Motion Retargeting 工具和 Lite-Kimodo 数据集（约 2.9 万条由文本生成的 G1 动作，重定向到 Lite Pro，Apache-2.0）；另出现一个把 SuperMimic 移植到 31 自由度 LimX Oli 人形的仓库。
- 跟进：ViT-H 官方仓库（github.com/mileret/ViT-H-release，MIT）已公开，但目前只有 README；作者计划 2026-11-01 前发布离线代码、2026-12-01 前发布遥操作代码。今日没有新的已核实招聘信号。

<details>
<summary><strong>新论文</strong></summary>

### Delay Randomization Widens the Delay Margin of Learned Humanoid Motion Trackers
- Link: https://arxiv.org/abs/2610.32277
- Source: arXiv 预印本；未注明录用会议/期刊
- Date: 2026-10-23
- Authors: Shaoqin Li, Yi Sun
- Topics: 人形 / 动作跟踪 / sim-to-sim / 执行延迟 / 域随机化 / 鲁棒性评测
- Summary: 用五段视频提取的动作训练 24 关节人形跟踪策略，并在一个经过核验的独立 CPU MuJoCo 测试环境中评测。未做延迟随机化的策略只有 20-30 ms 的延迟裕度（40 ms 时平均存活率 15%）；训练时在 0-50 ms 范围内随机化延迟后，40 ms 时平均存活率升至 95%，裕度扩大到 50-70 ms，代价是跟踪精度略有下降。
- Notes: 对照组额外训练了同样的迭代次数但没有提升，说明增益确实来自延迟随机化本身。作者建议按机器人实测延迟设定随机化范围，并把延迟裕度与其他 sim-to-sim 指标一起报告。作者还发现，最初看到的 sim-to-sim 差距其实来自测试环境的 bug（缺少地面、时间步长设错）。8 页，仅仿真。

### From Tabletop to Walking Bot: Deploying a VLA Model on a Legged Manipulator Robot
- Link: https://arxiv.org/abs/2610.32271
- Source: arXiv 预印本；未注明录用会议/期刊
- Date: 2026-10-23
- Authors: Giovanni Minelli, Antonio Langella, Giovanni B. Dessy, Lorenzo Amatucci, Giulio Turrisi, Victor Barasuol, Claudio Semini
- Topics: 四足 / 腿足机械臂 / 移动操作 / 视觉-语言-动作（VLA）/ 微调 / 实机
- Summary: 研究把预训练 VLA 从固定基座机械臂迁移到搭载 AgileX Piper 机械臂的 Unitree Go2 时需要做哪些调整，涉及数据采集、模型版本、动作 horizon 和示教规范，并报告了实机闭环抓取放置结果。
- Notes: 扩大示教覆盖范围使留出集上的末端误差降低 30%；加入推等辅助技能能带来新的行为模式，且不损害基础任务。作者阵容与 IIT 动态腿足系统实验室（Claudio Semini）一致；未说明是否开源代码。

### HoloBoxing: A Simple Recipe for Humanoid Boxing with 7 Minutes of Single-GPU Training
- Link: https://arxiv.org/abs/2610.32909
- Source: arXiv 预印本；未注明录用会议/期刊
- Date: 2026-10-23
- Authors: Xihan Ma, Bo Zhang, Boxiong Li, Yuhan Bao, Ziyue Liu, Yucheng Wang
- Topics: 人形 / 分层控制 / 预训练全身控制器 / 模仿初始化 / 强化学习 / 交互技能
- Summary: 把可复用的运动技能与任务决策分开：紧凑的规划器输出 32 维动作，经学习得到的解码器映射为未来一段时间的身体关键点目标，再由冻结的预训练全身控制器执行；先用实测状态做模仿学习初始化规划器，再进行强化学习。
- Notes: “7 分钟”只包括额外的表征拟合和单 GPU 任务训练，不含控制器预训练、数据准备、评测和超参搜索。实验仅在仿真中进行；arXiv 页面未给出代码或项目链接。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### menloresearch/cyclotron
- Link: https://github.com/menloresearch/cyclotron
- Category: 强化学习 / 训练框架 / 基准工具
- Robot Type: 人形（Menlo Asimov 1）
- Simulator: Isaac Lab（训练）；MuJoCo（基准测试环境）
- Deploy: 仿真与实机
- Summary: Asimov-1 运动策略的官方训练与评测框架，以独立 Isaac Lab 扩展的形式提供，采用 PPO 加对抗运动先验（AMP），覆盖训练、导出、可视化和基准测试全流程；README 中有仿真与实机行走的对比演示。
- Notes: BSD-3-Clause；2026-09-11 创建，最近推送 2026-10-23，约 130 星。可与下方的 Asimov 运动基准数据集配合使用。labs.md 原先记录“Asimov 运动策略尚待发布”，该仓库补上了这一缺口。

### Berkeley-Humanoids/Lite-Motion-Retargeting
- Link: https://github.com/Berkeley-Humanoids/Lite-Motion-Retargeting
- Category: 动作重定向 / 数据集工具 / 可视化
- Robot Type: 人形（Berkeley Lite Pro；源数据来自人体动捕和 Unitree G1）
- Simulator: IK 重定向不需要仿真器；可选用 ReActor 做基于物理的重定向
- Deploy: 数据
- Summary: 用逐帧 IK 把 LAFAN1、AMASS、BONES-SEED、MotionDecode 和 Kimodo G1 等数据源重定向到 Lite Pro 人形，在相同帧上对比 IK、UMR 和 ReActor 三种方法，并以分层 Rerun 文件发布动作，附带浏览用的 Space。
- Notes: GitHub 未检测到许可文件（未注明许可）。README 提醒多数源数据集不允许再分发。最近推送 2026-10-25。

### liuskywalkerjskd/supermimic_oli
- Link: https://github.com/liuskywalkerjskd/supermimic_oli
- Category: 控制 / 世界模型 / 动作跟踪 / 重定向
- Robot Type: 人形（LimX Oli HU_D04_01，31 自由度；保留 Unitree G1 支持）
- Simulator: Isaac Lab 3（kit-less，MuJoCo-Warp）
- Deploy: 仿真
- Summary: 基于 SuperMimic 复现版本（zita-ch/supermimic_vibed）的非官方移植，适配 LimX Oli 人形，补充了 Oli 的动作预处理、IK 重定向配置和完整 rollout 导出。
- Notes: 作者报告：单个 Oli 策略跟踪 40 段 LAFAN1 动作，归一化回报 0.6783，40 段中 36 段全程未触发终止，在一张 RTX 4090 上训练约 2.2 小时。MIT 许可；2026-10-23 创建。是对 repos.md 和 2026-10-26 草稿中已收录的 SuperMimic 复现的补充。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### Lite Kimodo Dataset
- Link: https://huggingface.co/datasets/Berkeley-Humanoids/Lite-Kimodo-Dataset
- Category: 优化/生成动作 / 机器人动作
- Subject: Berkeley Lite Pro 人形（由仿真 Unitree G1 片段重定向而来）
- Content: 据数据卡，包含 9,490 段单动作片段（约 10 小时）、9,947 段长时序片段（约 54 小时）和 9,941 段长时序片段（约 118 小时），均为 50 Hz，每段都与其 G1 源片段放在一起。
- Format: Rerun `.rrd`（分层存储：G1 源关节与身体位姿、重定向后的 Lite Pro 关节与身体目标），另有供浏览 Space 使用的 web 数据包
- Access: 公开
- License: Apache-2.0（数据卡声明，称继承自 cagataydev 的 Kimodo G1 数据集）
- Summary: 由文本生成、重定向到开源小型人形的大规模动作数据集；目标位姿已表示在机器人自身连杆坐标系下，可直接用于跟踪奖励。
- Notes: 这不是动作捕捉数据：动作先由 NVIDIA Kimodo 模型生成，再由跟踪策略在仿真 G1 上执行，最后重定向。再分发前请核对上游 Kimodo 模型的条款。2026-10-12 创建，今日首次收录。配套的 Lite-LAFAN1 数据集为私有。

### Asimov Locomotion Benchmark
- Link: https://huggingface.co/datasets/yipjiaqi/asimov-locomotion-bench
- Category: 基准
- Subject: Menlo Asimov 1 人形（速度指令运动策略）
- Content: 65 个带随机种子的 MuJoCo 场景：13 个运动、20 个站立受推、16 个行走受推、4 个持续推力、4 个低摩擦、1 个 100 m 绕圈，以及 7 个地形测试（台阶、斜坡、散落箱体、粗糙地砖），地形测试须到达终点区才算成功。
- Format: JSONL 测试定义 + YAML 基准与评测配置
- Access: 公开
- License: BSD-3-Clause（数据卡元数据）
- Summary: 面向人形速度跟踪策略的可复现鲁棒性基准，通过 Cyclotron 运行，结果可选择提交到策略所在的 Hub 仓库。
- Notes: 2026-10-23 由个人 Hugging Face 账号创建，引用了 Menlo 官方的 Cyclotron 和 asimov-1 仓库；未核实是否获 Menlo 官方认可。内容是场景规格，不包含录制的轨迹。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Menlo Research / Asimov（既有条目更新）
- Institution: Menlo Research
- Homepage: https://www.menlo.ai/
- GitHub: https://github.com/menloresearch
- Lab / Department: Applied R&D / Asimov / Cyclotron 运动团队
- Key Topics: 开源人形 / 双足运动 / 强化学习 / AMP / 基准测试 / sim-to-real
- Notes: 原条目记录运动策略“尚待发布”，现需更新：Cyclotron 已公开 Asimov-1 运动策略的训练、导出与基准代码，并附 sim-to-real 演示；Hugging Face 上也已有公开的 65 场景基准。

### Dynamic Legged Systems Lab / IIT（既有条目更新）
- Institution: 意大利技术研究院（Istituto Italiano di Tecnologia）
- GitHub: https://github.com/iit-DLSLab
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: 四足 / 腿足操作 / 视觉-语言-动作 / 实机部署
- Notes: 新的来源信号：Semini、Barasuol、Turrisi 和 Amatucci 合著了 Go2 + Piper 的 VLA 部署研究（arXiv:2610.32271），表明该实验室在容错运动之外，开始做基于学习的移动操作。

### Berkeley Humanoids（组织信号）
- Institution: 加州大学伯克利分校（据 GitHub 组织简介：“a team at UC Berkeley aiming to build full-stack humanoid platform”）
- GitHub: https://github.com/Berkeley-Humanoids
- Key Topics: 人形 / Berkeley Lite 硬件 / 动作重定向 / 动作数据集
- Notes: 该组织现已发布 Lite Pro 的重定向工具、Hugging Face 动作数据集和动作浏览 Space；此前只在 2026-08-10 草稿中以构建基础设施仓库出现。学生及代表作待核实，暂不列出。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日没有新的已核实招聘信号。已查看 EPFL BioRob 的人形神经力学博士/博士后职位，官方页面现已标注关闭；该职位未收录在 jobs.md 中，无需删除。提醒：2026-10-26 草稿中奥胡斯大学 A3 Lab 的 Physical AI 博士岗位将于 2026-11-01 截止。

</details>
