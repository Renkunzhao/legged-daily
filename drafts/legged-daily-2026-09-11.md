**English** | [中文](../zh/drafts/legged-daily-2026-09-11.md)
# Legged Daily - 2026-09-11

## Summary
- CAP trains one Unitree G1 locomotion policy to adapt continuously across clean, corrupted, partially occluded, and missing depth rather than hard-switching between perceptive and blind controllers.
- Harness Robotic OS presents a deployed embodied-agent runtime that closes the loop from quadruped sensing and navigation to inspection reasoning, voice interaction, alarms, and structured enterprise reports.
- IIT's Dynamic Legged Systems team maps how gait, payload, stiffness, and damping interact when a quadruped carries loads through a passive mechanical interface.
- Repository signals include CAP's official project placeholder, an IROS 2026 origami-inspired humanoid description release, and a substantial same-day update to a multi-backend Unitree Go2 simulation and locomotion stack.
- No sufficiently specific, high-confidence new legged-robotics job posting was selected today from the official sources checked.

<details>
<summary><strong>New Papers</strong></summary>

### CAP: Continuously Adaptive Perception-Blind Humanoid Locomotion via Learned Denoising
- Link: https://arxiv.org/abs/2609.11553
- Source: arXiv / CoRL 2026
- Date: 2026-09-10
- Authors: Hongjin Chen, Zijun Xu, Shihao Ma, Yi Zhao, Xilai Liu, Ke Ma, Wei Zhang, Chunyang Xie, Pengfei Li, Jieru Zhao, Wenchao Ding
- Topics: humanoid locomotion / perceptive locomotion / learned denoising / sensor failure / sim-to-real
- Summary: Trains a single locomotion policy with a denoising perceptive world model, a co-active proprioceptive encoder, depth-noise curriculum, and feature dropout so control degrades smoothly as depth quality worsens, with Unitree G1 validation under occlusion, sensor corruption, and outdoor depth artifacts.
- Notes: [Project page](https://hoshi-no-ai.github.io/CAP/). The project reports 39/40 successful controlled trials under clean or partially occluded perception, while full camera cover remains limiting on gaps and platforms that require preview depth.

### Harness Robotic OS: A Unified Embodied-Agent Runtime for Closed-Loop Quadruped Inspection
- Link: https://arxiv.org/abs/2609.11225
- Source: arXiv
- Date: 2026-09-10
- Authors: Yaoyuan Yan, Zhiyou Heng, Haoxiang Jie, Gang Liu, Hongjie Yan, Wei Zhou
- Topics: quadruped inspection / embodied agent / autonomy stack / multimodal perception / human-robot interaction
- Summary: Introduces HROS and its Argos deployment, unifying robot runtime, autonomy skills, cognitive-agent context and memory, voice interaction, and safety-gated improvement into a traceable residential inspection loop.
- Notes: The prototype integrates a Vbot quadruped, Fast-LIO2, Hobot-Stereo, PCT-Planner, EGO-Planner, and Qwen3-VL analysis orchestrated through OpenClaw. Reported results include 100% waypoint reachability and 99% alarm/report success; these are author-reported deployment results and were not independently reproduced in this run.

### Gait-Dependent Effects on Quadruped Locomotion for Load-Carrying using Passive Mechanism
- Link: https://arxiv.org/abs/2609.11059
- Source: arXiv
- Date: 2026-09-10
- Authors: Giovanni B. Dessy, Claudio Semini, Victor Barasuol
- Topics: quadruped locomotion / payload carrying / passive mechanism / gait analysis / stability
- Summary: Studies passive-arm stiffness and damping across gait and payload conditions, showing that underdamped settings can increase passive-joint oscillation and reduce crawl-gait ZMP margin, while trot is retained as a dynamic excitation case rather than a direct ZMP comparison.
- Notes: The paper summarizes the design space as gait-payload-stiffness-damping maps. Current evidence is simulation-based flat-ground analysis rather than hardware validation.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Hoshi-No-Ai/CAP
- Link: https://github.com/Hoshi-No-Ai/CAP
- Category: project page / upcoming locomotion code
- Robot Type: humanoid / Unitree G1
- Simulator: not yet released
- Deploy: hardware demonstrations documented; code pending
- Summary: Official companion repository for CAP, collecting the paper, project site, and videos for a perception-robust humanoid locomotion policy that continuously adapts to changing depth quality.
- Notes: Created 2026-09-11. The README explicitly says training and deployment code are still being prepared; the `main` branch is currently a placeholder and must not be treated as a usable code release.

### sattwik-sahu/iros2026-origami-robot
- Link: https://github.com/sattwik-sahu/iros2026-origami-robot
- Category: robot description / simulation assets
- Robot Type: origami-inspired humanoid
- Simulator: RViz / Gazebo Sim / NVIDIA Isaac Sim
- Deploy: simulation and visualization assets
- Summary: Releases URDF, more than 100 links and 118 STL meshes, USD/PhysX assets, ROS 2 Jazzy launch files, and Docker workflows for the NORTH POC2.2 humanoid platform prepared alongside an IROS 2026 submission.
- Notes: Created 2026-09-10 with zero stars at check time. This is a robot-description and visualization/simulation package, not a released locomotion controller or demonstrated sim-to-real stack; no standard SPDX license was detected by the GitHub API.

### darshmenon/quadruped-robotics-stack
- Link: https://github.com/darshmenon/quadruped-robotics-stack
- Category: locomotion / RL / classical control / autonomy stack
- Robot Type: quadruped / Unitree Go2
- Simulator: MuJoCo / Gazebo Harmonic / Isaac training path
- Deploy: simulation; hardware deployment not verified
- Summary: Combines PPO locomotion, CHAMP, Quad-SDK NMPC, ROS 2, terrain worlds, SLAM/navigation demos, recovery training, and pretrained-policy plumbing in one Go2-centered workspace.
- Notes: Updated 2026-09-11 with a legs-only MuJoCo mode intended to align checkpoint dimensions with its Gazebo environment. The README distinguishes working Go2 paths from stubs and documents several known training issues; 18 stars and no detected repository license at check time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### CAP collaboration network
- Institution: Fudan University / TARS Robotics / Shanghai Innovation Institute / Harbin Institute of Technology / Shanghai Jiao Tong University
- Homepage: https://hoshi-no-ai.github.io/CAP/
- GitHub: https://github.com/Hoshi-No-Ai/CAP
- Key Topics: humanoid locomotion / perception robustness / learned world models / sim-to-real
- Notes: The CoRL 2026 CAP project is a new multi-institution signal centered on perception-robust Unitree G1 locomotion. It connects Fudan and TARS Robotics with Shanghai Innovation Institute, HIT, and SJTU through a concrete paper, project page, hardware video, and planned code release.

### Dynamic Legged Systems Lab / IIT
- Institution: Istituto Italiano di Tecnologia
- Homepage: https://dls.iit.it/
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: quadruped control / payload transport / passive mechanisms / whole-body dynamics
- Notes: Giovanni B. Dessy, Claudio Semini, and Victor Barasuol released a gait-dependent passive payload-carrying study. It extends the lab signal beyond locomotion control alone toward co-design of gait and mechanical payload interfaces.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently specific, currently actionable new legged-robotics opening was selected today from the official careers sources checked. General careers pages, reposts, and openings without a verifiable active role or direct legged-robotics connection were omitted rather than inferred. No stale-item removal is proposed today.

</details>
