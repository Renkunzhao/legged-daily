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

## 2026-06-17 user additions: multi-skill locomotion / humanoid loco-manipulation

### Discovery of skill-switching criteria for learning agile quadruped locomotion
- Link: https://arxiv.org/abs/2502.06676
- Date: 2025-02-10
- Venue / status: Frontiers in Robotics and AI, 2026 / arXiv 2025
- Best Paper: No confirmed
- Type: quadruped agile locomotion / skill switching / reinforcement learning
- Relevance: high; directly relevant to choosing when to switch among locomotion skills.
- Follow-up: read the switching-criteria formulation and compare with mixture-of-experts or hierarchical skill selection.

### MoE-Loco: Mixture of Experts for Multitask Locomotion
- Link: https://arxiv.org/abs/2503.08564
- Date: 2025-03-11
- Venue / status: IROS 2025 / arXiv 2025
- Best Paper: No confirmed
- Type: multitask locomotion / mixture of experts / robot learning
- Relevance: high; strong reference for expert specialization and routing in locomotion.
- Follow-up: extract gating/routing design, task coverage, and sim-to-real assumptions.

### MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots
- Link: https://arxiv.org/abs/2605.13058
- Date: 2026-05-13
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: wheeled-legged robots / multi-skill unified control / Unitree Go2-W
- Relevance: already tracked in daily/master lists; keep as part of this user-specified cluster.
- Follow-up: revisit alongside MoE-Loco and skill-switching papers for unified multi-skill controller design.

### Learning Multi-Skill Legged Locomotion Using Conditional Adversarial Motion Priors
- Link: https://arxiv.org/abs/2509.21810
- Date: 2025-09-26
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: multi-skill legged locomotion / conditional AMP / imitation learning
- Relevance: high; connects multi-skill locomotion with conditional adversarial motion priors.
- Follow-up: inspect condition representation, AMP discriminator design, and task/skill library construction.

### BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion
- Link: https://arxiv.org/abs/2508.08241
- Date: 2025-08-11
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: humanoid control / motion tracking / guided diffusion
- Relevance: high; useful bridge from motion tracking toward more versatile humanoid behaviors.
- Follow-up: compare guided diffusion stage with residual/adaptation approaches such as ResMimic and SkillBlender.

### SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2511.07820
- Date: 2025-11-11
- Venue / status: Science Robotics, 2026
- Best Paper: N/A
- Type: humanoid whole-body control / motion tracking / large-scale data
- Relevance: high; important NVIDIA GEAR/SONIC reference for natural humanoid motion tracking.
- Follow-up: keep linked with the existing SONIC/GEAR repository entry and summarize data scaling + actuator modeling choices.

### HoloMotion-1 Technical Report
- Link: https://arxiv.org/abs/2605.15336
- Date: 2026-05-14
- Venue / status: arXiv Technical Report, 2026
- Best Paper: N/A
- Type: humanoid motion / technical report / whole-body learning
- Relevance: medium-high; likely useful as a motion-data or whole-body-control reference.
- Follow-up: verify project assets, data/code availability, and how it differs from SONIC/BeyondMimic-style tracking.

### SkillBlender: Towards Versatile Humanoid Whole-Body Loco-Manipulation via Skill Blending
- Link: https://arxiv.org/abs/2506.09366
- Date: 2025-06-11
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: humanoid loco-manipulation / skill blending / whole-body control
- Relevance: high; directly relevant to combining locomotion and manipulation skills.
- Follow-up: inspect blending mechanism, skill library assumptions, and real/sim validation.

### ResMimic: From General Motion Tracking to Humanoid Whole-Body Loco-Manipulation via Residual Learning
- Link: https://arxiv.org/abs/2510.05070
- Date: 2025-10-06
- Venue / status: arXiv 2025
- Best Paper: N/A
- Type: humanoid loco-manipulation / residual learning / motion tracking
- Relevance: high; strong comparison point for turning general tracking policies into manipulation-capable humanoid controllers.
- Follow-up: compare residual policy design against BeyondMimic guided diffusion and SkillBlender skill composition.

### SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework
- Link: https://arxiv.org/abs/2605.20373
- Date: 2026-05-19
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: humanoid loco-manipulation / human video / scalable skill learning
- Relevance: already tracked in daily/master lists; keep as part of this user-specified cluster.
- Follow-up: revisit when building a human-video-driven loco-manipulation reading path.

### WholeBodyVLA: Towards Unified Latent VLA for Whole-Body Loco-Manipulation Control
- Link: https://arxiv.org/abs/2512.11047
- Date: 2025-12-11
- Venue / status: ICLR 2026 Poster
- Best Paper: No confirmed
- Type: humanoid whole-body VLA / latent actions / loco-manipulation
- Relevance: high; central VLA-style reference for whole-body humanoid loco-manipulation.
- Follow-up: connect the paper to the existing WholeBodyVLA repository/resource entry and check benchmark/task definitions.

### Learning a Unified Policy for Position and Force Control in Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2505.20829
- Date: 2025-05-27
- Venue / status: CoRL 2025
- Best Paper: Yes, CoRL 2025 Best Paper
- Type: legged loco-manipulation / position-force control / unified policy
- Relevance: very high; user explicitly marked Best Paper and it is a core force-control loco-manipulation reference.
- Follow-up: prioritize for detailed notes on force/position objective structure and real-robot evidence.

### ULC: A Unified and Fine-Grained Controller for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2507.06905
- Date: 2025-07-09
- Venue / status: arXiv 2025 / in submission
- Best Paper: N/A
- Type: humanoid loco-manipulation / fine-grained whole-body controller
- Relevance: high; complements SkillBlender, ResMimic, and WholeBodyVLA in unified controller design.
- Follow-up: inspect controller granularity, command/action interface, and manipulation task suite.

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Date: 2026-06-04
- Venue / status: arXiv 2026
- Best Paper: N/A
- Type: humanoid loco-manipulation / motion discovery / LLM-guided search / kinodynamic optimization
- Relevance: already tracked in daily drafts; keep as part of this user-specified cluster.
- Follow-up: revisit for the automated skill-discovery route, especially compared with human-video or motion-tracking-based methods.

## 2026-06-29 user additions: legged odometry / state estimation / researcher signals

### Online Learning of Robust Legged Odometry with Minimal Exteroceptive Supervision
- Link: https://arxiv.org/abs/2606.21669
- Date: 2026-06-19
- Venue / status: arXiv 2026
- Type: legged odometry / online learning / proprioception / exteroceptive supervision / InEKF
- Authors: Abhijeet M. Kulkarni, Yuze Du, Guoquan Huang
- Relevance: high; directly targets deployable legged odometry that can fall back from degraded exteroception to an online-learned proprioceptive velocity model.
- Follow-up: compare with the March 2026 set-coverage state-estimation paper and with classical visual-inertial / legged kinematic fusion pipelines.

### Proprioceptive-only State Estimation for Legged Robots with Set-Coverage Measurements of Learned Dynamics
- Link: https://arxiv.org/abs/2603.18308
- Date: 2026-03-18
- Venue / status: arXiv 2026
- Type: proprioceptive-only state estimation / learned dynamics / set coverage / Gaussian filtering / quadruped datasets
- Authors: Abhijeet M. Kulkarni, Ioannis Poulakakis, Guoquan Huang
- Relevance: high; complements robust odometry by replacing Gaussian learned-measurement assumptions with set-coverage statements for more consistent proprioceptive-only legged state estimation.
- Follow-up: read the set-coverage measurement construction and note how it is fused with Gaussian filters under real noise.

### Guoquan (Paul) Huang
- Homepage: https://udel.edu/~ghuang/
- Google Scholar: https://scholar.google.com/citations?user=trMUyZIAAAAJ&hl=en
- Institution: University of Delaware
- Type: researcher / lab signal
- Key Topics: robotics state estimation / SLAM / visual-inertial navigation / legged odometry / probabilistic perception
- Relevance: high; coauthor on both user-specified legged odometry / state-estimation papers and a useful source for robust estimation methods transferable to legged robots.
- Follow-up: track publications from his group that connect VINS, calibration-free estimation, or learned measurements to legged platforms.

### Mingyu Ding
- Homepage: https://dingmyu.github.io/
- Google Scholar: https://scholar.google.com/citations?user=w4yTWwoAAAAJ&hl=en
- Institution: University of North Carolina at Chapel Hill / IDEAL@UNC
- Type: researcher / lab signal
- Key Topics: robot learning / embodied AI / humanoid loco-manipulation / VLAs / real-to-sim-to-real / dexterous manipulation
- Relevance: high for humanoid and whole-body robot learning; his lab page explicitly lists humanoid loco-manipulation, VLAs, latent actions, and real-to-sim-to-real as active directions.
- Follow-up: monitor IDEAL@UNC outputs for humanoid loco-manipulation, VLA, and robot-learning papers that fit future Legged Daily selections.

## Not added to legged tracking

### Telegram: @oci_helper
- Link: https://t.me/oci_helper
- Reason: appears to be an OCI helper / cloud stock-notification channel, not a legged robotics source.
- Decision: do not add to legged robotics source watchlist unless the user says this was intentional for another task.
