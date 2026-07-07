**English** | [中文](../zh/drafts/legged-daily-2026-07-07.md)
# Legged Daily - 2026-07-07

## Summary
- Today had few clearly new legged-robotics arXiv items; the strongest paper signal is X-Morph, a cross-morphology human-motion prior pipeline for quadrupeds, hexapods, and quadruped manipulators.
- MPX is a high-signal JAX MPC / trajectory-optimization stack for legged robots, with examples for Talos, H1, Aliengo, and Go2.
- Teleopit is worth tracking for Unitree G1 whole-body teleoperation because it covers BVH / Pico 4 retargeting, MuJoCo simulation, sim-to-real, and HDF5 data recording.
- NJU-RLC's quadrupedal-agility repository connects a 2025 paper to released training, deployment, retargeting, and motion-capture assets for agile Go2 behaviors.
- EPFL BioRob has a Fall 2026 humanoid locomotion PhD/postdoc signal; RAI Institute lists active research scientist roles in Cambridge and Zurich.

<details>
<summary><strong>New Papers</strong></summary>

### Human Motion Priors for Scalable Robot Learning Across Morphologies
- Link: https://arxiv.org/abs/2606.30290
- Source: arXiv
- Date: 2026-06-29
- Authors: Guillaume Sartoretti et al.
- Topics: cross-morphology retargeting, locomotion, loco-manipulation, robot learning, human motion priors
- Summary: X-Morph converts human motion into deployable locomotion and loco-manipulation policies for non-humanoid legged robots including a quadruped, a hexapod, and a quadruped manipulator.
- Notes: Project page: https://maker-rat.github.io/morph/. Useful as a bridge between humanoid motion-data scaling and broader legged-robot morphology coverage.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### iit-DLSLab/mpx
- Link: https://github.com/iit-DLSLab/mpx
- Category: MPC / trajectory optimization / toolkit
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo MJX
- Deploy: sim
- Summary: JAX-based MPC and trajectory-optimization library for legged robots, emphasizing GPU-parallel KKT solves, autodiff/vectorization, and whole-body MJX examples.
- Notes: README lists examples for Talos, H1, Aliengo, Go2, quadruped trot/barrel roll, and humanoid jump; strong candidate for the MPC/toolkit master list.

### BotRunner64/Teleopit
- Link: https://github.com/BotRunner64/Teleopit
- Category: retargeting / teleoperation / dataset / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: Lightweight whole-body teleoperation framework for Unitree G1, supporting BVH and Pico 4 VR retargeting, sim2sim, sim2real, training data recording, and ONNX policy playback.
- Notes: Recent README updates mention Pico realtime control, LinkerHand sim2real control, manual HDF5 recording, and consolidated sim/sim2real buffering.

### NJU-RLC/quadrupedal-agility
- Link: https://github.com/NJU-RLC/quadrupedal-agility
- Category: RL / deployment / retargeting / dataset
- Robot Type: quadruped
- Simulator: Isaac Gym
- Deploy: both
- Summary: Official implementation of "Learning Diverse Natural Behaviors for Enhancing the Agility of Quadrupedal Robots," with BBC/TSC/EASI training pipelines and Go2 deployment assets.
- Notes: Repository cites arXiv:2505.09979 and includes planned/released motion-capture, training, deployment, and retargeting components.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### EPFL BioRob / Biorobotics Laboratory
- Institution: EPFL
- Homepage: https://www.epfl.ch/labs/biorob/
- Lab / Department: Biorobotics Laboratory
- Key Topics: humanoid locomotion / bio-inspired control / reinforcement learning / neuromechanics
- Notes: Openings page lists a Fall 2026 PhD and postdoc project on leveraging neuromechanics of human locomotion for humanoid robots, combining simulations, spinal/supraspinal control ideas, and RL.

### IIT Dynamic Legged Systems Lab
- Institution: Istituto Italiano di Tecnologia
- GitHub: https://github.com/iit-DLSLab
- Key Topics: legged MPC / whole-body control / humanoid and quadruped locomotion / JAX optimization
- Notes: The MPX repository is a strong lab signal for GPU-parallel MPC and whole-body MJX examples on Talos, H1, Aliengo, and Go2.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRob / Biorobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: unknown; position marked Fall 2026
- Topics: humanoid locomotion / neuromechanics / reinforcement learning / bio-inspired control
- Status: active
- Notes: One PhD and one postdoc opening for a project on investigating and leveraging human locomotion neuromechanics using humanoid robots.

### RAI Institute
- Type: Research Scientist
- Location: Cambridge, MA / Zurich, Switzerland
- Source: official careers page
- Deadline: rolling / unknown
- Topics: robotics / AI / machine learning / machine perception / robot systems
- Status: active
- Notes: Careers page lists Research Scientist and Research Scientist (Zurich Location) roles; broad robotics research signal, not explicitly legged-only.

</details>
