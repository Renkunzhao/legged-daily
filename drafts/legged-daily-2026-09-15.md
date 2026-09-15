**English** | [中文](../zh/drafts/legged-daily-2026-09-15.md)
# Legged Daily - 2026-09-15

## Summary
- JEPLO introduces a mapping-free LiDAR locomotion stack that jointly learns predictive proprioceptive/exteroceptive embeddings and a locomotion policy, with Unitree Go2 sim-to-real demonstrations on stairs, boxes, darkness, and degraded perception.
- ResSafe separates a humanoid task policy from a residual safety-correction policy, reporting improved balance robustness in simulation and hardware payload tests without online model-based filtering.
- The complete JEPLO release includes Isaac Lab training, MuJoCo validation, Go2/Jetson deployment, a dataset, pretrained-policy support, and hardware setup material under GPL-3.0.
- HimLoco-AMP-Lab is a compact BSD-licensed Go2 PPO/AMP framework for Isaac Lab with history observations, expert-motion replay, policy export, and MuJoCo sim-to-sim; expert trajectories are intentionally not distributed.
- No new high-confidence actionable job opening was selected today. Flexion Robotics humanoid motion-generation roles remain visible on the official careers page but were already captured in an earlier draft, so they are not duplicated here.

<details>
<summary><strong>New Papers</strong></summary>

### JEPLO: Joint-Embedding Predictive Learning for LiDAR-Based Legged Locomotion
- Link: https://arxiv.org/abs/2609.15770
- Source: arXiv
- Date: 2026-09-14
- Authors: Qihao Yuan, Yixuan Qiu, Ziyu Cao, Ming Cao, Kailai Li
- Topics: quadruped locomotion / LiDAR perception / JEPA world model / reinforcement learning / sim-to-real
- Summary: Learns predictive proprioceptive and LiDAR-derived terrain embeddings with a PE-JEPA world model, then jointly trains a deployable locomotion policy through a concurrent JEPA teacher-student pipeline without an explicit terrain map.
- Notes: The authors report Unitree Go2 sim-to-real traversal of long stairs and boxes, operation in darkness, and improved robustness under LiDAR occlusion, sparsity, and noise. Code, data, deployment tools, and hardware designs are public; results were not independently reproduced in this run.

### ResSafe: Learning Safety Filtering with Residual Reinforcement Learning for Humanoids
- Link: https://arxiv.org/abs/2609.15988
- Source: arXiv
- Date: 2026-09-14
- Authors: Gechen Qu, Tong Zhang, Bike Zhang, Yen-Jen Wang, Koushil Sreenath, Claire Tomlin, Jason Jangho Choi
- Topics: humanoid whole-body control / safety filtering / residual reinforcement learning / extreme balance / sim-to-real
- Summary: Freezes a nominal motion policy focused on task performance and trains a separate residual policy to add safety corrections, decoupling tracking performance from robustness and fall avoidance.
- Notes: The paper connects the learned residual to min-norm safety-filter corrections and reports simulation plus real-robot balance tests under random payloads. Across the four hardware motions shown on the project page, the method generally lowers falls versus the nominal baseline, though performance varies against the domain-randomized and discriminating-hyperplane baselines; results were not independently reproduced.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### ASIG-X/JEPLO
- Link: https://github.com/ASIG-X/JEPLO
- Category: reinforcement learning / perceptive locomotion / world model / deployment toolkit
- Robot Type: quadruped / Unitree Go2
- Simulator: Isaac Lab / Isaac Sim for training; customized Unitree MuJoCo for sim-to-sim
- Deploy: simulation and hardware; ONNX/TensorRT deployment on a Go2 equipped with Livox Mid-360 and Jetson AGX Orin
- Summary: Releases the full JEPLO stack for mapping-free LiDAR locomotion, including training, pretrained-policy playback, MuJoCo validation, ROS 2 depth generation, Go2 deployment code, dataset links, and hardware setup guidance.
- Notes: Created 2026-09-12 and pushed on 2026-09-15 when checked; GPL-3.0. The README explicitly warns that training can be unstable and that exported TensorRT models should be validated against recorded inputs/outputs before robot control.

### JF-Li5266/HimLoco-AMP-Lab
- Link: https://github.com/JF-Li5266/HimLoco-AMP-Lab
- Category: reinforcement learning / imitation learning / locomotion toolkit
- Robot Type: quadruped / Unitree Go2
- Simulator: Isaac Lab / Isaac Sim for training; MuJoCo for sim-to-sim
- Deploy: simulation and model export; TorchScript/ONNX export is included, but no physical-robot deployment evidence is provided
- Summary: Provides Go2 velocity-control tasks for PPO and adversarial motion priors, with six-frame actor observations, terrain curriculum, domain randomization, expert-motion replay, checkpoint playback/export, and a MuJoCo sim-to-sim runner.
- Notes: Created 2026-07-02 and last pushed 2026-09-12 when checked; BSD-3-Clause. Authorized expert trajectories must be supplied locally and are not distributed, so the AMP path is not fully reproducible from the repository alone; pure PPO does not require them.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### University of Groningen–Linköping University ASIG collaboration
- Institution: University of Groningen / Linköping University
- Homepage: https://asig-x.github.io/jeplo_web/
- GitHub: https://github.com/ASIG-X/JEPLO
- Key Topics: perceptive legged locomotion / LiDAR / predictive world models / reinforcement learning / sim-to-real
- Notes: Qihao Yuan, Yixuan Qiu, Ziyu Cao, Ming Cao, and Kailai Li released JEPLO together with code, data, hardware designs, and real Go2 demonstrations. The cross-institution signal is especially relevant for robust onboard perception and terrain-aware locomotion without explicit mapping.

### UC Berkeley–UCLA safe humanoid control collaboration
- Institution: University of California, Berkeley / University of California, Los Angeles
- Homepage: https://sciautonomy.github.io/ResSafe_Web/
- arXiv: https://arxiv.org/abs/2609.15988
- Key Topics: humanoid whole-body control / safe reinforcement learning / safety filters / balance robustness
- Notes: Gechen Qu and collaborators including Koushil Sreenath, Claire Tomlin, and Jason Jangho Choi released ResSafe with hardware balance trials. It is a strong signal at the intersection of learning-based whole-body control and control-theoretic safety filtering.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence, actionable legged-robotics or humanoid opening was added in this run. Flexion Robotics' Zurich generative humanoid motion-generation research-engineer and internship postings remain visible on the official careers page, but both were already recorded in the 2026-08-13 draft and are therefore not duplicated. Existing opportunities in `jobs.md` should still be verified at their official sources before application.

</details>
