[English](../../drafts/user-suggested-legged-reading-2026-06-13.md) | **中文**
# 用户指定腿足阅读队列 - 2026-06-13

## 用途
记录用户发来的论文与来源，供后续精读，并视情况纳入未来 `legged-daily` 草稿或 master lists。

## 高优先级阅读笔记

### Multi-Critic Actor Learning, ICLR 2022
- Link: TBD
- Priority: high
- User focus: 理解 multi-critic actor learning 的基本思想。
- Follow-up: 对比 critic decomposition / reward-channel separation 与 locomotion reward design 的关系。

### RobotKeyframing, CoRL 2025 / PMLR
- Link: TBD
- Priority: high
- User focus: 最贴近 PUMA 的 dense + sparse locomotion reward 参考。
- Follow-up: 如果能拿到全文，抽取 dense / sparse reward terms 与 keyframing 结构。

### Multi-critic Learning for Whole-body End-effector Twist Tracking, 2025
- Link: TBD
- Priority: high
- User focus: 看真实机器人多目标控制里的 multi-critic 用法。
- Follow-up: 梳理 critics / objectives 如何对应 whole-body end-effector twist tracking 与真实机器人部署。

### HoST, RSS 2025
- Link: TBD
- Priority: medium-high
- User focus: 看 humanoid 系统级应用。
- Follow-up: 提取系统架构、policy stack 和真实 humanoid 集成点。

## 用户指定来源 / 论文

### Awesome Humanoid Robot Learning
- Link: https://github.com/YanjieZe/awesome-humanoid-robot-learning
- Type: curated repository / paper list
- Relevance: 强；适合作为 humanoid learning 论文聚合源，尤其偏真实机器人与开源代码工作。
- Follow-up: 作为 aggregator source 持续监控；日报中只筛高信号条目，避免整表搬运。

### PUMA: Perception-driven Unified Foothold Prior for Mobility Augmented Quadruped Parkour
- Link: https://arxiv.org/abs/2601.15995
- Date: 2026-01-22
- Type: quadruped parkour / visual perception / foothold prior
- Relevance: 高；PUMA 核心参考，面向离散复杂地形的 perception-driven foothold prior。
- Follow-up: 精读 reward design 与训练流程；重点和 RobotKeyframing 的 reward 结构对照。

### START: Traversing Sparse Footholds with Terrain Reconstruction
- Link: https://arxiv.org/abs/2512.13153
- Date: 2025-12-15
- Type: quadruped sparse footholds / terrain reconstruction / onboard vision
- Relevance: 高；与 PUMA 同属 sparse/discrete foothold 主题，但走显式局部地形重建路线。
- Follow-up: 对比 explicit heightmap reconstruction 与 PUMA 的 egocentric polar foothold prior。

### Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching
- Link: https://arxiv.org/abs/2602.15827
- Date: 2026-02
- Type: humanoid parkour / motion matching / depth-based multi-skill policy
- Relevance: 高；是 parkour-style legged agility 在 humanoid 侧的重要对应工作，强调 human-skill chaining。
- Follow-up: 检查 motion matching、DAgger + RL distillation，以及 perception-driven skill selection。

### ContactGaussian-WM: Learning Physics-Grounded World Model from Videos
- Link: https://arxiv.org/abs/2602.11021
- Date: 2026
- Type: physics-grounded world model / contact-rich dynamics / video learning
- Relevance: 中；偏 contact-rich planning / MPC 的相邻 world-model 参考，不是直接腿足，但对接触建模有价值。
- Follow-up: 仅在关联 loco-manipulation、contact-rich humanoid manipulation 或 model-based legged planning 时纳入日报主线。

### PIN-WM: Learning Physics-INformed World Models for Non-Prehensile Manipulation
- Link: https://arxiv.org/abs/2504.16693
- Date: 2025
- Type: physics-informed world model / non-prehensile manipulation / differentiable physics
- Relevance: 中；相邻 manipulation world-model 工作，对 contact-rich planning 有参考价值，但不属于核心腿足 locomotion。
- Follow-up: 和 ContactGaussian-WM、ContactSDF 对比 differentiable-physics identification 思路。

### ContactSDF: Signed Distance Functions as Multi-Contact Models for Dexterous Manipulation
- Link: https://arxiv.org/abs/2408.09612
- Project / code: https://github.com/asu-iris/ContactSDF
- Date: 2024
- Type: contact model / SDF / differentiable multi-contact dynamics
- Relevance: 中；是 manipulation / whole-body contact 的接触模型参考，不是直接 locomotion。
- Follow-up: 作为 contact-rich humanoid manipulation 或 world-model 背景材料使用。

### High-speed control and navigation for quadrupedal robots on complex and discrete terrain
- Link: https://arxiv.org/abs/2506.02835
- Project: https://awesomericky.github.io/projects/Quadruped_parkour/index.html
- Type: quadruped high-speed navigation / complex discrete terrain
- Relevance: 高；贴近 quadruped parkour 与 sparse foothold traversal。
- Follow-up: 检查 navigation/control decomposition、真实速度与地形假设。

## 2026-06-17 用户补充：多技能运动 / 人形 loco-manipulation

### Discovery of skill-switching criteria for learning agile quadruped locomotion
- Link: https://arxiv.org/abs/2502.06676
- Date: 2025-02-10
- Venue / status: Frontiers in Robotics and AI, 2026 / arXiv 2025
- Best Paper: No confirmed
- Type: 四足敏捷运动 / 技能切换 / 强化学习
- Relevance: 高；直接对应 locomotion skills 之间“何时切换”的判据学习。
- Follow-up: 精读 switching criteria 建模，并与 mixture-of-experts / hierarchical skill selection 对照。

### MoE-Loco: Mixture of Experts for Multitask Locomotion
- Link: https://arxiv.org/abs/2503.08564
- Date: 2025-03-11
- Venue / status: IROS 2025 / arXiv 2025
- Best Paper: No confirmed
- Type: 多任务运动 / mixture of experts / robot learning
- Relevance: 高；是 locomotion 中 expert specialization 与 routing 的强参考。
- Follow-up: 提取 gating/routing 设计、任务覆盖范围和 sim-to-real 假设。

### MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots
- Link: https://arxiv.org/abs/2605.13058
- Date: 2026-05-13
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: 轮足机器人 / 多技能统一控制 / Unitree Go2-W
- Relevance: 已在日报 / master lists 跟踪；这里保留在用户指定主题簇中。
- Follow-up: 和 MoE-Loco、skill-switching 论文一起复看，用于统一多技能控制器设计。

### Learning Multi-Skill Legged Locomotion Using Conditional Adversarial Motion Priors
- Link: https://arxiv.org/abs/2509.21810
- Date: 2025-09-26
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: 多技能腿足运动 / conditional AMP / 模仿学习
- Relevance: 高；把 multi-skill locomotion 与 conditional adversarial motion priors 连接起来。
- Follow-up: 检查条件表示、AMP discriminator 设计和技能库构建方式。

### BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion
- Link: https://arxiv.org/abs/2508.08241
- Date: 2025-08-11
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: 人形控制 / motion tracking / guided diffusion
- Relevance: 高；是从 motion tracking 走向更通用人形行为的重要桥接工作。
- Follow-up: 将 guided diffusion 阶段与 ResMimic、SkillBlender 等 residual/adaptation 方法对照。

### SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2511.07820
- Date: 2025-11-11
- Venue / status: Science Robotics, 2026
- Best Paper: N/A
- Type: 人形全身控制 / motion tracking / 大规模数据
- Relevance: 高；NVIDIA GEAR/SONIC 方向的重要自然人形 motion tracking 参考。
- Follow-up: 与现有 SONIC/GEAR 仓库条目关联，整理数据规模化和 actuator modeling 选择。

### HoloMotion-1 Technical Report
- Link: https://arxiv.org/abs/2605.15336
- Date: 2026-05-14
- Venue / status: arXiv Technical Report, 2026
- Best Paper: N/A
- Type: 人形动作 / 技术报告 / 全身学习
- Relevance: 中高；可作为 motion data 或 whole-body control 参考。
- Follow-up: 核查项目资产、数据/代码可用性，以及它和 SONIC/BeyondMimic 式 tracking 的区别。

### SkillBlender: Towards Versatile Humanoid Whole-Body Loco-Manipulation via Skill Blending
- Link: https://arxiv.org/abs/2506.09366
- Date: 2025-06-11
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: 人形 loco-manipulation / skill blending / 全身控制
- Relevance: 高；直接对应 locomotion 与 manipulation skills 的组合。
- Follow-up: 检查 blending 机制、技能库假设和真实/仿真验证。

### ResMimic: From General Motion Tracking to Humanoid Whole-Body Loco-Manipulation via Residual Learning
- Link: https://arxiv.org/abs/2510.05070
- Date: 2025-10-06
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: 人形 loco-manipulation / residual learning / motion tracking
- Relevance: 高；是把通用 tracking policy 变成移动操作能力的强对照参考。
- Follow-up: 对比 residual policy 设计与 BeyondMimic guided diffusion、SkillBlender skill composition。

### SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework
- Link: https://arxiv.org/abs/2605.20373
- Date: 2026-05-19
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: 人形 loco-manipulation / 人类视频 / 可扩展技能学习
- Relevance: 已在日报 / master lists 跟踪；这里保留在用户指定主题簇中。
- Follow-up: 构建 human-video-driven loco-manipulation 阅读路径时复看。

### WholeBodyVLA: Towards Unified Latent VLA for Whole-Body Loco-Manipulation Control
- Link: https://arxiv.org/abs/2512.11047
- Date: 2025-12-11
- Venue / status: ICLR 2026 Poster
- Best Paper: No confirmed
- Type: 人形 whole-body VLA / latent actions / loco-manipulation
- Relevance: 高；是 whole-body humanoid loco-manipulation 的 VLA-style 核心参考。
- Follow-up: 与现有 WholeBodyVLA 仓库/资源条目关联，检查 benchmark / task definitions。

### Learning a Unified Policy for Position and Force Control in Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2505.20829
- Date: 2025-05-27
- Venue / status: CoRL 2025
- Best Paper: Yes, CoRL 2025 Best Paper
- Type: 腿足 loco-manipulation / position-force control / unified policy
- Relevance: 很高；用户明确标注 Best Paper，也是 force-control loco-manipulation 核心参考。
- Follow-up: 优先精读 position/force objective 结构和真实机器人证据。

### ULC: A Unified and Fine-Grained Controller for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2507.06905
- Date: 2025-07-09
- Venue / status: arXiv 2025 / in submission
- Best Paper: N/A
- Type: 人形 loco-manipulation / fine-grained whole-body controller
- Relevance: 高；补足 SkillBlender、ResMimic、WholeBodyVLA 这一组 unified controller 方向。
- Follow-up: 检查 controller granularity、command/action interface 和 manipulation task suite。

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Date: 2026-06-04
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: 人形 loco-manipulation / motion discovery / LLM-guided search / kinodynamic optimization
- Relevance: 已在日报草稿跟踪；这里保留在用户指定主题簇中。
- Follow-up: 作为 automated skill-discovery 路线复看，重点和 human-video / motion-tracking-based 方法对比。

## 2026-06-29 用户补充：腿足里程计 / 状态估计 / 研究者信号

### Online Learning of Robust Legged Odometry with Minimal Exteroceptive Supervision
- Link: https://arxiv.org/abs/2606.21669
- Date: 2026-06-19
- Venue / status: arXiv 2026
- Type: 腿足里程计 / 在线学习 / 本体感知 / 外感知监督 / InEKF
- Authors: Abhijeet M. Kulkarni, Yuze Du, Guoquan Huang
- Relevance: 高；直接面向可部署腿足里程计，在外感知退化时可切换到在线学习得到的本体速度模型。
- Follow-up: 和 2026 年 3 月 set-coverage 状态估计论文，以及传统 visual-inertial / 腿足运动学融合路线对照。

### Proprioceptive-only State Estimation for Legged Robots with Set-Coverage Measurements of Learned Dynamics
- Link: https://arxiv.org/abs/2603.18308
- Date: 2026-03-18
- Venue / status: arXiv 2026
- Type: 纯本体状态估计 / learned dynamics / set coverage / Gaussian filtering / 四足数据集
- Authors: Abhijeet M. Kulkarni, Ioannis Poulakakis, Guoquan Huang
- Relevance: 高；用 set-coverage statements 替代 learned measurement 的高斯噪声假设，补足 robust odometry 方向中的一致性与抗漂移问题。
- Follow-up: 精读 set-coverage measurement 的构造方式，以及它如何在真实噪声下与 Gaussian filter 融合。

### Guoquan (Paul) Huang
- Homepage: https://udel.edu/~ghuang/
- Google Scholar: https://scholar.google.com/citations?user=trMUyZIAAAAJ&hl=en
- Institution: University of Delaware
- Type: 研究者 / 实验室信号
- Key Topics: 机器人状态估计 / SLAM / 视觉惯性导航 / 腿足里程计 / 概率感知
- Relevance: 高；是用户指定两篇腿足里程计 / 状态估计论文的共同作者，适合作为鲁棒估计方法迁移到腿足机器人的跟踪源。
- Follow-up: 跟踪其团队把 VINS、免标定估计或 learned measurements 接到腿足平台的后续工作。

### Mingyu Ding
- Homepage: https://dingmyu.github.io/
- Google Scholar: https://scholar.google.com/citations?user=w4yTWwoAAAAJ&hl=en
- Institution: University of North Carolina at Chapel Hill / IDEAL@UNC
- Type: 研究者 / 实验室信号
- Key Topics: 机器人学习 / embodied AI / 人形 loco-manipulation / VLAs / real-to-sim-to-real / 灵巧操作
- Relevance: 对 humanoid 与 whole-body robot learning 高相关；其主页明确列出 humanoid loco-manipulation、VLAs、latent actions、real-to-sim-to-real 等方向。
- Follow-up: 持续监控 IDEAL@UNC 在 humanoid loco-manipulation、VLA 与 robot learning 方向的新论文，筛入后续 Legged Daily。

## 未加入腿足跟踪

### Telegram: @oci_helper
- Link: https://t.me/oci_helper
- Reason: 看起来是 OCI helper / 云资源放货通知频道，不是腿足机器人来源。
- Decision: 暂不加入 legged robotics source watchlist；除非用户说明这是给另一个任务用的。
