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

## 未加入腿足跟踪

### Telegram: @oci_helper
- Link: https://t.me/oci_helper
- Reason: 看起来是 OCI helper / 云资源放货通知频道，不是腿足机器人来源。
- Decision: 暂不加入 legged robotics source watchlist；除非用户说明这是给另一个任务用的。
