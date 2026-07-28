**English** | [中文](../zh/drafts/legged-daily-2026-07-28.md)
# Legged Daily - 2026-07-28

## Summary
- Three new papers met the inclusion bar: a reusable discrete humanoid motion prior deployed on Unitree G1, wrench-augmented exploration for quadruped RL, and an explicit polynomial interaction layer for embodied motor policies.
- The Hybrid Motion Prior paper is the strongest hardware signal: one frozen RVQ-based skill interface is reused across velocity tracking, point-goal navigation, and fall-recovery training, with velocity tracking deployed on a real G1.
- WARL improves early exploration by temporarily exposing virtual force/torque actions and then removing them through a success-rate curriculum; the authors also report the important failure mode that such assistance can encourage motions that underuse the robot's embodiment.
- Two new repositories met the repo bar: a measured Isaac Lab reproduction of DreamWaQ on Unitree Go2 and an experimental C++17 deployment controller for G1 locomotion and reference-motion tracking.
- JSK's WARL release and the University of Michigan's PRISM release are useful research-network updates. No sufficiently new, non-duplicate job opening was verified today.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Reusable Hybrid Motion Priors for Humanoid Locomotion from Motion Imitation
- Link: https://arxiv.org/abs/2607.24083
- Source: arXiv
- Date: 2026-07-27
- Authors: Valerio Belli, Valerio Modugno, Enrico Mingo Hoffman, Fabio Amadio
- Topics: humanoid locomotion / motion imitation / reinforcement learning / discrete motion prior / residual vector quantization / Unitree G1
- Summary: A three-stage pipeline distills a motion-imitation expert into a frozen proprioceptive encoder, residual vector-quantized codebook, and action decoder, then trains downstream locomotion policies by selecting discrete code entries instead of relearning low-level motion.
- Notes: The same HMP is reused for velocity tracking, point-goal navigation, and fall-recovery velocity tracking in simulation, and the velocity-tracking policy is deployed on a real Unitree G1. The authors report that rotation-trick codebook training improves latent organization and reduces downstream falls relative to a straight-through estimator.

### WARL: Wrench-Augmented Reinforcement Learning for Task-Agnostic Learning in Legged Robots
- Link: https://arxiv.org/abs/2607.24036
- Source: arXiv
- Date: 2026-07-27
- Authors: Keita Yoneda, Kento Kawaharazuka, Kei Okada
- Topics: quadruped locomotion / reinforcement learning / exploration / force and torque augmentation / curriculum learning
- Summary: WARL augments the training action space with virtual force and torque commands to make difficult behaviors easier to discover, then uses a success-rate-based switching curriculum to remove the wrench and leave a joint-control-only policy.
- Notes: Quadruped experiments cover multiple terrains and motor tasks without terrain-specific reward adjustment or complex hand-designed curricula. The paper also identifies a limitation: wrench assistance can produce solutions that do not sufficiently exploit the robot's physical embodiment, so physically consistent augmentation remains an open design problem. Project page: https://keitayoneda.github.io/kleiyn-warl/

### PRISM: Polynomial Representations for Interaction-Structured Motor Control
- Link: https://arxiv.org/abs/2607.23473
- Source: arXiv
- Date: 2026-07-26
- Authors: Seung Hyun Lee, Stella X. Yu
- Topics: humanoid locomotion / motor policy architecture / polynomial interactions / reinforcement learning / imitation learning / compliant control
- Summary: PRISM adds a compact factorized polynomial module that explicitly learns higher-order interactions among observable physical variables, exposing cues related to power, inertia, contact, slip, and compliance that standard MLP policy inputs leave implicit.
- Notes: Evaluations span humanoid locomotion and contact-rich manipulation. The authors report gains over standard and capacity-matched larger MLP policies, plus sensorless compliant behavior without force, wrench, tactile, contact-label, or admittance-control inputs. Project page: https://lsh3163.github.io/prism/

</details>

<details>
<summary><strong>New Repos</strong></summary>

### romankalyna/dreamwaq-isaaclab
- Link: https://github.com/romankalyna/dreamwaq-isaaclab
- Category: reinforcement learning / reproduction / state estimation / locomotion
- Robot Type: quadruped; Unitree Go2
- Simulator: NVIDIA Isaac Lab 2.0 / Isaac Sim 4.5
- Deploy: simulation; actor observations are designed around deployable proprioception, but no physical-robot run is reported
- Summary: An MIT-licensed reproduction of DreamWaQ's asymmetric actor-critic and CENet estimator in Isaac Lab, training a Go2 policy to infer velocity and latent terrain context from proprioceptive history while reserving terrain scans and true velocity for training-time components.
- Notes: The README reports a deployable 64-dimensional actor nearly matching a 235-dimensional privileged baseline, with evaluation velocity-estimation MSE of 0.0058 (m/s)^2. The author explicitly labels the results as a single-seed reproduction rather than a statistically supported replication and lists deviations from the original paper. Created and last pushed on 2026-07-28; 3 stars at verification.

### M0M0ljh/Beyondmimic_Deploy
- Link: https://github.com/M0M0ljh/Beyondmimic_Deploy
- Category: deployment / locomotion / motion tracking / controller
- Robot Type: humanoid; Unitree G1
- Simulator: Unitree MuJoCo for simulation testing
- Deploy: both simulation and G1 hardware through unitree_sdk2 DDS and ONNX Runtime
- Summary: An experimental C++17 finite-state deployment controller for joystick-commanded G1 locomotion and reference-motion tracking, with x86_64/aarch64 builds, DDS integration, ONNX tensor checks, and automatic transitions to damping on several runtime faults.
- Notes: The repository does not ship the ONNX policy binaries and had no detected repository license at verification. Its README warns that this is not a certified safety controller, requires suspended-robot testing and an operator ready to select Damping, and does not yet enforce joint limits, target slew limits, or configured torque limits. Created and last code-pushed on 2026-07-23; 1 star at verification.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### JSK Robotics Laboratory — WARL author team
- Institution: The University of Tokyo
- Homepage: https://www.jsk.t.u-tokyo.ac.jp/
- arXiv: https://arxiv.org/abs/2607.24036
- Lab / Department: Department of Mechano-Informatics, Graduate School of Information Science and Technology; AI Center
- Key Topics: quadruped locomotion / reinforcement learning / exploration / curriculum learning / robot embodiment
- Notes: Keita Yoneda, Kento Kawaharazuka, and Kei Okada released WARL, extending the JSK network's legged-robot learning signal from task-specific motion generation toward a more task-agnostic exploration mechanism. The explicit negative result around embodiment-inconsistent wrench assistance is worth tracking.
- Students and Representative Works:
  - [Keita Yoneda](https://keitayoneda.github.io/) — [WARL](https://keitayoneda.github.io/kleiyn-warl/)

### Stella X. Yu / University of Michigan motor-control author team
- Institution: University of Michigan, Ann Arbor
- Homepage: https://lsh3163.github.io/prism/
- arXiv: https://arxiv.org/abs/2607.23473
- Lab / Department: Computer Science and Engineering
- Key Topics: humanoid locomotion / embodied motor control / polynomial policy representations / reinforcement learning / imitation learning / sensorless compliance
- Notes: Seung Hyun Lee and Stella X. Yu released PRISM, a cross-task policy-representation signal connecting humanoid locomotion and contact-rich manipulation through explicit physical-variable interactions rather than larger generic MLPs.
- Students and Representative Works:
  - [Seung Hyun Lee](https://lsh3163.github.io/) — [PRISM](https://lsh3163.github.io/prism/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently new, high-confidence legged-robotics opening was verified from an official source today. Previously tracked active roles, including the LAAS-CNRS Gepetto / CNRS-AIST JRL humanoid-robotics PhD closing on 2026-07-31 and Amazon Robotics Compass safe-locomotion role, were not repeated as new items.

</details>
