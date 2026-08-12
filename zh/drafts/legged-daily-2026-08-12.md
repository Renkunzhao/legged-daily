# 腿足机器人日报草稿 — 2026-08-12

状态：仅草稿；等待确认后才能合并到主列表。

## 今日摘要

- 两篇新 arXiv 论文达到收录标准：AECNav 在实体四足机器人 40 次实验中报告 95% 成功率、约 5 Hz 的训练免开放词汇目标导航；Hip Energized Monopedal Hopping 提出有解析依据的能量调节策略，并在 Penn Jerboa 上实现最高 1.77 m/s。
- 三个新建 GitHub 仓库值得早期查看：较完整的 MuJoCo 四足动作重定向工具、VIVE 到 GR00T Sonic / Unitree G1 的全身遥操作管线，以及紧凑的 G1 复杂地形 AMP-PPO 课程项目。
- 论文流给出了 Daniel Koditschek 团队腿足运动研究的持续信号；仓库流则显示 Unitree G1/Go2 周边正在形成更可复用的数据处理与部署工具链。
- 今天没有发现比现有跟踪集合更强、且可由官方来源确认的新职位。Amazon Robotics Compass 的 Safe Locomotion 官方岗位今日复核仍有效，继续等待是否加入主列表的确认。

## 新论文

### 1. AECNav: Active Evidence Consolidation for Efficient Zero-Shot Open-Vocabulary Object Navigation

- 作者：Guanlin Liu, Shaobin Ling, Renyuan Liu, Zeying Gong, Junjie Hu
- 日期：2026-08-11（arXiv v1）
- 链接：[arXiv](https://arxiv.org/abs/2608.10817)
- 摘要：这是一个训练免的零样本开放词汇目标导航管线。方法在各推理阶段共享视觉编码，以簇级 log-odds 累积证据，把“预期检测未出现”作为负证据，并主动选择信息增益高、代价低的探索前沿。摘要报告其在 HM3D-v2、HM3D-OVON、MP3D 上成功率分别为 84.7%、57.3%、51.3%，实体四足机器人 40 次实验成功率为 95%，运行频率约 5 Hz。
- 价值：它把开放词汇感知真正接入腿足平台的在线决策，同时正面处理延迟和相似干扰物导致的误确认。
- 注意：实体实验数据来自论文摘要；代码注明“录用后公开”，目前尚无代码链接。

### 2. Hip Energized Monopedal Hopping

- 作者：Shane Rozen-Levy, Griffon McMahon, Daniel Koditschek
- 日期：2026-08-11（arXiv v1）
- 链接：[arXiv](https://arxiv.org/abs/2608.10387)
- 摘要：论文利用俯仰稳定控制产生的反作用力矩，补偿俯仰自由平面单足机器人的阻尼能量损失；新的落脚策略在径向与角向自由度之间分配能量，混杂平均分析则给出不动点和特征值的闭式表达。Penn Jerboa 实验实现 1.02–1.77 m/s，即 5.10–8.85 个腿长每秒的稳定跳跃。
- 价值：这是少见的可解释运动控制工作，把控制器、能量机制、稳定性分析、仿真与硬件表现连在同一条证据链上。
- 注意：平台是平面单足机器人，论文没有展示对三维四足或人形机器人的直接迁移。

## 新仓库

### 1. Lain-Ego0/GQMR — General Quadruped Motion Retargeting

- 链接：https://github.com/Lain-Ego0/GQMR
- 创建 / 核验：2026-08-11 / 2026-08-12
- 快照：Python，MIT；核验时 4 stars、1 fork。
- 内容：以 MuJoCo 为统一后端的四足动作重定向工具，包含 motion schema、安全 NPZ I/O、GUI、流式录制、多目三角化、动作质量检查，以及 AMP / DeepMimic 导出。README 列出 Unitree Go2/Go1/A1/A2/B2、ANYmal C、云深处 Lite3 等内置模型。
- 价值：它试图补齐动物/人体姿态数据到腿足策略训练资产之间最繁琐的一段，并提供固定测试动作和跨机器人批量评估。
- 注意：这是非常新的个人仓库，未启用 CI，独立验证有限；复用前应检查打包模型资产及第三方数据的许可边界。

### 2. zhangwencong317/HTC_VIVE_Whole_Body_Tracking

- 链接：https://github.com/zhangwencong317/HTC_VIVE_Whole_Body_Tracking
- 创建 / 核验：2026-08-12 / 2026-08-12
- 快照：Python，Apache-2.0；核验时 1 star；示例数据另采用 CC BY-NC-SA 4.0。
- 内容：从 HTC VIVE trackers 经标定、Pinocchio IK 与 SMPL 打包接入 NVIDIA GR00T Sonic，支持 MuJoCo 回放和 Unitree G1 部署。仓库包含生产用 C++ bridge、样例录制、网络检查，以及明确的真机安全步骤。
- 价值：它公开了全身遥操作项目经常缺失的工程细节，包括 tracker 角色、标定、Windows/Linux 通信、Jetson 部署和离线回放。
- 注意：依赖兼容版本的 GR00T WholeBodyControl 和具体软硬件环境；README 声称支持真实 G1，但本轮未独立复现。

### 3. ytq0198/Unitree-G1

- 链接：https://github.com/ytq0198/Unitree-G1
- 创建 / 核验：2026-08-12 / 2026-08-12
- 快照：Python；核验时 2 stars，未检测到仓库许可证。
- 内容：面向程序生成复杂地形的 Unitree G1 课程项目，使用 AMP-PPO 和直接 29-DoF 关节动作，包含机体系下一航点观测、高度扫描或深度策略、平滑性/动作风格约束，以及多随机初始状态评估。
- 价值：仓库虽小，但训练、评估命令和模拟器扩展性测量写得较明确，可作为易读的 G1 地形导航基线参考。
- 注意：没有许可证，也未提交 checkpoint、视频、TensorBoard 日志或最终量化结果；应把它视为早期教学实现，而非已验证研究发布。

## 实验室 / 教授信号

### Penn Engineering / Kod*lab — Daniel Koditschek 与 Penn Jerboa

- 信号：新的 Penn Jerboa 论文延续了以混杂动力学、能量调节和实体硬件为核心的腿足运动研究路线。
- 为什么值得跟踪：对于关注端到端 RL 之外或与之互补的可解释方法，这一团队持续产出 templates / anchors、步态稳定性与控制器—机构协同设计方面的工作。
- 来源：https://arxiv.org/abs/2608.10387
- 注意：这是论文动态，不是新发布的招生或招聘通知。

### Unitree 相关开源集成活动

- 信号：同一天出现两个具体 G1 工作流——经 GR00T Sonic 的 VIVE 全身遥操作和 AMP-PPO 地形导航；GQMR 则面向多个四足平台构建可复用动作资产。
- 为什么值得跟踪：生态正在从孤立策略演示转向数据转换、回放、标定、评估和部署等可复用工具链。
- 注意：这些是早期社区发布，不是已确认的机构实验室公告。

## 招聘信号

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion

- 地点：美国加州 Pasadena
- 官方链接：https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 状态：2026-08-12 检查时官方页面仍有效；此前已提出，非今日新发现。
- 相关性：实体四足/人形 RL 部署、sim-to-real、形式化安全约束、全身控制、地形感知运动和失效模式分析。
- 注意：高级岗位，要求博士或较长应用研究经历，并要求多年实体机器人 RL 经验。

今天没有其他新发布机会同时满足官方来源和相关性门槛。

## 建议合并项——需要确认

- 是否将论文 1–2 加入 `papers.md` 和 `zh/papers.md`？
- 是否将仓库 1–3 加入 `repos.md` 和 `zh/repos.md`？
- 是否在 `labs.md` 和 `zh/labs.md` 中新增或加强 Penn Engineering / Daniel Koditschek 来源？
- 是否将持续跟踪的 Amazon Robotics Compass Safe Locomotion 岗位加入 `jobs.md` 和 `zh/jobs.md`？

请确认全部，或指定条目编号。当前未修改任何正式主列表。
