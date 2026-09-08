**English** | [中文](../zh/drafts/legged-daily-2026-09-08.md)
# Legged Daily - 2026-09-08

## Summary
- CFAM proposes a frozen perception-reasoning-action backbone plus a gradient-free Capsule Field for one-shot, on-device post-deployment adaptation, evaluated across five embodiments including quadrupeds and humanoids.
- IIT's Dynamic Legged Systems Lab updated its BSD-3-Clause Isaac Lab stack for fault-tolerant quadruped locomotion, combining motor-failure environments with concurrent state estimation, rapid motor adaptation, mixture-of-experts policies, symmetry handling, MuJoCo transfer, and ROS 2 deployment.
- SimForge offers one JAX RL interface across Genesis, Newton, and MuJoCo, with 30 validated robot-task-simulator combinations and reported hardware deployment on Unitree G1/Go2 and Booster K1.
- Rhoyn's walking benchmark now places 29 open-source Unitree G1 policies behind one C++ interface and reports 471,424 disturbance-recovery runs across MuJoCo and PhysX; its results also expose substantial robustness and licensing variation.
- The strongest source signals today are IIT DLS for fault-tolerant locomotion and the Skylark Labs–CMU–UC Berkeley collaboration for continual post-deployment Physical AI; no fresh official job opening was verified.

<details>
<summary><strong>New Papers</strong></summary>

### Continual Field-Adaptive Models (CFAMs) for Post-Deployment Physical AI
- Link: https://arxiv.org/abs/2609.04552
- Source: arXiv
- Date: 2026-09-03
- Authors: Amarjot Singh, Tanmay R. Pancholi, Jainam Kothari, Shrirang Mahajan, Ketan Bansal, Zackory Erickson, Giuseppe Loianno, Alexandre M. Bayen, Jeff Schneider, Vince Nakayama
- Topics: physical AI / continual learning / quadruped / humanoid / VLA / on-device adaptation
- Summary: Introduces a multi-embodiment architecture with frozen Sensor, Reasoning, and Action modules plus a fast Capsule Field that stores verified near-out-of-distribution experience through one-shot, gradient-free on-device updates.
- Notes: Evaluation covers a manipulator, quadruped, humanoid, quadrotor, and off-road vehicle. The paper reports reaching a full-data policy operating point with 40% of the prior-training trajectories, a 13.9-percentage-point test-time action-success gain from autonomous near-OOD capture, and -0.5-point backward transfer versus -11.4 for LoRA. Open-world novelty is explicitly outside scope, and no public code release was verified.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### fault-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- Category: RL
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Provides Isaac Lab Direct environments and deployment paths for quadruped locomotion under motor failures, with Go2 and Pegasus configurations spanning flat/rough terrain, blind/vision policies, sim-to-sim, and ROS 2 sim-to-real.
- Notes: The BSD-3-Clause repository was updated on 2026-09-08. Its documented building blocks include concurrent state estimation, rapid motor adaptation, mixture-of-experts policies, morphological symmetries, the lab's MUSE estimator, and Unitree ROS 2 communication; compatibility remains tied to the tested Isaac Lab and rsl_rl versions.

### SimForge
- Link: https://github.com/jsw7460/SimForge
- Category: RL
- Robot Type: general
- Simulator: Genesis / Newton / MuJoCo
- Deploy: both
- Summary: A JAX-based, simulator-agnostic RL framework for training and cross-simulator evaluation through one API, with locomotion and motion tasks for Unitree G1/Go2, Booster T1/K1, and manipulation support for I2RT YAM.
- Notes: The project documents 10 task configurations across all three simulators, PPO/SAC/TD3 parity checks against Stable-Baselines3, domain randomization, motion tracking, and hardware demonstrations on G1, Go2, and K1. Its umbrella repository pins simulator stacks as submodules; no repository-level license was detected, so reuse terms should be checked component by component.

### teleop-walking-benchmark
- Link: https://github.com/rhoyn/teleop-walking-benchmark
- Category: toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / PhysX
- Deploy: sim / browser
- Summary: Ports 29 open-source Unitree G1 walking policies to a common C++ interface and compares disturbance recovery over a shared 60-second waypoint tour in MuJoCo and PhysX.
- Notes: The current report aggregates 471,424 runs with random impacts up to 600 N and separately reports completion, tracking error, energy, and vibration. The best policies still fail roughly one fifth of tours, and some policies shift sharply across physics engines. Rhoyn's harness is MIT-licensed, but bundled/fetched policies retain mixed terms, including non-commercial, undeclared, and sim-only restrictions documented in NOTICE.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Dynamic Legged Systems Lab
- Institution: Istituto Italiano di Tecnologia (IIT)
- Homepage: https://www.dls.iit.it/
- GitHub: https://github.com/iit-DLSLab
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: quadruped / locomotion / fault tolerance / RL / MPC / state estimation / sim-to-real
- Notes: The 2026-09-08 update to `fault-locomotion-isaaclab` extends an already substantial open-source chain that includes basic Isaac Lab locomotion, Quadruped-PyMPC, JAX MPC, MUSE state estimation, distributed whole-body MPC, and Unitree deployment tooling. Maintainer Giulio Turrisi and lab lead Claudio Semini are useful sources for fault-tolerant and model-/learning-based legged control.
- Students and Representative Works:
  - [Giulio Turrisi](https://github.com/giulioturrisi) — [Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion](https://arxiv.org/abs/2606.25965)

### Skylark Labs-led CFAM collaboration
- Institution: Skylark Labs / Carnegie Mellon University / University of California, Berkeley
- Homepage: https://skylarklabs.ai/cfams.html
- arXiv: https://arxiv.org/abs/2609.04552
- Lab / Department: cross-institution Physical AI collaboration
- Key Topics: continual learning / physical AI / quadruped / humanoid / VLA / edge adaptation
- Notes: CFAM connects Skylark Labs with Zackory Erickson and Jeff Schneider at CMU and Giuseppe Loianno and Alexandre Bayen at UC Berkeley. It is a useful source network for multi-embodiment policies that must adapt after deployment under fixed onboard compute, although the current evidence is paper/project-page based and no public implementation was verified.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently fresh, active, and high-confidence legged-robotics opportunity was verified from an official source in this run.

</details>
