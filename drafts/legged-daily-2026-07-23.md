**English** | [中文](../zh/drafts/legged-daily-2026-07-23.md)
# Legged Daily - 2026-07-23

## Summary
- YAHMP provides a controlled empirical study and an Apache-2.0 modular stack for Unitree G1 general motion tracking, separating design choices that materially improve tracking from those that mainly affect effort, complexity, or interaction.
- Extreme-RGMT addresses the generalist-versus-specialist trade-off through continual learning, preserving mastered motions while concentrating training on rare, difficult dynamic segments; the project demonstrates highly dynamic Unitree G1 motions and online inertial-motion-capture tracking.
- PGTT's new arXiv revision reports IROS 2026 acceptance and strengthens the case for morphology-agnostic perceptive locomotion: phase structure is introduced through reward shaping rather than oscillator or IK action priors, with Go2 hardware validation and preliminary ANYmal-C transfer.
- Two official codebases are worth adding: YAHMP for MuJoCo/MJLab humanoid tracking experiments and PGTT for MJX training, terrain generation, evaluation, perception, and documented Go2 hardware deployment.
- The Extreme-RGMT author network is a useful signal around Beijing Institute of Technology and Humanoid Robotics (Shanghai) / OpenLoong, connecting academic control research with a physical humanoid platform team.

<details>
<summary><strong>New Papers</strong></summary>

### What Matters in Humanoid General Motion Tracking? An Empirical Study
- Link: https://arxiv.org/abs/2607.19903
- Source: arXiv
- Date: 2026-07-22
- Authors: Fabio Amadio, Enrico Mingo Hoffman
- Topics: humanoid / whole-body motion tracking / imitation learning / sim-to-real / Unitree G1
- Summary: A controlled empirical study of motion-command representation, observation history, action representation, actuation profile, hand-force randomization, and training approach in general humanoid motion tracking, implemented in the open-source YAHMP framework.
- Notes: The authors evaluate retargeted motions against a TWIST2 baseline trained on the same set and deploy policies zero-shot on a real Unitree G1, demonstrating diverse tracking, perturbation recovery, and forceful interaction.

### Extreme-RGMT: Continual Learning of Highly Dynamic Skills for Robust Generalist Humanoid Control
- Link: https://arxiv.org/abs/2607.20110
- Source: arXiv
- Date: 2026-07-22
- Authors: Yubiao Ma, Han Yu, Kai Guo, Changtai Lv, Zhengquan Mao, Boyang Xing, Xuemei Ren, Dongdong Zheng
- Topics: humanoid / whole-body motion tracking / continual learning / highly dynamic skills / teleoperation
- Summary: A two-stage framework that starts from a generalist motion-tracking policy, then acquires difficult dynamic skills while constraining policy drift on already-mastered motions.
- Notes: Difficulty-aware sampling and advantage-prioritized trajectory resampling target sparse critical segments; the paper and project page show Unitree G1 rollouts including aerial cartwheels, backflips, kip-ups, and online tracking from inertial motion capture. No training code was verified in this run.

### PGTT: Phase-Guided Terrain Traversal for Perceptive Legged Locomotion
- Link: https://arxiv.org/abs/2510.18348
- Source: arXiv / IROS 2026
- Date: 2026-07-22
- Authors: Alexandros Ntagkas, Chairi Kiourt, Konstantinos Chatzilygeroudis
- Topics: quadruped / perceptive locomotion / reinforcement learning / terrain adaptation / sim-to-real
- Summary: A perceptive deep-RL locomotion method that encodes per-leg phase through spline-based reward shaping while retaining direct joint-space actions, reducing dependence on morphology-specific oscillator or IK action priors.
- Notes: This is a v2 update to a 2025 preprint, now marked accepted at IROS 2026. The paper reports stronger disturbance and obstacle success than evaluated baselines, real Unitree Go2 validation with a LiDAR heightmap pipeline, and preliminary ANYmal-C transfer with the same hyperparameters.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### YAHMP
- Link: https://github.com/fabio-amadio/yahmp
- Category: RL / motion tracking / evaluation / toolkit
- Robot Type: humanoid — Unitree G1
- Simulator: MuJoCo / MJLab
- Deploy: simulation and documented hardware deployment
- Summary: An Apache-2.0 modular framework for training, evaluating, exporting, and deploying Unitree G1 general motion-tracking policies, with retargeted AMASS/OMOMO support and a supplied ONNX policy path.
- Notes: The repository includes nominal, future-reference, and teacher-student variants plus conversion, evaluation, ONNX export, and deployment utilities. It had 13 stars at verification; the paper reports zero-shot real-G1 deployment, but this run did not reproduce training or hardware results.

### phase_guided_terrain_traversal
- Link: https://github.com/NtagkasAlex/phase_guided_terrain_traversal
- Category: RL / control / perception / terrain generation
- Robot Type: quadruped — Unitree Go2 / ANYmal
- Simulator: MuJoCo MJX
- Deploy: simulation and Unitree Go2 hardware
- Summary: The official PGTT implementation, covering procedural terrain generation, JAX/MJX training, multi-run evaluation, saved policies, a LiDAR elevation-mapping perception stack, and Unitree SDK hardware deployment.
- Notes: Shared robot-agnostic modules support Go2 and ANYmal configurations; the documented hardware path uses Unitree L1 LiDAR, Point-LIO, elevation mapping, and `unitree_sdk2py`. The repository had 66 stars at verification and no explicit license was visible in GitHub metadata.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Dongdong Zheng / Humanoid Robotics (Shanghai) — Extreme-RGMT network
- Institution: Beijing Institute of Technology / Humanoid Robotics (Shanghai) Co., Ltd.
- Homepage: https://zeonsunlightyu.github.io/Extreme-RGMT.github.io/
- arXiv: https://arxiv.org/abs/2607.20110
- Lab / Department: School of Automation, Beijing Institute of Technology; Humanoid Robotics (Shanghai) / OpenLoong team
- Key Topics: humanoid / whole-body control / motion tracking / continual learning / teleoperation
- Notes: Extreme-RGMT is a new joint signal spanning BIT, Humanoid Robotics (Shanghai), and Shandong University. It is particularly relevant for tracking work that couples generalist learned control, rare highly dynamic skills, online inertial-motion-capture input, and physical Unitree G1 experiments.
- Students and Representative Works:
  - [Yubiao Ma](https://arxiv.org/search/cs?searchtype=author&query=Ma,+Y) — [Extreme-RGMT](https://arxiv.org/abs/2607.20110)
  - [Han Yu](https://zeonsunlightyu.github.io/Extreme-RGMT.github.io/) — [Extreme-RGMT](https://arxiv.org/abs/2607.20110)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence job or opportunity signal was found since the previous run. Previously tracked rolling openings, including ETH Zurich RSL and EPFL BioRob entries already present in `jobs.md`, are not repeated as new additions today.

</details>
