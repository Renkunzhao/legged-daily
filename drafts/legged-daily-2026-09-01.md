**English** | [中文](../zh/drafts/legged-daily-2026-09-01.md)
# Legged Daily - 2026-09-01

## Summary
- SleepWalking (SWAQ) reframes blind locomotion under partial observability as an information-retention problem and reports better terrain progression than DWAQ with lower inference cost.
- IIT's HHCM line presents a compact 2-DoF humanoid ankle actuator in which two customized cams share one gas spring for pitch/roll torque compensation.
- Three new Unitree G1 repositories cover terrain-relative rough-terrain control and sim-to-sim transfer, estimator-aware RL, and risk-aware search-and-rescue navigation; all are early-stage and currently lack detected licenses.
- The paper affiliations add a Northwestern Polytechnical University–Shanghai Jiao Tong University–Yunmu network around blind locomotion and a new actuator-design signal from IIT HHCM.
- Two previously tracked opportunities need cleanup: EPFL BioRob now marks its humanoid-locomotion PhD/postdoc positions CLOSED, and the Inria Auctus quadruped co-design PhD deadline has passed.

<details>
<summary><strong>New Papers</strong></summary>

### SleepWalking: Privileged Representation Shaping for End-to-End Blind Locomotion in Legged Robots
- Link: https://arxiv.org/abs/2608.30883
- Source: arXiv
- Date: 2026-08-31
- Authors: Zheng Pan, Tenghui Wang, Peilin Li, Shiyu Zhou, Hao Sun, Yan Ma, Liang Yu, Liang He
- Topics: blind legged locomotion / reinforcement learning / representation learning / privileged information / partial observability
- Summary: Introduces SWAQ, a one-stage recurrent actor-critic that uses next-step privileged physical reconstruction to shape a history representation during training while deploying a direct proprioceptive-history-to-action policy without an explicit estimator output in the control path.
- Notes: Under aligned settings, the authors report a 15.0% higher peak mean terrain level than DWAQ and 44.4% fewer inference MACs per control step. The paper includes representation probes and theoretical analysis, but the accessible official sources reviewed today do not expose a code or project-page link.

### A Dual-Cam Parallel Elastic Actuator with Shared Gas-Spring Compensation for Humanoid Ankles
- Link: https://arxiv.org/abs/2608.30832
- Source: IEEE AIM 2026 / arXiv
- Date: 2026-08-31
- Authors: Jingcheng Jiang, Yifang Zhang, Nikos G. Tsagarakis
- Topics: humanoid / actuator / parallel elasticity / ankle / mechanical optimization
- Summary: Proposes a 2-DoF humanoid ankle PEA that uses two customized cam modules and one shared gas spring to provide coupled pitch/roll torque compensation in a compact lower-leg package.
- Notes: The work derives a coupled model and optimization procedure for synthesizing cam profiles from target torque curves, then validates the concept through lower-leg CAD integration, kinematic simulation, and static FEA. The current evidence is design/simulation validation rather than a physical prototype experiment.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### humanoid-g1-locomotion
- Link: https://github.com/hrx2025lucky-lab/humanoid-g1-locomotion
- Category: RL
- Robot Type: humanoid
- Simulator: Isaac / MuJoCo
- Deploy: sim
- Summary: A Unitree G1 locomotion workspace that currently implements terrain-relative rough-terrain observations/rewards in Isaac Lab and an Isaac Lab-to-MuJoCo sim-to-sim validation path with explicit joint, observation, PD, action-scale, and control-rate alignment.
- Notes: The repository documents a concrete failure mode in which world-frame root-height terms falsely terminate robots on descending terrain, and replaces them with terrain-relative height scans. The broader 11-part roadmap is mostly unfinished; no hardware result is claimed and no license was detected as of 2026-09-01.

### G1-EKF-Locomotion
- Link: https://github.com/baodo0710/G1-EKF-Locomotion
- Category: RL
- Robot Type: humanoid
- Simulator: Isaac
- Deploy: sim
- Summary: A work-in-progress Isaac Lab extension that replaces privileged Unitree G1 base linear velocity with a Kalman-filtered estimate fusing IMU integration and stance-leg odometry, and trains PPO directly against that sensor-derived state.
- Notes: The maintainer reports 0.26 m/s estimator MAE and a converged flat-terrain policy, while rough-terrain gait pathology and ESKF/sim-to-real work remain on the roadmap. The implementation is very new, results are maintainer-reported, and no license was detected as of 2026-09-01.

### unitree-g1-risk-aware-navigation
- Link: https://github.com/TFGUnitreeG1/unitree-g1-risk-aware-navigation
- Category: toolkit
- Robot Type: humanoid
- Simulator: Isaac
- Deploy: sim
- Summary: Integrates trained G1 locomotion checkpoints, waypoint navigation, RGB-D/YOLO terrain classification, a spatial risk map, adaptive waypoint routes, simulated search-and-rescue scenarios, and experiment post-processing tools.
- Notes: The repository includes three locomotion checkpoints, USD scenarios, route files, and evaluation scripts, but YOLO weights are external and the reviewed materials do not claim real-hardware validation. No license was detected as of 2026-09-01.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Northwestern Polytechnical University / Shanghai Jiao Tong University blind-locomotion collaboration
- Institution: Northwestern Polytechnical University / Shanghai Jiao Tong University / Yunmu Intelligent Manufacturing Co., Ltd.
- Homepage: https://arxiv.org/html/2608.30883v1
- arXiv: https://arxiv.org/abs/2608.30883
- Lab / Department: paper affiliation network
- Key Topics: quadruped / blind locomotion / reinforcement learning / representation learning / partial observability
- Notes: SWAQ links corresponding authors Liang Yu and Liang He at Northwestern Polytechnical University with Tenghui Wang and Shiyu Zhou at Shanghai Jiao Tong University and Peilin Li at Yunmu. This is a useful new source network for proprioception-only locomotion and learned history representations.

### Humanoids and Human Centered Mechatronics (HHCM) Research Line
- Institution: Istituto Italiano di Tecnologia
- Homepage: https://arxiv.org/html/2608.30832v1
- arXiv: https://arxiv.org/abs/2608.30832
- Lab / Department: Humanoids and Human Centered Mechatronics Research Line
- Key Topics: humanoid / actuation / parallel elasticity / mechanical design / energy efficiency
- Notes: Jingcheng Jiang, Yifang Zhang, and Nikos G. Tsagarakis add a compact shared-spring humanoid ankle design to IIT's humanoid mechatronics stream. This complements the repository's existing IIT Dynamic Legged Systems source with a distinct hardware/actuator signal.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Proposed Removal / Stale Item — EPFL BioRob humanoid locomotion PhD and postdoc
- Current Status: no longer actionable
- Reason: The official BioRob openings page now labels the Fall 2026 humanoid-neuromechanics PhD and postdoc opening CLOSED and states that the positions are closed.
- Source Checked: EPFL BioRob official openings page — https://www.epfl.ch/labs/biorob/openings/

### Proposed Removal / Stale Item — Inria Auctus / LAAS-CNRS Gepetto quadruped co-design PhD
- Current Status: expired
- Reason: The official application deadline was 2026-08-31, which has passed; the item should stop being surfaced as active unless the official page explicitly extends or reopens it.
- Source Checked: Inria official posting — https://jobs.inria.fr/public/classic/en/offres/2026-10319

</details>
