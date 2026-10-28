**English** | [中文](../zh/drafts/legged-daily-2026-10-28.md)
# Legged Daily - 2026-10-28

## Summary
- KAIST proposes a backward-only smooth gradient for frictional contact, keeping hard-contact forward dynamics intact; its quadruped policy was trained on 100,000 samples in 108 seconds and deployed directly on a 45-kg robot. The paper was submitted to T-RO, not accepted yet (arXiv:2610.35852, 2026-10-26).
- Amazon FAR's FLoRe learns vision-and-force-reactive humanoid loco-manipulation from robot-free force-sensing grippers. Its real-robot three-task rollout success was 80%, against 26.7% for the position-only baseline (arXiv:2610.35862).
- Continuous-Time Safe Planning for Agile Quadrupeds uses Bernstein polynomials to certify obstacle clearance and input limits over entire trajectories rather than only sampled time steps; the authors report quadruped hardware experiments with moving obstacles (arXiv:2610.35670).
- Newly curated Go2 projects include stride-conditioned SLR with a ROS 2 hardware path and HimLoco-AMP-Lab with Isaac Lab-to-MuJoCo sim-to-sim. A third reproducible Isaac Lab baseline for MIRRORME BPX includes flat/stair checkpoints.
- The PHUMA (CoRL 2026 Spotlight) G1/H1-2 locomotion dataset is downloadable, but the Hub release excludes licensing-restricted subsets; its complete 73-hour corpus requires upstream-data reconstruction. FLoRe's force-annotated demonstrations are a watch candidate, not a public dataset.
- No new high-confidence job opening today. Aarhus University's previously tracked Physical AI PhD remains listed with a 2026-11-01 23:59 CET deadline; TUM AVS humanoid mobile-manipulation PhD has a 2026-11-15 deadline.

<details>
<summary><strong>New Papers</strong></summary>

### Differentiable Contact Dynamics for Legged Locomotion: Policy Learning and Contact-Implicit Trajectory Optimization
- Link: https://arxiv.org/abs/2610.35852
- Source: arXiv preprint; submitted to IEEE Transactions on Robotics (T-RO), not reported accepted
- Date: 2026-10-26
- Authors: Gijeong Kim, Seungbin Oh, Dongyun Kang, Hae-Won Park
- Topics: quadruped / frictional contact / differentiable physics / policy learning / BPTT / contact-implicit trajectory optimization / real robot
- Summary: Derives a smooth sensitivity for Coulomb friction by relaxing de Saxce-corrected cone complementarity only in the backward pass, while the hard-contact solver still determines forward rollouts. The gradient crosses clamping, sliding and separation mode boundaries and supports both BPTT policy training and contact-implicit optimization.
- Notes: Project https://diffcontact.github.io/ . The team reports 100,000 samples / 108 s for trot and pace on a desktop PC, and transfer without fine-tuning to a 45-kg quadruped including push and low-friction tests. These results are specific to the reported tasks and hardware; no public code release was verified.

### Learning Force-Reactive Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.35862
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-26
- Authors: Sihang Li, Xiaofeng Guo, Jinkun Cao, Charlie Cheng, Ruihan Yang, Chen Feng, Guanya Shi, Haozhi Qi
- Topics: humanoid / loco-manipulation / force sensing / hybrid compliance / whole-body control / diffusion policy / real robot
- Summary: FLoRe combines robot-free demonstrations captured with two force-sensing UMI-style grippers and body trackers, a vision-proprioception-wrench conditioned diffusion policy, and a compliant whole-body controller that converts commanded hand forces into feedback-corrected target shifts while preserving balance.
- Notes: Project https://louis-leee.github.io/FLoRe/ . Across three real-robot contact-rich tasks (wiping a board, rotating a crate, pushing a gantry), the authors report 80% rollout success versus 26.7% for a position-only policy under the same controller. The project says code coming soon; demonstrations are not publicly downloadable from the project page.

### Continuous-Time Safe Planning and Control for Agile Quadrupeds
- Link: https://arxiv.org/abs/2610.35670
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-26
- Authors: Gage MacLin, Mason Peterson, Camilla Tabasso, Venanzio Cichella, Joshua Migdal, Tye Brady, Taskin Padir
- Topics: quadruped / safe navigation / online planning / Bernstein polynomials / collision avoidance / real robot
- Summary: Preserves a heading-coupled fully-actuated SE(2) velocity model and optimizes composite Bernstein trajectories, using their convex-hull property to check collision avoidance and motion-input limits over the continuous horizon rather than only at discretized waypoints.
- Notes: Includes closed-loop quadruped hardware navigation among unknown moving obstacles as well as simulation comparisons. The paper does not give a confirmed code release or accepted venue.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Yoshifumi-Masuya/slr-stride
- Link: https://github.com/Yoshifumi-Masuya/slr-stride
- Category: control / RL / locomotion / sim-to-real
- Robot Type: quadruped (Unitree Go2)
- Simulator: Isaac Lab; original SLR simulation lineage
- Deploy: both (author reports ROS 2 deployment on physical Go2)
- Summary: Extends the CoRL 2024 SLR proprioceptive policy with a separately commanded 0.1-0.4 m stride length, measured from touchdown events, using explicit stride tracking, delayed curriculum activation, zero-command stand-still behavior, and Isaac Lab and ROS 2 deployment paths.
- Notes: An unofficial SLR fork, not a new peer-reviewed paper. The README warns to respect upstream non-commercial licensing; no root LICENSE was found through the API. Of particular interest for command-conditioned gait control and avoiding reward loopholes at zero velocity.

### ultimate-max/HimLoco-AMP-Lab
- Link: https://github.com/ultimate-max/HimLoco-AMP-Lab
- Category: RL / AMP / locomotion / sim-to-sim
- Robot Type: quadruped (Unitree Go2); ChituMax legged platform
- Simulator: Isaac Lab (Isaac Sim 5.1); MuJoCo sim-to-sim
- Deploy: sim
- Summary: Isaac Lab framework providing PPO and adversarial-motion-prior velocity tracking, six-frame history observations, terrain curricula, domain randomization, motion replay, TorchScript/ONNX export, and MuJoCo sim-to-sim execution.
- Notes: BSD-3-Clause project code. AMP expert trajectories are intentionally not distributed and must be provided with permission; pure PPO is usable without them. Sim-to-sim does not establish hardware deployability.

### Ryon-droid/bpx-rl-train
- Link: https://github.com/Ryon-droid/bpx-rl-train
- Category: RL / training framework / benchmark tooling
- Robot Type: quadruped (MIRRORME BPX)
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.1; RSL-RL PPO
- Deploy: sim
- Summary: External Isaac Lab project with flat, mixed-terrain and stairs velocity-tracking tasks and a documented 45-D actor / 12-D action interface; includes full trained checkpoints, TorchScript/ONNX policies, run configs and evaluation reports for flat walking and dedicated stairs.
- Notes: BSD-3-Clause. Explicitly simulation-only; does not include robot SDK or physical deployment. Useful as a reproducible training and evaluation baseline rather than a new locomotion algorithm.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### PHUMA: Physically Reliable Humanoid Locomotion Dataset
- Link: https://huggingface.co/datasets/DAVIAN-Robotics/PHUMA
- Category: robot motion / video-derived motion / retargeting
- Subject: Unitree G1 and H1-2 humanoids; human mocap and internet-video motion sources
- Content: The paper reports a 73-hour complete motion corpus; the public Hugging Face repository is a 3.42-GB partial release and excludes LAFAN1- and LocoMuJoCo-derived motions under upstream licenses.
- Format: compressed archive of per-clip .npy arrays containing root translation, root quaternion, joint positions and fps
- Access: open partial release; additional upstream-licensed parts via instructions and reconstruction
- License: Apache-2.0 on the Hugging Face dataset card; source datasets retain independent upstream restrictions
- Summary: Physics-aware filtering and physics-constrained motion retargeting produce robot-executable locomotion references; the authors show real-G1 tracking transfer. Released data and the reconstruction instructions are accessible.
- Notes: CoRL 2026 Spotlight, paper https://arxiv.org/abs/2510.26236 , code https://github.com/DAVIAN-Robotics/PHUMA . This is a newly curated older dataset, not a 2026-10-28 release. The public subset should not be mistaken for the complete 73-hour set.

### FLoRe Force-Annotated Demonstrations (watch candidate; not released)
- Link: https://louis-leee.github.io/FLoRe/
- Category: robot motion / contact-force demonstrations
- Subject: human-held dual UMI-style force-sensing grippers, body trackers; humanoid loco-manipulation
- Content: Force/wrench measurements plus hand, torso and foot movement used to train the FLoRe policy; number of demonstrations not disclosed on the project page
- Access: not released; watch candidate only
- License: not stated
- Summary: Force-annotated robot-free demonstrations for force-reactive humanoid tasks, but a public data download could not be verified.
- Notes: Keep out of the formal datasets.md until downloadable and license can be checked; project currently marks code coming soon.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Hae-Won Park / KAIST (new paper signal)
- Institution: KAIST
- Homepage: https://diffcontact.github.io/
- Lab / Department: legged locomotion and differentiable contact research team
- Key Topics: quadruped / frictional contact / differentiable dynamics / optimal control / sim-to-real
- Notes: Gijeong Kim, Seungbin Oh, Dongyun Kang and Hae-Won Park introduce a backward-only smooth contact gradient for fast policy learning and CITO (arXiv:2610.35852); hardware demonstrations and a detailed project page are public. Formal venue is a T-RO submission, not an acceptance.

### Amazon Frontier AI & Robotics (existing network update)
- Institution: Amazon FAR, with NYU, Carnegie Mellon University and University of Chicago collaborators
- Homepage: https://louis-leee.github.io/FLoRe/
- Lab / Department: Frontier AI & Robotics
- Key Topics: humanoid / loco-manipulation / force-reactive control / learning from demonstrations / whole-body RL
- Notes: FLoRe (arXiv:2610.35862) adds a force-sensing UMI demonstration and hybrid force/compliance control direction to an already tracked network with RPL. Project page states the three-task real-robot results and code-coming-soon status.

### DAVIAN Robotics / KAIST AI (dataset signal)
- Institution: KAIST AI, with KRAFTON and Holiday Robotics collaborators
- Homepage: https://davian-robotics.github.io/PHUMA/
- GitHub: https://github.com/DAVIAN-Robotics/PHUMA
- Lab / Department: DAVIAN Robotics
- Key Topics: humanoid / motion datasets / physics-aware retargeting / imitation / sim-to-real
- Notes: PHUMA was accepted as a CoRL 2026 Spotlight and released a G1/H1-2 data pipeline and partial downloadable dataset; the complete corpus relies on separately licensed sources.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Aarhus University / A3 Lab (existing draft: deadline follow-up, not a new opening)
- Type: PhD
- Location: Aarhus, Denmark
- Source: official university posting — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: physical AI / VLA / world models / robot learning / test-time adaptation / edge inference
- Status: active
- Notes: Official site is still accessible on 2026-10-28. Three-year position with Behzad Bozorgtabar and Qi Zhang; previously covered in the 2026-10-26 draft. Embodied AI adjacent to legged robotics, not legged-specific. No duplicate new-job insertion proposed.

### TUM / Autonomous Vehicle Systems Lab (existing draft: deadline follow-up, not a new opening)
- Type: PhD / Research Associate
- Location: Garching, Germany
- Source: official lab posting — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: humanoid / whole-body control / perception / mobile manipulation / VLM / VLA
- Status: active
- Notes: The official site still displays the 3-year TV-L E13 (100%) opening and asks for fluent German and English. Previously covered in the 2026-10-25 draft. The page mislabels the weekday for its numerical deadline; use 2026-11-15, not the weekday. No duplicate new-job insertion proposed.

</details>
