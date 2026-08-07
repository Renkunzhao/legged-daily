**English** | [中文](../zh/drafts/legged-daily-2026-08-07.md)
# Legged Daily - 2026-08-07

## Summary
- Three new arXiv papers met the inclusion bar today: ω-0 unifies visual prediction and whole-body action generation for humanoid manipulate-while-moving tasks; TRACE targets contact-robust proprioceptive odometry; and KILVO fuses kinematics, IMU, LiDAR, and vision for failure-resilient humanoid state estimation.
- ω-0 is the strongest whole-body learning signal: its official page reports one policy across 11 household tasks, 81.8% real-world success, and a new 40.3-hour, 4,827-episode multimodal humanoid dataset, although neither code nor a public dataset download was verified today.
- KILVO's paper states that code and datasets are released, but the linked GitHub repository remains only a 209-byte placeholder saying they will be available soon; the paper is included, while the repository is not counted as a usable release.
- IIT DLSLab's quadruped get-up stack received a substantive deployment update, and a new H1 Isaac Lab repository publishes unusually detailed evaluation and ablation results; the latter remains an independent, unlicensed release with no hardware validation.
- MARS Lab at NTU is a higher-priority source after ω-0 extends its embodied-AI line to real humanoid concurrent loco-manipulation. Amazon Robotics Compass's official Safe Locomotion role remains active.

<details>
<summary><strong>New Papers</strong></summary>

### ω-0: A Latent Predictive World Action Model for Concurrent Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2608.06375
- Source: arXiv / official project page
- Date: 2026-08-07
- Authors: Zhe Li, Zhenzhe Zhang, Yangyang Wei, Wenjie Zhang, Xichen Yuan, Peiyuan Zhi, Gen Li, Xinying Guo, Fengjie Gao, Jianfei Yang, Shanghang Zhang
- Topics: humanoid / concurrent loco-manipulation / world-action model / vision-language-action learning / diffusion policy / whole-body control / real-world dataset
- Summary: ω-0 conditions on language, visual observations, and proprioception to predict compact future visual embeddings and controller-compatible whole-body action latents, enabling one policy to coordinate locomotion, posture, balance, arms, and hands during household manipulation.
- Notes: The official page reports 81.8% success and 90.3% task progress across 11 real-world tasks, and introduces ω-HOME with 40.3 hours, 24 tasks, 4,827 episodes, and six synchronized modalities. These are author-reported preprint results; no code or downloadable dataset release was verified today. Project page: https://gentlefress.github.io/OMEGA-0_page/

### Learned Proprioceptive Odometry for Legged Robots under Unreliable Contact Conditions
- Link: https://arxiv.org/abs/2608.05975
- Source: arXiv
- Date: 2026-08-07
- Authors: Taehyeon Kong, Woojin Kim, Jemin Hwangbo
- Topics: legged robots / proprioceptive odometry / contact-aware estimation / attention / sim-to-real / sensor fusion
- Summary: TRACE predicts relative pose and body-frame velocity from IMU and joint histories, using foot-aware cross-attention to adaptively combine inertial and leg-wise kinematic tokens without manually chosen contact or slip thresholds.
- Notes: The method adds kinematic-consistency auxiliary losses, policy randomization in simulation, and partial real-world fine-tuning. The authors report lower indoor and outdoor position drift than filtering, hybrid, and learned baselines under unreliable contacts; no public code was verified today, and the paper is submitted to RA-L.

### Kinematic-Inertial-LiDAR-Visual Odometry with Robust Multimodal Adaptation for Humanoid Robots
- Link: https://arxiv.org/abs/2608.05647
- Source: arXiv / IEEE/ASME Transactions on Mechatronics
- Date: 2026-08-07
- Authors: Jixin Gao, Fucheng Liu, Teng Zhang, Fusheng Zha
- Topics: humanoid / state estimation / odometry / sensor fusion / contact estimation / LiDAR / vision / sensor-failure robustness
- Summary: KILVO integrates IMU prediction, high-rate asynchronous leg-kinematic constraints, sequential LiDAR and visual updates, and compact contact estimation in a hybrid error-state iterated Kalman filter designed for humanoid sensing and degraded-modality operation.
- Notes: The paper reports evaluation on public datasets and multiple real humanoids and is accepted by IEEE/ASME Transactions on Mechatronics. Its linked repository currently contains only a placeholder saying code and datasets will be available soon, despite the paper abstract saying they are released: https://github.com/JixinGao/KILVO

</details>

<details>
<summary><strong>New Repos</strong></summary>

### iit-DLSLab/get-up-isaaclab
- Link: https://github.com/iit-DLSLab/get-up-isaaclab
- Category: RL / control / deployment
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: BSD-3-Clause Isaac Lab implementation of quadruped self-righting for Unitree Go2, with RSL-RL training, Rapid Motor Adaptation, parameter identification, MuJoCo sim-to-sim evaluation, and ROS 2 hardware deployment.
- Notes: The 2026-08-07 update adds a Pegasus policy and deployment fixes, following new PD-randomization and center-of-mass-offset events on August 6. The README targets Isaac Lab 2.3.2, RSL-RL 3.3.0, and MuJoCo 3.7.0 and includes training, sim-to-sim, and sim-to-real demonstrations.

### HaoZiOwO/rl-h1-locomotion
- Link: https://github.com/HaoZiOwO/rl-h1-locomotion
- Category: RL / evaluation / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim
- Summary: New Unitree H1 velocity-tracking study built on Isaac Lab and RSL-RL, with flat and rough-terrain training, payload tests, reward ablations, multi-seed evaluation, checkpoints, and PPO/BC/SAC sample-efficiency comparisons.
- Notes: Created on 2026-08-07. The README publishes detailed numerical results and reproduction commands and documents Isaac Sim 5.1 rendering failures; however, the repository has no declared license, no stars at verification, and no hardware deployment evidence, so treat it as an independent experimental artifact rather than a validated reference implementation.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### MARS Lab — Nanyang Technological University
- Institution: Nanyang Technological University, Singapore
- Homepage: https://marslab.tech/
- arXiv: https://arxiv.org/abs/2608.06375
- Lab / Department: Multimodal embodied AI and Robotic Systems Lab
- Key Topics: humanoid / loco-manipulation / world models / multimodal embodied AI / robot learning / real-world deployment
- Notes: ω-0 materially strengthens this already tracked source: the lab moves from multimodal embodied AI into a unified real-humanoid world-action model, a 40.3-hour household dataset, and 11-task deployment. Track the official project page for code, ω-HOME download access, and independent evaluation details.
- Students and Representative Works:
  - [Zhe Li et al.](https://arxiv.org/abs/2608.06375) — [ω-0: A Latent Predictive World Action Model for Concurrent Humanoid Loco-Manipulation](https://gentlefress.github.io/OMEGA-0_page/)

### Jemin Hwangbo and collaborators — KAIST
- Institution: Korea Advanced Institute of Science and Technology
- arXiv: https://arxiv.org/abs/2608.05975
- Lab / Department: legged-robot learning and state-estimation collaboration
- Key Topics: legged robots / learned state estimation / proprioceptive odometry / contact robustness / sim-to-real
- Notes: TRACE adds an estimation-focused signal to the existing KAIST/Jemin Hwangbo source network: it combines learned attention, physics-inspired consistency losses, policy-randomized simulation, and partial real-world fine-tuning for contact-degraded legged odometry.
- Students and Representative Works:
  - [Taehyeon Kong et al.](https://arxiv.org/abs/2608.05975) — [Learned Proprioceptive Odometry for Legged Robots under Unreliable Contact Conditions](https://arxiv.org/abs/2608.05975)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-07 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role develops and deploys RL controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms, combining formal safety mechanisms, sim-to-real, and model-based whole-body control. No higher-confidence newly posted opportunity surpassed this active signal today.

</details>
