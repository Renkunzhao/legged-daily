**English** | [中文](../zh/drafts/user-suggested-legged-reading-2026-06-13.md)
# User-Suggested Legged Reading Queue - 2026-06-13

## Purpose
Capture papers and sources sent by the user for follow-up reading and possible insertion into future `legged-daily` drafts or master lists.

## High-priority reading notes

### Multi-Critic Actor Learning, ICLR 2022
- Link: TBD
- Priority: high
- User focus: understand the basic idea of multi-critic actor learning.
- Follow-up: compare critic decomposition / reward-channel separation against locomotion reward design.

### RobotKeyframing, CoRL 2025 / PMLR
- Link: TBD
- Priority: high
- User focus: closest reference to PUMA-style dense + sparse locomotion rewards.
- Follow-up: extract dense / sparse reward terms and keyframing structure if full text is available.

### Multi-critic Learning for Whole-body End-effector Twist Tracking, 2025
- Link: TBD
- Priority: high
- User focus: how multi-objective control is used on real robots.
- Follow-up: map critics / objectives to whole-body end-effector twist tracking and real-robot deployment details.

### HoST, RSS 2025
- Link: TBD
- Priority: medium-high
- User focus: humanoid system-level application.
- Follow-up: identify system architecture, policy stack, and real-world humanoid integration points.

## User-suggested sources / papers

### Awesome Humanoid Robot Learning
- Link: https://github.com/YanjieZe/awesome-humanoid-robot-learning
- Type: curated repository / paper list
- Relevance: strong source for humanoid learning papers, especially real-robot and code-released work.
- Follow-up: monitor as an aggregator source; avoid dumping broad lists into daily updates without filtering.

### PUMA: Perception-driven Unified Foothold Prior for Mobility Augmented Quadruped Parkour
- Link: https://arxiv.org/abs/2601.15995
- Date: 2026-01-22
- Type: quadruped parkour / visual perception / foothold prior
- Relevance: high; core PUMA reference for perception-driven foothold priors on discrete complex terrain.
- Follow-up: read reward design and training pipeline; compare against RobotKeyframing reward structure.

### START: Traversing Sparse Footholds with Terrain Reconstruction
- Link: https://arxiv.org/abs/2512.13153
- Date: 2025-12-15
- Type: quadruped sparse footholds / terrain reconstruction / onboard vision
- Relevance: high; same sparse/discrete foothold theme as PUMA, but uses explicit local terrain reconstruction.
- Follow-up: compare explicit heightmap reconstruction against PUMA's egocentric polar foothold prior.

### Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching
- Link: https://arxiv.org/abs/2602.15827
- Date: 2026-02
- Type: humanoid parkour / motion matching / depth-based multi-skill policy
- Relevance: high; humanoid counterpart to parkour-style legged agility, with human-skill chaining.
- Follow-up: inspect motion matching, DAgger + RL distillation, and perception-driven skill selection.

### ContactGaussian-WM: Learning Physics-Grounded World Model from Videos
- Link: https://arxiv.org/abs/2602.11021
- Date: 2026
- Type: physics-grounded world model / contact-rich dynamics / video learning
- Relevance: medium; adjacent world-model reference for contact-rich planning and MPC, not directly legged but useful for contact modeling.
- Follow-up: track only if connecting to loco-manipulation, contact-rich humanoid manipulation, or model-based legged planning.

### PIN-WM: Learning Physics-INformed World Models for Non-Prehensile Manipulation
- Link: https://arxiv.org/abs/2504.16693
- Date: 2025
- Type: physics-informed world model / non-prehensile manipulation / differentiable physics
- Relevance: medium; adjacent manipulation world-model paper, useful for contact-rich planning but outside core legged locomotion.
- Follow-up: compare differentiable-physics identification to ContactGaussian-WM and ContactSDF.

### ContactSDF: Signed Distance Functions as Multi-Contact Models for Dexterous Manipulation
- Link: https://arxiv.org/abs/2408.09612
- Project / code: https://github.com/asu-iris/ContactSDF
- Date: 2024
- Type: contact model / SDF / differentiable multi-contact dynamics
- Relevance: medium; contact modeling reference for manipulation and potentially humanoid whole-body contact, not direct locomotion.
- Follow-up: useful as background for contact-rich humanoid manipulation or world-model sections.

### High-speed control and navigation for quadrupedal robots on complex and discrete terrain
- Link: https://arxiv.org/abs/2506.02835
- Project: https://awesomericky.github.io/projects/Quadruped_parkour/index.html
- Type: quadruped high-speed navigation / complex discrete terrain
- Relevance: high; close to quadruped parkour and sparse foothold traversal.
- Follow-up: inspect navigation/control decomposition, real-world speed, and terrain assumptions.

## Not added to legged tracking

### Telegram: @oci_helper
- Link: https://t.me/oci_helper
- Reason: appears to be an OCI helper / cloud stock-notification channel, not a legged robotics source.
- Decision: do not add to legged robotics source watchlist unless the user says this was intentional for another task.
