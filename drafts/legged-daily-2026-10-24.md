**English** | [中文](../zh/drafts/legged-daily-2026-10-24.md)
# Legged Daily - 2026-10-24

## Summary
- LocoManiLab (arXiv, 2026-10-22) introduces a humanoid loco-manipulation testbed with 234 tasks and 51.5 h of simulated teleoperation; its code and dataset are still marked coming soon.
- WholeBodyMem (arXiv, submitted to RA-L) uses object-event-guided memory for humanoid loco-manipulation and introduces the HuMeGo Unitree G1 benchmark. Its authors list datasets on Hugging Face, but file access could not be independently verified today.
- PhysibleMDM (arXiv, 2026-10-21) adds inference-time physical-feasibility constraints to motion diffusion without retraining, including bipedal dynamics tests.
- GitHub API review surfaced a new reproducible humanoid motion-tracking evaluator, an updated G1/ACP experimentation workspace, and a simulation-only G1 decoupled-control project.
- Angel Robotics' official active-jobs index lists a legged-locomotion RL research position in Daejeon; the posting dates from June and has an ambiguous countdown, so current application status merits reconfirmation.

<details>
<summary><strong>New Papers</strong></summary>

### LocoManiLab: A Unified Testbed for Data, Policies, Controllers, and Deployment in Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.30876
- Source: arXiv preprint (not yet confirmed peer-reviewed)
- Date: 2026-10-22
- Authors: Dewei Wang, Jinrui Han, Jiyuan Shi, Chenyun Zhang, Xianbo Lu, Jiabao Wu, Jiqin Feng, Jipeng Kong, Ping Luo, Chenjia Bai, Xuelong Li
- Topics: humanoid / loco-manipulation / data collection / benchmark / whole-body control / sim-to-real
- Summary: Integrates task definitions, demonstrations, policy training, controller comparisons and deployment tests: 234 atomic/compositional tasks across five household scene categories, 51.5 hours of simulated teleoperation, twelve evaluated policies and five whole-body controllers.
- Notes: Project https://locomanilab.github.io/ labels both code and dataset “Coming soon” as checked 2026-10-24; these are not verified open releases. The project page labels its launch 2026-10-23, while the first arXiv submission is 2026-10-22.

### Memory before Goal: Role of Pre-History Memory for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.31166
- Source: arXiv preprint; submitted to IEEE Robotics and Automation Letters (RA-L), not an acceptance
- Date: 2026-10-22
- Authors: Chenyuan Chen, Ran Ding, Lechen Zhang, Zewen He, Yoshihiko Nakamura
- Topics: humanoid / vision-language-action / object-centric memory / loco-manipulation / Unitree G1
- Summary: WholeBodyMem uses SAM3-tracked object events to select sparse pre-goal observation frames for cross-attention, addressing information lost during walking and manipulation; introduces the HuMeGo benchmark with six simulated and six real Unitree G1 tasks.
- Notes: Authors report success gains from 29.1% to 72.6% in simulation and 36.7% to 88.3% in real-world experiments under their protocol. Project https://memory-before-goal.github.io/; public project repository https://github.com/crystalccy1/MemoryBeforeGoal currently lists “Code and models: Coming soon.”

### PhysibleMDM: Enforcing Inference-Time Physical Feasibility Constraints on Motion Diffusion Models via Noise Optimization
- Link: https://arxiv.org/abs/2610.30500
- Source: arXiv preprint (venue acceptance not stated)
- Date: 2026-10-21
- Authors: Maximilian Stölzle, David Müller, Agon Serifi, Ruben Grandia, Espen Knoop, Moritz Bächer
- Topics: humanoid motion / diffusion / physical feasibility / inverse dynamics / biped
- Summary: Optimizes input noise at inference time with Sep-CMA-ES under kinematic constraints and inverse-dynamics cone-program tests, improving motion feasibility without retraining the diffusion generator.
- Notes: Paper reports 75% less ground penetration, 92% less self-collision penetration and 74% less slip on 100 SMPL motion styles, plus a bipedal robot dynamics evaluation; these are author-reported results, not proof of hardware deployment.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### MotionChallenge-Project/MotionChallenge-Core
- Link: https://github.com/MotionChallenge-Project/MotionChallenge-Core
- Category: benchmark / toolkit / evaluation
- Robot Type: humanoid
- Simulator: MuJoCo 3.17 (CPU batch evaluation)
- Deploy: sim
- Summary: Apache-2.0 evaluation kernel and controller adapter SDK for full-clip humanoid motion tracking, recording completion, first failure, alignment-aware error metrics, reproducible rollout traces, and provenance.
- Notes: Repository created 2026-10-23 and updated 2026-10-24; adapters currently reference GRIT, SONIC v1.1, HoloMotion v1.4.1, and PMT Flat. Model checkpoints and datasets are external to the core repository; benchmark claims require independent evaluation.

### xia112358/somaforge
- Link: https://github.com/xia112358/somaforge
- Category: toolkit / motion tracking / retargeting / RL
- Robot Type: humanoid (Unitree G1)
- Simulator: Isaac Lab 3.0 / Isaac Sim 6.2 / Newton 1.7
- Deploy: sim
- Summary: An existing G1 experimentation workspace updated on 2026-10-23 that combines whole-body tracking, expert-to-student distillation, contact-aware motion editing, prediction, and documentation for an ACP single-task reproduction.
- Notes: Apache-2.0; an update to a July 2026 repository rather than a newly created repository. The README describes a unified runtime, with training inputs/checkpoints downloaded separately; not an official ACP release.

### yezheng04/unitree-g1-23dof-decoupled-control
- Link: https://github.com/yezheng04/unitree-g1-23dof-decoupled-control
- Category: RL / control / evaluation
- Robot Type: humanoid (Unitree G1 23-DoF)
- Simulator: Isaac Lab 2.3.2 / Isaac Sim 5.1 / PhysX
- Deploy: sim
- Summary: Implements decoupled lower-body locomotion (13 policy actions covering legs and waist yaw) and independent ten-joint arm trajectories, with curriculum training, evaluation, and a released simulation checkpoint.
- Notes: Created 2026-10-22; Apache-2.0. The project explicitly presents a simulation engineering implementation, not validated real-robot transfer.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### HuMeGo — humanoid object-memory loco-manipulation benchmark (watch candidate)
- Link: https://huggingface.co/collections/ChenyuanC/humego-6ada5cbea74d4cc678c91c68
- Category: benchmark / robot field datasets / robot motion
- Subject: Unitree G1 (simulation and real robot)
- Content: Six simulation tasks with 100 training demonstrations and 90 test scenes per task, and six real-robot tasks with 15 demonstrations per task; object-event memory tests involving what/where/when/counting.
- Format: LeRobot v2.1 datasets; simulated head camera at 50 Hz and real head camera at 30 fps (as described by authors)
- Access: authors state publicly hosted on Hugging Face; actual dataset pages and files could not be independently opened as of 2026-10-24
- License: CC BY 4.0 (author repository statement; not independently checked on Hugging Face)
- Summary: A benchmark testing whether humanoid loco-manipulation policies retain task-critical observations encountered before the goal action, including six real-world Unitree G1 tasks.
- Notes: WATCH ONLY — independent download and license verification are required before insertion into formal datasets.md. Source README: https://github.com/crystalccy1/MemoryBeforeGoal .

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### LocoManiLab collaboration — China Telecom TeleAI and partner universities
- Institution: China Telecom Institute of Artificial Intelligence (TeleAI); University of Science and Technology of China; University of Hong Kong; Zhejiang University; Shanghai Jiao Tong University; ShanghaiTech University; Gamma Robotics
- Homepage: https://locomanilab.github.io/
- Lab / Department: LocoManiLab author collaboration network
- Key Topics: humanoid / loco-manipulation / data and benchmark design / whole-body control / sim-to-real
- Notes: The official project lists cross-institution authors and a 2026-10-23 project launch. Follow the testbed's planned code and dataset release, currently marked “Coming soon.”

### WholeBodyMem / HuMeGo collaboration — MBZUAI
- Institution: Mohamed bin Zayed University of Artificial Intelligence (MBZUAI; affiliation as listed in the project repository)
- Homepage: https://memory-before-goal.github.io/
- GitHub: https://github.com/crystalccy1/MemoryBeforeGoal
- Lab / Department: WholeBodyMem author team
- Key Topics: humanoid / object-guided memory / VLA / loco-manipulation / Unitree G1
- Notes: Chenyuan Chen and coauthors propose pre-history object-event memory and introduce HuMeGo (arXiv:2610.31166, submitted to RA-L). Track independent dataset access verification and forthcoming code/models.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Angel Robotics — RL-Based Legged Robot Locomotion Researcher (newly discovered listing)
- Type: Research Scientist / Research Engineer (contract position)
- Location: Daejeon, South Korea
- Source: official career posting — https://www.angel-robotics.com/ko/recruit/notice/51
- Deadline: rolling / until filled (official active-openings index); precise status merits reconfirmation
- Topics: quadruped / biped / reinforcement learning / MPC / WBC / sim-to-real / Isaac Sim / MuJoCo
- Status: watching
- Notes: Posted 2026-06-16, not a newly opened 2026-10-24 vacancy. The official active-openings index still lists the role, but its detail page displays “D-00”. Position specifies PhD qualification and locomotion RL, disturbance rejection and real-robot deployment; verify application availability before applying.

</details>
