**English** | [中文](../zh/drafts/legged-daily-2026-09-09.md)
# Legged Daily - 2026-09-09

## Summary
- TANGO directly maps language instructions and egocentric RGB to 29-DoF humanoid actions, enabling zero-shot Unitree G1 traversal through cluttered real scenes after simulation-only training.
- PGMT adds motion-conditioned terrain perception and terrain-aware tracking relaxation to a general humanoid motion prior; its Unitree G1 deployment handles obstacles reported up to 37 cm while retaining teleoperation, dynamic tracking, and fall recovery.
- Mind the Phase shows that gait-phase-conditioned effective rank reveals policy structure hidden by whole-gait averages, and reports roughly 3× lower joint jitter transferring from simulation to a physical Spot.
- Tencent released a BSD-3-Clause Unitree RL stack spanning Isaac Gym training, MuJoCo sim-to-sim validation, and physical deployment for Go2, G1, H1, and H1_2, including pretrained policies and deployment configurations.
- XPENG officially commissioned a humanoid production line and showed IRON autonomously walking off it, a notable signal that its robotics program is moving from R&D prototypes toward line manufacturing; no fresh official job opening was verified.

<details>
<summary><strong>New Papers</strong></summary>

### TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body Vision-Language-Action Model
- Link: https://arxiv.org/abs/2609.09158
- Source: arXiv
- Date: 2026-09-08
- Authors: Anqi Li, Yuxin Chen, Zhaobo Li, Zhuo Cao, Junli Ren, Masayoshi Tomizuka, Dhruv Shah
- Topics: humanoid / vision-language-action / navigation / whole-body control / sim-to-real
- Summary: Introduces a whole-body vision-language navigation framework that converts natural-language instructions and egocentric RGB observations into 29-DoF joint-space actions for collision-free humanoid traversal through cluttered 3D environments.
- Notes: Training is simulation-only, using global path planning, kinematic whole-body motion generation, obstacle-aware motion editing, and RL tracking to synthesize feasible demonstrations. The authors report zero-shot deployment on Unitree G1 without real-world navigation training data; the current evidence is from the paper, and no public code release was verified.

### PGMT: Perceptive General Motion Tracking for Humanoid Robots
- Link: https://arxiv.org/abs/2609.08511
- Source: arXiv
- Date: 2026-09-08
- Authors: Hongyi Li, Li Peizhuo, Yucheng Tao, Ze Wang, Fangzhou Xu, Jinyi Chen, Yanyan Yuan, Dapeng Jia, Yongbin Jin, Mingfeng Fan, Guillaume Sartoretti, Hongtao Wang
- Topics: humanoid / motion tracking / terrain perception / locomotion / teleoperation / recovery
- Summary: Extends general humanoid motion tracking to complex terrain by combining a tracking-and-recovery prior with motion-conditioned terrain glimpses and terrain-aware relaxation of infeasible reference motions.
- Notes: The paper reports zero-shot Unitree G1 deployment over real-world terrain with obstacles up to 37 cm, while one policy supports terrain-adaptive locomotion, diverse whole-body behaviors, teleoperation, dynamic tracking, and fall recovery.

### Mind the Phase: Effective Rank and Representation Health in Legged Locomotion
- Link: https://arxiv.org/abs/2609.06958
- Source: arXiv / CoRL 2026
- Date: 2026-09-07
- Authors: Felipe Tommaselli, Thiago H. Segreto, Juliano D. Negri, Ricardo V. Godoy, Marcelo Becker
- Topics: quadruped / reinforcement learning / representations / effective rank / sim-to-real
- Summary: Studies the effective rank of locomotion-policy Jacobians and shows that conditioning the analysis on swing and stance exposes architecture-dependent representation structure that global rank averages conceal.
- Notes: Layer-normalized residual policies allocate about two more effective-rank dimensions to swing than stance, unlike vanilla MLPs. A resulting architecture/training recipe reports roughly 3× lower joint jitter from simulation to a physical Spot. The project page cautions that higher rank alone is not a health objective and that the current arXiv version is not yet the final camera-ready paper.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Unitree RL GYM
- Link: https://github.com/Tencent/legged_rl_gym
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: Isaac Gym / MuJoCo
- Deploy: both
- Summary: Tencent's BSD-3-Clause reinforcement-learning stack for Unitree Go2, G1, H1, and H1_2 covers the workflow from Isaac Gym training and policy export through MuJoCo sim-to-sim checks to physical deployment.
- Notes: Created on 2026-09-09, the repository includes robot-specific environments, MuJoCo and hardware configurations, pretrained policy files, Unitree SDK 2 communication, and demonstrations for simulation and real robots. It is built on legged_gym and rsl_rl; the initial repository is large and newly published, so reproducibility and maintenance maturity remain to be established.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### XPENG Robotics / IRON
- Institution: XPENG
- Homepage: https://www.xpeng.com/news/01a080371029a057bc8e8a02a2c6012b
- Lab / Department: Humanoid Robotics / Physical AI
- Key Topics: humanoid / whole-body mobility / physical AI / robot manufacturing / commercialization
- Notes: XPENG announced on 2026-09-08 that its humanoid production line had entered operation and that an IRON robot autonomously walked off the line after production. The company reports more than 80% automation across core manufacturing processes, 76 body degrees of freedom plus 21 per hand, and plans for mass production by the end of 2026 followed by initial deployment in its stores and campuses. These are company-reported specifications and plans rather than independent production-volume evidence.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently fresh, active, and high-confidence legged-robotics opportunity was verified from an official source in this run.

</details>
