**English** | [中文](../zh/drafts/legged-daily-2026-10-30.md)
# Legged Daily - 2026-10-30

## Summary
- HC2Robot predicts the timing, position, and quality of future foothold contacts using deployable observations; its authors report 97.60% average success over several simulated humanoid parkour terrains, without established hardware validation.
- ETH-led phase-conditioned PPO uses phase-specific critics, reward gates and resets for long-horizon loco-manipulation; real Unitree G1 and arm-equipped Spot experiments are reported.
- CPG-ENN learns a low-dimensional, interpretable gait interface for walk, trot, pace, bound and pronk, with 99.39% simulated gait-transition success and real Go2 gait demonstrations.
- Inspected Go2 convex MPC and integrated ROS2/Gazebo/MuJoCo codebases, plus a G1 AMP race training baseline; all are rediscovered engineering references, not claimed first released today.
- HiPHI offers 617.5 hours of human motion/interaction behind research-license access approval; G1 Moves provides 60 retargeted G1 motion clips and policy exports openly.
- Official TUM humanoid mobile-manipulation PhD applications close 2026-11-15; the existing Aarhus Physical AI PhD posting closes 2026-11-01 and is worth a deadline reminder.

<details>
<summary><strong>New Papers</strong></summary>

### HC2Robot: Hyper-Connection Transformers with Predicted Foresight for Multi-Terrain Humanoid Parkour
- Link: https://arxiv.org/abs/2610.36825
- Source: arXiv preprint (no confirmed conference or journal acceptance)
- Date: 2026-10-27
- Authors: Wenhao Xu, Yanheng Mai, Yifei Fu, Nan Zheng, Yanbo Zhou, Zirui Huang, Mingsheng Ling, Xinjue Wang, Renjing Xu
- Topics: humanoid / perceptive locomotion / precise footholds / privileged learning / temporal Transformer / RL
- Summary: A Predicted Foresight Module estimates each foot's upcoming touchdown timing, position, and support quality from deployable observations; a Hyper-Connection Transformer and future-motion head combine this predictive contact representation with temporal context for parkour control.
- Notes: Authors report 97.60% mean simulated traversal success across stairs, gaps, platforms and slopes with improved safe-foot placement; physical-robot deployment is not established by the abstract. A promising contact-prediction signal rather than evidence of real-world success.

### Learning Multi-Phase Robot Loco-Manipulation via Phase-Conditioned Policy Optimization
- Link: https://arxiv.org/abs/2610.36270
- Source: arXiv preprint (no confirmed peer-reviewed venue)
- Date: 2026-10-26
- Authors: Simone Manni, Annika Wollschläger, Dario Bellicoso, Abel Gawel, Marco Hutter, Simon Le Cleac'h, Jan Brüdigam
- Topics: humanoid / quadruped / loco-manipulation / phase-conditioned PPO / hierarchical control / sim-to-real
- Summary: Extends PPO for multi-phase crouch–grasp–locomote tasks via a phase-conditioned critic, phase-gated rewards and multi-phase reset curriculum, separating balance control from task-stage execution without requiring human reference motions.
- Notes: The authors show multi-stage hardware tasks on both a Unitree G1 and a Boston Dynamics Spot equipped with a manipulator. Results are cross-platform, while the paper does not state a confirmed conference or journal venue.

### A Trainable CPG Framework for Quadruped Locomotion
- Link: https://arxiv.org/abs/2610.36537
- Source: arXiv preprint (no confirmed peer-reviewed venue)
- Date: 2026-10-27
- Authors: Xiyan Liu, Yide Liu, Guoyong Mao, Shaoxing Qu
- Topics: quadruped / gait control / CPG / reinforcement learning / velocity tracking / Unitree Go2
- Summary: CPG-ENN combines a symmetric eight-neuron rhythm generator with a shared execution neural network; a single feedback policy modulates six interpretable trajectory parameters to realize five gaits and transitions without separate gait policies or online IK.
- Notes: The authors report 99.39% simulated transition success across 20 ordered gait pairs and four commanded speed levels, and demonstrate the five gaits and transitions on real Go2 hardware. No confirmed venue or code release was identified.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### elijah-waichong-chan/go2-convex-mpc
- Link: https://github.com/elijah-waichong-chan/go2-convex-mpc
- Category: MPC / control / simulator / toolkit
- Robot Type: quadruped (Unitree Go2)
- Simulator: MuJoCo / Pinocchio / CasADi / OSQP
- Deploy: sim
- Summary: UC Berkeley MEng capstone implementation of convex centroidal contact-force MPC, Raibert-style touchdown placement, quintic swing trajectories and trotting examples for Go2.
- Notes: README reports 30–50 Hz MPC with 200 Hz leg/gait control, simulated forward/backward velocities up to 0.8 m/s, and about 2.70 ms average MPC processing time in its benchmark; real-hardware validation is not claimed. Rediscovered existing engineering repository.

### darshmenon/quadruped-robotics-stack
- Link: https://github.com/darshmenon/quadruped-robotics-stack
- Category: RL / MPC / simulator / navigation toolkit
- Robot Type: quadruped (Unitree Go2; other robot descriptions remain stubs)
- Simulator: MuJoCo 3.1 / Gazebo Harmonic / ROS 2 Humble
- Deploy: sim
- Summary: End-to-end Go2 engineering workspace spanning PPO locomotion, CHAMP kinematic gaits, Quad-SDK NMPC, rough-terrain curricula, 3D SLAM and navigation with Gazebo and MuJoCo demos.
- Notes: README explicitly says only Go2 has a complete working robot model and the CHAMP non-Go2 configs are placeholder stubs. MIT license indicated; simulated Go2 NMPC walking is demonstrated, not a verified real-robot result.

### Jiarui-Xie/AMP_Running_baseline
- Link: https://github.com/Jiarui-Xie/AMP_Running_baseline
- Category: RL / AMP / motion tracking / training toolkit
- Robot Type: humanoid (Unitree G1)
- Simulator: Isaac Lab 2.3.1 / Isaac Sim 5.1
- Deploy: both (author-supplied BASE sim-to-real demonstration; later checkpoints simulation-only)
- Summary: Legged Lab fork developed for the 2026 Beijing Yizhuang humanoid half-marathon, adding a two-clip walk/run AMP base, SONIC-style actuator modeling, per-joint command-delay randomization and an energy-aware high-speed post-training configuration.
- Notes: Baseline checkpoint model_6200.pt and videos are linked by the author; the later high-speed checkpoint is not reported as physically tested. MIT license is indicated; inherited motion-clip licenses should be checked.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### HiPHI — High-Precision Human Motion and Object Interaction
- Link: https://huggingface.co/datasets/noitomrobotics/HiPHI
- Category: human mocap / robot-ready motion reference / human-object interaction
- Subject: human (retargetable to humanoids; G1 demonstrations)
- Content: 617.5 hours including mirrored motions, with 371.8 hours body-only and 245.7 hours HOI; 132 performers; 200.1 million frames at 90 Hz; 40 canonical object meshes.
- Format: 55-joint BVH / object-pose CSV / OBJ meshes / metadata CSV / 32 tar.zst motion archives
- Access: gated (Hugging Face questionnaire, research-license agreement and approval required)
- License: modalitynet-open-research-license (commercial licensing separate)
- Summary: Large-scale synchronized optical motion capture and object tracks for humanoid imitation, motion generation, retargeting and contact-aware whole-body learning; associated paper is listed as CoRL 2026.
- Notes: Dataset page displays real file/package structure and access workflow; public metadata and press announcements do not mean anonymous download. A rediscovered August 2026 data release, not a new October 30 launch.

### exptech/g1-moves — G1 Moves
- Link: https://huggingface.co/datasets/exptech/g1-moves
- Category: robot motion / human mocap / motion retargeting
- Subject: Unitree G1 EDU (29 DoF) / human demonstrations
- Content: 60 clips (28 dance, 27 karate, 5 bonus), roughly 29.6 minutes / 106,434 frames at 60 Hz; each motion has trained policy assets according to the dataset card.
- Format: BVH / FBX / PKL / NPZ / ONNX and video
- Access: open
- License: cc-by-4.0 (as declared on the Hugging Face dataset card)
- Summary: A compact reproducibility resource with raw capture, retargeted G1 trajectories, RL-ready action data and exported policies for humanoid motion-tracking experiments.
- Notes: Already-existing release rediscovered in today's sweep; dataset card descriptions differ slightly on frame count across revisions, so use the latest dataset-card total and verify individual clips before benchmarking.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Marco Hutter / Robotic Systems Lab — ETH Zurich
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: humanoid / quadruped / loco-manipulation / reinforcement learning / hierarchical whole-body control
- Notes: New phase-conditioned PPO paper (https://arxiv.org/abs/2610.36270) includes Marco Hutter and collaborators and verifies task-stage reinforcement learning on G1 and manipulator-equipped Spot; track future reproducible code.

### Shaoxing Qu / Zhejiang University — quadruped gait learning
- Institution: Zhejiang University, Department of Engineering Mechanics
- arXiv: https://arxiv.org/abs/2610.36537
- Lab / Department: State Key Laboratory of Fluid Power & Mechatronic Systems / Center for X-Mechanics
- Key Topics: quadruped / CPG / neural locomotion / interpretable gait commands / RL
- Notes: CPG-ENN reports physically interpretable gait modulation and five-gait hardware demonstrations on Unitree Go2; the work provides a new author-network source for multi-gait locomotion.

### He Kong / Southern University of Science and Technology — REACH
- Institution: Southern University of Science and Technology; collaboration with The Chinese University of Hong Kong
- Homepage: https://aislab-sustech.github.io/REACH/
- arXiv: https://arxiv.org/abs/2610.36546
- Lab / Department: School of Automation and Intelligent Manufacturing
- Key Topics: humanoid / crawling / variable-height walking / LiDAR planning / contact-rich transitions
- Notes: REACH is marked to appear at IEEE Humanoids 2026 and demonstrates real G1 transitions between walking and crawling in low-clearance environments. The project page says code is still “To be released,” despite the arXiv abstract saying code is available; record code status as unverified, not released.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Technical University of Munich / AVS Lab — Humanoid Mobile Manipulation PhD (proposed addition)
- Type: PhD / Research Associate
- Location: Garching, Germany
- Source: official TUM lab listing — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: humanoid / loco-manipulation / whole-body control / perception / motion planning / VLM / VLA
- Status: active
- Notes: Three-year full-time TV-L E13 position under Johannes Betz with humanoid and quadruped hardware available for research. German and English professional communication required. Existing opportunity revalidated from earlier draft discussions, but not yet in formal jobs.md; official page lists the exact deadline.

### Aarhus University / A3 Lab — Physical AI PhD (deadline reminder; proposed addition)
- Type: PhD
- Location: Aarhus, Denmark
- Source: official university posting — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: robot foundation models / VLA / world models / test-time adaptation / edge intelligence
- Status: active
- Notes: Existing cross-domain research opportunity, not a newly opened legged-only role; the official deadline is imminent. Three-year project supervised by Behzad Bozorgtabar and Qi Zhang, with public-data/simulation and potential hardware evaluation.

</details>
