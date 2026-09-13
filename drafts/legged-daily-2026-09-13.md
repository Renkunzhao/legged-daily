**English** | [中文](../zh/drafts/legged-daily-2026-09-13.md)
# Legged Daily - 2026-09-13

## Summary
- Actuator Dynamics Curricula turns simulated joint stiffness into a curriculum variable, enabling a Spot quadruped policy to learn a narrow-viability quadrupedal-to-handstand transition and transfer it to hardware.
- A morphology-aware retargeting pipeline maps general SMPL-X human motion onto the wheeled Galaxea R1 Pro, coupling planar base motion, torso substitution, arm tracking, and wheel command decoding.
- Frame-Coded Legged Locomotion develops a theoretical connection between rough-terrain contact loss and finite-frame erasure coding, deriving redundancy, reconstruction, and stiffness limits for multi-legged gaits.
- Two fresh repositories cover complementary entry points: a low-cost 12-DOF quadruped with CAD/URDF/Isaac Sim assets, and a MuJoCo PPO prototype with ONNX and ROS 2 inference scaffolding. Both remain early-stage and lack a selected license.
- Humanoid published an active Vancouver opening for a Senior Low-Level Control Engineer focused on actuator/joint control, real-time C++, ROS 2, EtherCAT/CAN, system identification, and physical robot bring-up.

<details>
<summary><strong>New Papers</strong></summary>

### Actuator Dynamics Curricula for Narrow-Viability Tasks in Legged Robot Learning
- Link: https://arxiv.org/abs/2609.09492
- Source: arXiv / CoRL 2026
- Date: 2026-09-08
- Authors: Kousheek Chakraborty, Chandan K. Rajendra, Ayham Alharbat, Abeje Y. Mersha
- Topics: quadruped learning / reinforcement learning / actuator dynamics / curriculum learning / sim-to-real
- Summary: Introduces an actuator-dynamics curriculum that begins with high simulated joint stiffness and anneals toward system-identified hardware values as episode completion improves, enlarging the initially explorable viability region for tasks dominated by early termination.
- Notes: The authors validate the mechanism on cart-pole viability analysis and a Boston Dynamics Spot quadrupedal-to-handstand transition, reporting successful simulation across ten seeds and hardware transfer. This is an author-reported result and was not independently reproduced in this run.

### Morphology-Aware Human Motion Retargeting for Wheeled-Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2609.11357
- Source: arXiv
- Date: 2026-09-10
- Authors: Chenbo Xia, Chao Ye
- Topics: wheeled humanoid / motion retargeting / loco-manipulation / differential inverse kinematics / reinforcement learning
- Summary: Converts multi-dataset SMPL-X motion into executable Galaxea R1 Pro behavior by redistributing human lower-body motion across a planar wheel base and serial torso while preserving manipulation-relevant arm geometry.
- Notes: The pipeline combines morphology-aware differential IK, shoulder-rooted arm retargeting, torso substitution, continuous wheel steering/rolling decoding, and an Isaac Lab BaseDecode policy. The authors explicitly defer quantitative policy comparisons to a later revision, so current evidence should be treated as a reproducible pipeline release rather than a complete benchmark.

### Frame-Coded Legged Locomotion over Noisy Terrain
- Link: https://arxiv.org/abs/2609.10273
- Source: arXiv
- Date: 2026-09-09
- Authors: Lav R. Varshney
- Topics: multi-legged locomotion / rough terrain / contact robustness / frame theory / information theory
- Summary: Models heterogeneous leg-ground contacts as coefficients of a finite-frame expansion subject to terrain-induced erasures and corruption, with compliant morphology acting as a contact-gated decoder for body-level commands.
- Notes: The paper derives minimax missing-contact frames, rate and reconstruction thresholds, noise amplification, stiffness margins, and an incremental-redundancy rule. It is a fundamental theory contribution based on analytical and linear-Gaussian models, not a reported physical-robot validation.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### hp0303/low-cost-quadruped-platform
- Link: https://github.com/hp0303/low-cost-quadruped-platform
- Category: hardware platform / robot description / deterministic control
- Robot Type: quadruped / custom 12-DOF platform
- Simulator: NVIDIA Isaac Sim 5.1
- Deploy: simulation assets plus assembled hardware prototype; physical control validation remains roadmap work
- Summary: Provides an accessible quadruped foundation built around commodity RC servos, including a complete STEP assembly, URDF and meshes, joint-mapping audits, configuration files, Isaac Sim import/validation scripts, and a deterministic crawl controller.
- Notes: Created 2026-09-11. The README carefully separates authored model values, simulation assumptions, and unverified hardware limits; BOM, printable manufacturing files, calibration, IMU-assisted gait, and learning control remain roadmap items. No license has been selected, so source visibility does not grant reuse rights.

### hasankara80/NeuroQuad-RL
- Link: https://github.com/hasankara80/NeuroQuad-RL
- Category: reinforcement learning / locomotion / deployment scaffolding
- Robot Type: quadruped / custom 8-DOF model
- Simulator: MuJoCo
- Deploy: simulation; ONNX export and ROS 2 Humble inference scaffolding, without validated hardware transfer
- Summary: Implements a compact end-to-end PPO locomotion prototype with a custom Gymnasium environment, mass and friction randomization, deterministic evaluation, checkpointing, ONNX actor export, Docker packaging, and a Python ROS 2 inference interface.
- Notes: Created 2026-09-10. The repository documents an early reward-hacking failure and subsequent termination/reward changes, which is useful for educational inspection, but it has no physical deployment evidence, zero stars at check time, and no detected license.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Saxion-led actuator-dynamics curriculum collaboration
- Institution: Saxion University of Applied Sciences / University of Groningen / University of Twente
- Homepage: https://arxiv.org/abs/2609.09492
- Key Topics: legged robot learning / actuator modeling / curriculum learning / sim-to-real / dynamic skills
- Notes: Kousheek Chakraborty, Chandan K. Rajendra, Ayham Alharbat, and Abeje Y. Mersha connect viability-kernel analysis with a hardware-transferred Spot handstand transition. This is a useful European applied-research signal at the boundary of actuator identification and reinforcement-learning curriculum design.

### Harbin Institute of Technology wheeled-humanoid retargeting team
- Institution: Harbin Institute of Technology
- Homepage: https://arxiv.org/abs/2609.11357
- Key Topics: wheeled humanoid / human-motion retargeting / loco-manipulation / differential inverse kinematics / Isaac Lab
- Notes: Chenbo Xia and Chao Ye released a complete motion-to-policy pipeline for the Galaxea R1 Pro. The work is notable for treating the wheel base and serial torso as a morphology-aware substitute for human lower-body motion instead of applying a legged-humanoid retargeter unchanged.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Humanoid — Controls Team
- Type: Senior Control Engineer / Research Engineer
- Location: Vancouver / Burnaby, British Columbia, Canada; on-site
- Source: official Ashby careers page — https://jobs.ashbyhq.com/humanoid/80880185-8453-4bcd-9677-9d7c04ac7514
- Deadline: unknown
- Topics: low-level control / actuator and joint control / ROS 2 / real-time C++ / EtherCAT and CAN / system identification / robot hardware
- Status: active
- Notes: Published 2026-09-10. The role owns joint- and actuator-level controller design and validation for humanoid limbs and end-effectors, including PID, feedforward, impedance/admittance, observers, multi-DoF modeling, sensor integration, safety handling, and hardware bring-up. It requests an M.S./Ph.D. or equivalent experience plus 5+ years in robotic or mechatronic systems; the official job-board API marked it listed at check time.

</details>
