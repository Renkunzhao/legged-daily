**English** | [中文](../zh/drafts/legged-daily-2026-07-31.md)
# Legged Daily - 2026-07-31

## Summary
- PAC-MAN is today's strongest paper signal: it couples whole-body control-barrier guidance with onboard masked-depth perception, then transfers a lightweight policy zero-shot to a Unitree G1 and reports 19/20 successful real-world dodges with no falls.
- The paper's key systems lesson is that stronger safety structure is useful only when perception keeps the threat observable: Joint-CBF guidance degrades with a fixed camera but recovers with active tracking or privileged state, while the simpler Link-CBF policy remains deployable from onboard sensing.
- Three substantive implementation repositories met the repo bar: a G1 walking/balance/fall-safe Isaac Lab task suite, a documented SpotMicro RL development history spanning 18 checkpoints, and an Apache-2.0 wheel-legged balance/jumping curriculum with a released checkpoint.
- Caltech AMBER Lab remains a high-priority humanoid safety/control source through PAC-MAN, following its recent HANDOFF and MPC-RL work. No new lab should be added solely from this paper, but the repeated real-G1 deployments strengthen the existing source signal.
- No new job opening met the novelty bar. The previously tracked LAAS-CNRS Gepetto safe-RL humanoid PhD remains active at verification and closes today, 2026-07-31 at 23:59.

<details>
<summary><strong>New Papers</strong></summary>

### PAC-MAN: Perception-Aware CBF-RL for Whole-Body Safety in Humanoid Dodgeball
- Link: https://arxiv.org/abs/2607.28623
- Source: arXiv / official project page
- Date: 2026-07-30
- Authors: Lizhi Yang, Junheng Li, Aaron D. Ames
- Topics: humanoid safety / control barrier functions / reinforcement learning / onboard perception / whole-body control / sim-to-real / Unitree G1
- Summary: PAC-MAN trains whole-body humanoid dodge behaviors with per-link or joint-space CBF guidance while restricting the deployed policy to proprioception and segmentation-masked depth from a head-mounted camera.
- Notes: The fixed-camera Link-CBF policy transfers to a physical Unitree G1 without fine-tuning and reports 19 successful dodges in 20 hand throws, zero falls, and recovery walks between throws. Joint-CBF performs best with accurate ball state but loses effectiveness when fixed-camera observations lose the threat; a tracking gimbal or privileged runtime filter restores the advantage. Project page: https://lzyang2000.github.io/perceptive_cbf_rl/.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### ductnguyen-dtn/g1-humanoid-locomotion
- Link: https://github.com/ductnguyen-dtn/g1-humanoid-locomotion
- Category: reinforcement learning / locomotion / balance / fall safety / debugging notes
- Robot Type: humanoid; Unitree G1
- Simulator: NVIDIA Isaac Lab / Isaac Sim with RSL-RL training entry points
- Deploy: simulation tasks only; real-robot deployment is not demonstrated
- Summary: A compact set of G1 Isaac Lab tasks for flat-ground velocity tracking, standing balance with push recovery, and fall-safe behavior, covering curated and self-imported 29-DoF assets.
- Notes: The repository documents two useful failure modes: near-zero imported inertias can destabilize PhysX, and fall-shaping rewards cannot train when pushes rarely induce a fall or episodes terminate before landing. It provides environment configurations and setup instructions but no trained policy weights or hardware result; no repository license was detected at verification.

### ductnguyen-dtn/spotmicro-locomotion
- Link: https://github.com/ductnguyen-dtn/spotmicro-locomotion
- Category: reinforcement learning / low-cost quadruped / asset debugging / experiment tracking
- Robot Type: quadruped; hand-built SpotMicro with 12 MG996R servos
- Simulator: NVIDIA Isaac Lab / Isaac Sim
- Deploy: physical robot bring-up and calibration are documented, but the learned gait is currently a simulation result and policy weights are not included
- Summary: An Isaac Lab SpotMicro locomotion project that preserves the full path from a world-welded URDF/USD failure to stable forward walking, with 18 promoted checkpoints and rejected ablations recorded alongside matching configuration snapshots.
- Notes: The strongest reusable lesson is diagnostic: nonzero policy actions with exactly zero base motion revealed a fixed root joint rather than an RL failure. The current simulation baseline still has a documented rear-leg gait asymmetry; the repository does not claim a solved or hardware-deployed learned gait. No repository license was detected, although the credited upstream SpotMicro firmware/ROS project is MIT-licensed.

### zyicome/Wheel-Legged-Lab
- Link: https://github.com/zyicome/Wheel-Legged-Lab
- Category: reinforcement learning / wheel-legged balance / jumping / curriculum learning / VMC
- Robot Type: two-wheel, two-leg underactuated robot
- Simulator: NVIDIA Isaac Lab 2.3.2 / Isaac Sim 5.1.0 with RSL-RL PPO
- Deploy: simulation only; no completed sim-to-real validation
- Summary: An Apache-2.0 Isaac Lab project that maps policy outputs through virtual model control and progressively trains balance, velocity/yaw tracking, height control, staged jumping, in-air leg retraction, moving jumps, target landing, and oracle obstacle crossing.
- Notes: The repository includes a released moving-jump checkpoint, TensorBoard events, videos, staged-training scripts, and robot assets. Its README reports simulation demonstrations up to a 7 cm obstacle and clearly labels the work as a learning/reproduction project without physical deployment or multi-seed statistical validation.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Caltech AMBER Lab / Aaron D. Ames
- Institution: California Institute of Technology
- Homepage: https://amber.caltech.edu/
- Source: https://arxiv.org/abs/2607.28623 and https://lzyang2000.github.io/perceptive_cbf_rl/
- Key Topics: humanoid safety / control barrier functions / reinforcement learning / whole-body control / onboard perception / sim-to-real
- Notes: PAC-MAN is a new update from the already tracked AMBER source network. It extends the group's recent humanoid control work from interfaces and MPC-guided RL toward reactive whole-body safety under partial onboard perception, with a zero-shot Unitree G1 hardware evaluation. Treat this as an update to the existing lab entry rather than a new lab addition.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto Team — PhD in Humanoid Robotics: Safe Reinforcement Learning
- Type: PhD
- Location: Toulouse, France, with part of the project at CNRS-AIST JRL in Tsukuba, Japan
- Source: official website — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59
- Topics: humanoid / legged locomotion / reinforcement learning / MPC / whole-body control / safe control
- Status: active at verification; final-day reminder for a previously tracked opportunity
- Notes: The official page remained reachable on 2026-07-31. The 36-month thesis combines RL-based discrete decisions over contacts, footsteps, gaits, and behavior transitions with online MPC for feasible continuous whole-body motion, with planned validation on PAL Robotics Kangaroo and/or Unitree H1/R1. No new job addition is proposed today; if the page closes after the deadline, review this entry for stale removal in the next run.

</details>
