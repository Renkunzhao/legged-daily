**English** | [中文](../zh/drafts/legged-daily-2026-09-03.md)
# Legged Daily - 2026-09-03

## Summary
- WM-LOCO uses a recurrent world model to give a Unitree G1 predictive visual context for sparse footholds, reporting 93.3% average hardware success across stepping stones, stairs, and a gap.
- Safe-Stop separates emergency-stop control from a learned decision about whether stopping remains feasible, reporting 96.4% out-of-distribution stop success on G1.
- FOCUS replaces binary foot-contact gating with continuous per-foot forward-kinematics reliability and reports large odometry-error reductions in simulation and real humanoid trials.
- Two notable new code releases cover multi-IMU quadruped state estimation and a reproducible 13-policy G1 walking benchmark; a third provides an Apache-2.0 Python/MCP stack for a tabletop hexapod.
- The papers expose useful new source networks at D-Robotics and across UC Berkeley, CMU, and Stanford; no sufficiently fresh, high-confidence job opening was verified today.

<details>
<summary><strong>New Papers</strong></summary>

### World-Model-Augmented Visual Locomotion for Humanoids on Foothold-Constrained Terrain
- Link: https://arxiv.org/abs/2609.02542
- Source: arXiv
- Date: 2026-09-02
- Authors: Yuxi Liu, Lijun Han, Ziming Wang, Ao Zhang, Cong Yang, Wei Sui
- Topics: humanoid / visual locomotion / world models / reinforcement learning / foothold-constrained terrain
- Summary: Introduces WM-LOCO, which jointly trains a recurrent state-space world model and PPO policy so predictive features from proprioception and one onboard depth image guide Unitree G1 locomotion over sparse footholds without explicit foothold labels.
- Notes: The same onboard policy traverses stepping stones, stairs, and a gap on hardware with 93.3% average success. In simulation, the matched baseline reaches 0% on gaps and stepping stones, while WM-LOCO also improves stride efficiency and pelvis acceleration on stairs.

### Humanoid Safe Stop via Learned Stoppability Value
- Link: https://arxiv.org/abs/2609.02358
- Source: arXiv
- Date: 2026-09-02
- Authors: Junfeng Long, Pieter Abbeel, Koushil Sreenath, Roberto Horowitz, Guanya Shi, C. Karen Liu
- Topics: humanoid / safety / emergency stopping / reach-avoid / learned value estimation
- Summary: Casts emergency stopping as a reach-avoid problem and combines a learned stop policy with stop-probability and reach-avoidance estimators, committing to the stop only when both judge it recoverable and otherwise handing off to a damping fall policy.
- Notes: The project page reports 96.4% out-of-distribution stop success and a 3.89% unsafe-approval rate on Unitree G1. The stop policy and estimators are designed to transfer across upstream behaviors without retraining.

### FOCUS: Foot Observation Confidence for Robust Humanoid Proprioceptive Odometry
- Link: https://arxiv.org/abs/2609.02222
- Source: arXiv
- Date: 2026-09-02
- Authors: Kaixin Feng, Angsong Li, Shaopeng Zhang, Enyu Li, Peiwen Lin, Chuang Wang, You Li, Haiyu Lan
- Topics: humanoid / proprioceptive odometry / state estimation / EKF / foot reliability / Transformer
- Summary: Proposes continuous per-foot forward-kinematics reliability weights, learned from automatically generated simulation signals, to blend kinematic and IMU velocity estimates and adapt EKF observation covariance without hard contact switching.
- Notes: The deployed causal Transformer uses only IMU and joint kinematics. The authors report ATE reductions of 83.7% in simulated walking, 70.8% across 19 real walking segments, and 42.7% across four real dynamic-motion routines.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### DogLegs
- Link: https://github.com/YibinWu/DogLegs
- Category: toolkit
- Robot Type: quadruped
- Simulator: none
- Deploy: data
- Summary: A standalone C++17 estimator for main-body pose, velocity, and IMU errors using one body IMU, four leg-mounted IMUs, joint encoders, and foot forces, released with field datasets and an IROS 2025 paper link.
- Notes: The repository provides configurations for parking-lot, grass, asphalt-road, construction-site, and off-road sequences and does not require ROS at estimator runtime. It was created on 2026-09-03; no repository license was detected, so reuse terms remain unclear.

### teleop-walking-benchmark
- Link: https://github.com/rhoyn/teleop-walking-benchmark
- Category: toolkit
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: Ports 13 open-source Unitree G1 walking policies to one C++ interface and evaluates them on the same randomized waypoint tours and impact-recovery campaign in MuJoCo.
- Notes: The published 100-seed campaign contains 1,300 runs; GR00T-WBC completes 71/100 tours, while no policy completes every seed. The benchmark code is MIT, but checkpoint terms vary, including non-commercial, undeclared, and sim-only restrictions documented in NOTICE.

### palmimo-devkit
- Link: https://github.com/Jizai-inc/palmimo-devkit
- Category: toolkit
- Robot Type: hexapod
- Simulator: none
- Deploy: hardware
- Summary: An Apache-2.0 Python SDK, motion engine, MCP server, and agent-example stack for Palmimo, a Raspberry Pi 5 tabletop hexapod with an 18-servo tripod gait and a compute-only dry run that does not require connected hardware.
- Notes: The repository was created on 2026-09-02 and is explicitly marked pre-release. Hardware operation is supported, but manufacturing design files are not published and robot-learning simulation assets are only planned for progressive release.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### D-Robotics visual humanoid locomotion network
- Institution: D-Robotics / Beijing University of Posts and Telecommunications / Harbin Institute of Technology / Soochow University
- Homepage: https://arxiv.org/html/2609.02542
- arXiv: https://arxiv.org/abs/2609.02542
- Lab / Department: paper affiliation network led by D-Robotics
- Key Topics: humanoid / visual locomotion / world models / reinforcement learning / sparse footholds
- Notes: WM-LOCO adds an industry-led source network around fully onboard Unitree G1 depth-based locomotion. Corresponding author and project lead Wei Sui is affiliated with D-Robotics; the coauthor network also connects BUPT, HIT, and Soochow University.

### UC Berkeley / CMU / Stanford humanoid-safety collaboration
- Institution: University of California, Berkeley / Carnegie Mellon University / Stanford University
- Homepage: https://junfeng-long.github.io/safestop/
- arXiv: https://arxiv.org/abs/2609.02358
- Lab / Department: cross-institution paper collaboration
- Key Topics: humanoid / safe control / reach-avoid analysis / reinforcement learning / emergency stopping
- Notes: Safe-Stop links Junfeng Long with Pieter Abbeel, Koushil Sreenath, Roberto Horowitz, Guanya Shi, and C. Karen Liu, creating a useful cross-lab signal at the intersection of learned humanoid control and formal recoverability reasoning.
- Students and Representative Works:
  - [Junfeng Long](https://junfeng-long.github.io/) — [Humanoid Safe Stop via Learned Stoppability Value](https://junfeng-long.github.io/safestop/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently fresh, active, and high-confidence legged-robotics opportunity was verified from an official source in this run. General web search was degraded by bot challenges, so no unverified aggregator result was promoted into the draft.

</details>
