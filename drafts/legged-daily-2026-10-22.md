**English** | [中文](../zh/drafts/legged-daily-2026-10-22.md)
# Legged Daily - 2026-10-22

## Summary
- SuperMimic trains a humanoid motion tracker through one differentiable world model; it reports surpassing a 7-day, 128-GPU baseline in 3 GPU-hours and transfers to a Unitree G1.
- "Watch Your Step" predicts upcoming footholds and samples the elevation map only around them, reaching a given terrain difficulty in about a third of the training iterations and transferring zero-shot to a Unitree G1.
- An ETH RSL team trains a single end-to-end quadruped jumping policy for lunar gravity, with a hardware vertical jump under gravity offloading.
- HoloMotion v2.0 (2026-10-12) adds one sparse-to-whole-body G1 policy with a public checkpoint; RoboParty's RP1 open-source humanoid platform launched 2026-10-15 with hardware, firmware, and training repositories.
- No new lab/professor signal or job opening was verified today; no code links were found for the three papers above.

<details>
<summary><strong>New Papers</strong></summary>

### SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model
- Link: https://arxiv.org/abs/2610.28480
- Source: arXiv
- Date: 2026-10-20
- Authors: Qiayuan Liao, Yiyang Shao, Junfeng Long, Kevin Zakka, Roberto Horowitz, Pieter Abbeel, Koushil Sreenath
- Topics: humanoid whole-body control / motion tracking / differentiable world model / scaling / sim-to-real
- Summary: Fits one differentiable world model of shared dynamics from logged rigid-body-simulator transitions and trains it jointly with the tracking policy, using backpropagation through short imagined rollouts to give analytic policy gradients.
- Notes: The abstract reports exceeding a state-of-the-art tracker trained for 7 days on 128 GPUs within 3 hours on one GPU, more than 1000× fewer GPU-hours, and 25 failures out of 129,514 benchmark motions versus 179 for the baseline (zero after 9.8 hours on two GPUs). Transfers to a physical Unitree G1 on diverse and acrobatic motions. No code link was found; results not independently reproduced.

### Watch Your Step: Anticipated Perception for Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.29612
- Source: arXiv
- Date: 2026-10-21
- Authors: Matthias Heyrman, Chenhao Li, Ioannis Dadiotis, Marco Hutter
- Topics: perceptive locomotion / foothold prediction / elevation map / humanoid / zero-shot transfer
- Summary: A lightweight foothold prediction model, trained alongside the policy from proprioception and the velocity command, selects small elevation-map patches around predicted footholds so the policy sees only step-relevant terrain.
- Notes: The abstract reports reaching a given terrain difficulty in roughly a third of the training iterations versus the full map, better results where footholds are sparse and on unseen terrain, and parity with an attention-based encoder trained at several times the cost. Zero-shot transfer to a Unitree G1 on obstacles, stairs, gaps, and step-downs indoors and outdoors. No code link was found.

### End-to-End Reinforcement Learning for Quadrupedal Jumping in Lunar Gravity
- Link: https://arxiv.org/abs/2610.29586
- Source: arXiv
- Date: 2026-10-21
- Authors: Levin Müller, Oliver Fischer, Marco Trentini, Yusuke Tanaka, Marco Hutter
- Topics: quadruped / jumping / planetary exploration / reinforcement learning / sim-to-real
- Summary: A multistage RL approach yields one end-to-end policy for commanded point-to-point jumping under lunar gravity using only mission-compatible onboard sensing.
- Notes: In simulation, landing errors are smaller than the robot's body size, and the authors analyze torque/power demands and robustness to control-update freezes of up to 1 s in flight. Hardware shows a vertical jump under lunar-gravity offloading with torque and power profiles consistent with simulation; point-to-point jumps are shown in simulation only per the abstract.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### HorizonRobotics/HoloMotion
- Link: https://github.com/HorizonRobotics/HoloMotion
- Category: control / motion tracking / retargeting / teleoperation
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo (sim2sim replay)
- Deploy: both
- Summary: Apache-2.0 foundation-model stack for humanoid whole-body control, covering retargeting (HoloRetarget), motion-tracking policy training, ONNX policy bundles, and real-robot G1 deployment.
- Notes: The 2026-10-12 v2.0 update provides one policy for sparse-to-whole-body control with initial 1-point and 5-point real-robot teleoperation, and the v2.0.0 checkpoint is on Hugging Face; the README marks v2.0 as a preview with real-robot gait and tracking quality still being refined. The README schedules the HoloMotion-2 technical report and v2.1 for late October 2026. Related: HoloMotion-1 Technical Report in papers.md.

### Roboparty/RP1
- Link: https://github.com/Roboparty/RP1
- Category: toolkit / hardware platform
- Robot Type: humanoid
- Deploy: hardware
- Summary: Overview repository for RoboParty's fully open-source humanoid platform, linking mechanical, electronics, firmware, robot-description, deployment, and training sub-repositories (24/28/30/42-DoF variants).
- Notes: The overview repo is GPL-3.0 and each sub-repository carries its own license (a third-party summary lists CERN-OHL-W-2.0 for hardware). Training lives in `roboparty_train` (locomotion, motion imitation, behavior foundation models); the README's demo section is "Coming soon". The public launch date of 2026-10-15 comes from a third-party GitHub issue, not the README. Related: Roboparty/UFO in repos.md.

### iit-DLSLab/morphosymm-rsl-rl
- Link: https://github.com/iit-DLSLab/morphosymm-rsl-rl
- Category: RL / toolkit
- Robot Type: general / legged
- Simulator: Isaac Lab
- Deploy: sim
- Summary: BSD-3-Clause extension of RSL-RL PPO that uses morphological symmetries for legged locomotion, through symmetry data augmentation and explicit equivariant networks built on `symmetric_learning`.
- Notes: The README badges show Isaac Lab v3.0.0 and rsl-rl v5.4.2; mjlab appears only as a repository topic. The GitHub topic page showed a 2026-10-09 update, which could not be confirmed on the repository page. Related papers: Morphological Symmetries in Robotics (IJRR 2025) and Leveraging Symmetry in RL-based Legged Locomotion Control (IROS 2024).

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No newly verified lab or professor signal in this run.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No newly verified opening
- Type: PhD / RA / Internship / Research Engineer / Postdoc
- Source: official-source review
- Deadline: unknown
- Topics: humanoid / quadruped / locomotion / robot learning
- Status: watching
- Notes: No opening was confirmed on an official page. Existing entries remain unchanged; the previously proposed LAAS-CNRS safe-RL PhD removal (deadline 2026-07-31, expired) remains pending confirmation.

</details>
