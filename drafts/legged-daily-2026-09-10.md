**English** | [中文](../zh/drafts/legged-daily-2026-09-10.md)
# Legged Daily - 2026-09-10

## Summary
- A physics-grounded granular-contact simulator enables a humanoid locomotion policy to transfer across basalt, dry sand, and beach sand in hardware experiments.
- ViBe adapts a pretrained motion tracker into visually perceptive whole-body controllers with parameter-efficient post-training and zero-shot sim-to-real results across four tasks.
- TANGO treats cluttered humanoid navigation as continuous whole-body control, mapping language and egocentric RGB directly to 29-DoF actions and transferring zero-shot to a Unitree G1.
- DEEP Robotics has refreshed a connected open-source stack spanning motion retargeting, imitation-policy training, and broader Isaac Lab reinforcement-learning/deployment workflows.
- No sufficiently specific, high-confidence new legged-robotics job posting was selected today from the official sources checked.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Terrain-Adaptive Humanoid Locomotion on Granular Terrain
- Link: https://arxiv.org/abs/2609.10286
- Source: arXiv
- Date: 2026-09-09
- Authors: Junnosuke Kamohara, Feiyang Wu, Andy Ningan Zong, Daniel I. Goldman, Yashwanth Nakka, Seth Hutchinson, Ye Zhao
- Topics: humanoid locomotion / granular terrain / reinforcement learning / sim-to-real / terrain adaptation
- Summary: Introduces an efficient granular-contact model based on 3D resistive force theory and a teacher-student locomotion controller that identifies and adapts to terrain conditions, with hardware validation on basalt, dry sand, and beach sand.
- Notes: [Project page](https://humanoid-gm-locomotion.github.io/HUMANOID-GM/). The project page currently marks code as “Coming Soon”; it should not yet be treated as released.

### ViBe: Visual Behavior Adaptation for Perceptive Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2609.09918
- Source: arXiv
- Date: 2026-09-09
- Authors: Lokesh Krishna, Sarvesh Venkatesan, An Zhang, Quan Nguyen
- Topics: humanoid / perceptive whole-body control / motion tracking / visual adaptation / sim-to-real
- Summary: Presents a post-training framework that uses pretrained visual features, a multi-query extractor, and low-rank policy adapters to convert motion trackers into perceptive controllers, demonstrating zero-shot hardware transfer for terrain traversal, parkour, object manipulation, and dodgeball.
- Notes: [Project page](https://lok-i.github.io/vibe-control/).

### TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body Vision-Language-Action Model
- Link: https://arxiv.org/abs/2609.09158
- Source: arXiv / CoRL 2026
- Date: 2026-09-08
- Authors: Anqi Li, Yuxin Chen, Zhaobo Li, Zhuo Cao, Junli Ren, Masayoshi Tomizuka, Dhruv Shah
- Topics: humanoid navigation / vision-language-action / whole-body control / obstacle negotiation / sim-to-real
- Summary: Introduces a whole-body VLA system that predicts 29-DoF actions from language and egocentric RGB, using simulation-generated traversal supervision and zero-shot deployment on a Unitree G1 in cluttered real environments.
- Notes: [Project page](https://tango-vla.github.io/). The deployment separates low-frequency VLA inference on a server from a high-frequency onboard motion tracker.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### DeepRoboticsLab/deep-robotics-mimic
- Link: https://github.com/DeepRoboticsLab/deep-robotics-mimic
- Category: RL / imitation learning / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / Isaac Sim / MuJoCo viewer
- Deploy: both
- Summary: Trains PPO motion-tracking policies for DR02 Pro with DeepMimic-style rewards, supporting retargeted motion conversion, single- and multi-GPU training, evaluation, ONNX export, and deployment through the DEEP Robotics SDK.
- Notes: BSD-3-Clause. Updated 2026-09-09; its data pipeline explicitly consumes outputs from `deep-robotics-retarget`.

### DeepRoboticsLab/deep-robotics-retarget
- Link: https://github.com/DeepRoboticsLab/deep-robotics-retarget
- Category: retargeting / toolkit / viewer
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: data
- Summary: Retargets SMPL-X, BVH, and other human-motion sources to DR02 Pro joint trajectories using two-stage inverse kinematics, with optional collision avoidance, batch processing, and real-time visualization.
- Notes: BSD-3-Clause; modified from GMR. Updated 2026-09-08 and designed as the upstream motion-data stage for `deep-robotics-mimic`.

### DeepRoboticsLab/rl_training
- Link: https://github.com/DeepRoboticsLab/rl_training
- Category: RL / toolkit
- Robot Type: humanoid / quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: both
- Summary: Provides RSL-RL-based training environments and deployment-oriented tooling for Lite3 and M20 quadrupeds and the DR02 humanoid, including multi-GPU training, checkpoint comparison, tutorials, and ONNX export.
- Notes: BSD-3-Clause. Updated 2026-09-08; the repository documents separate deployment repositories for simulation and real robots.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### DEEP Robotics Lab
- Institution: DEEP Robotics
- Homepage: https://www.deeprobotics.cn/
- GitHub: https://github.com/DeepRoboticsLab
- Lab / Department: Official open-source engineering organization
- Key Topics: humanoid / quadruped / locomotion / reinforcement learning / imitation learning / deployment
- Notes: Recent coordinated updates expose a clearer DR02 Pro workflow: human-motion retargeting with `deep-robotics-retarget`, PPO reference-motion tracking with `deep-robotics-mimic`, and broader Isaac Lab training for DR02, Lite3, and M20 through `rl_training`. This is one connected tooling signal rather than three independent lab announcements.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently specific, currently actionable new legged-robotics opening was selected today from the official careers sources checked. General careers pages without a verifiable role, location, or active posting were omitted rather than inferred.

</details>
