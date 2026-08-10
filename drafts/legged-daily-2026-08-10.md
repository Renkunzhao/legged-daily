**English** | [中文](../zh/drafts/legged-daily-2026-08-10.md)
# Legged Daily - 2026-08-10

## Summary
- Two new arXiv papers clear the inclusion bar: one closes a multi-camera perception-to-control loop for time-constrained quadrupedal ball interception, while the other learns fault-tolerant gait timing under actuator power loss and validates zero-shot transfer on IIT's 68 kg KYON quadruped.
- `ductnguyen-dtn/g1-humanoid-locomotion` contributes four Isaac Lab task variants for Unitree G1 walking, push recovery, and safe falling, with unusually useful failure-analysis notes, but no license or trained checkpoint.
- `ductnguyen-dtn/spotmicro-locomotion` documents an 18-checkpoint RL progression on a hand-built SpotMicro and preserves exact configuration snapshots; it does not include policy weights and the reported gait remains asymmetric.
- Berkeley Humanoids published a ROS Jazzy Conda buildfarm for missing RoboStack packages and maintenance forks, a narrow but reproducible infrastructure release for its humanoid software stack.
- No new lab/professor source surpassed the current master-list coverage. Amazon Robotics Compass's official Safe Locomotion role remains active and is still pending confirmation for master-list addition.

<details>
<summary><strong>New Papers</strong></summary>

### Spatiotemporal Agility: Time-Constrained Reinforcement Learning for Vision-Guided Dynamic Quadrupedal Interception
- Link: https://arxiv.org/abs/2608.06907
- Source: arXiv
- Date: 2026-08-10
- Authors: Yidong Zhu, Zibo Dai, Tongning Zhang, Leixin Chang, Hua Chen
- Topics: quadruped / reinforcement learning / vision-guided locomotion / dynamic interception / sim-to-real
- Summary: An integrated quadrupedal ball-interception system predicts a target's landing position and time from multiple cameras, then feeds them directly to a position- and time-conditioned locomotion policy rather than routing through velocity commands.
- Notes: Zhejiang University and LimX Dynamics report a complete low-latency hardware loop and higher catch success than velocity-tracking and instantaneous-ball-state baselines for tested landing points within 2 m and flight times of 0.8-1.2 s. The paper includes real-robot experiments, but no public code repository was verified today.

### Learning Fault-Tolerant Locomotion with Adaptive Gait Timing
- Link: https://arxiv.org/abs/2608.07328
- Source: arXiv / IROS 2026
- Date: 2026-08-10
- Authors: Giovanbattista Gravina, Luca Rossini, Carlo Rizzardo, Arturo Laurenzi, Nikos Tsagarakis
- Topics: quadruped / fault-tolerant locomotion / reinforcement learning / adaptive gait timing / sim-to-real
- Summary: An asymmetric actor-critic policy reconstructs privileged fault information from proprioceptive history and learns gait frequency as part of its action, allowing a single controller to reorganize timing after actuator power loss without predefined faulty-leg strategies.
- Notes: IIT validates the method in high-fidelity uneven-terrain simulation and through zero-shot real-world experiments on the 68 kg KYON quadruped on flat ground. The official project page provides architecture, simulation, and hardware videos; the paper states IROS 2026 acceptance, but no public training code was verified.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### ductnguyen-dtn/g1-humanoid-locomotion
- Link: https://github.com/ductnguyen-dtn/g1-humanoid-locomotion
- Category: RL / control / simulator
- Robot Type: humanoid
- Simulator: Isaac Lab / PhysX
- Deploy: sim
- Summary: Unitree G1 task collection for flat-ground velocity tracking, standing balance with push recovery, and safe-falling training across NVIDIA-curated and self-imported 29-DoF assets.
- Notes: Created on 2026-08-10. The repository documents why stronger pushes and continued episodes through descent are needed to activate fall-shaping rewards, plus fixes for near-zero imported inertias, invalid body-name randomization, and contact-sensor hierarchy issues. It contains task configurations but no trained checkpoint, explicit license, hardware deployment, or community validation; zero stars at verification time.

### ductnguyen-dtn/spotmicro-locomotion
- Link: https://github.com/ductnguyen-dtn/spotmicro-locomotion
- Category: RL / control / hardware integration
- Robot Type: quadruped
- Simulator: Isaac Lab / PhysX
- Deploy: both
- Summary: Reproducible Isaac Lab locomotion task and training record for a hand-built 12-servo SpotMicro, tracing the policy from a welded-base asset failure through standing stability to forward walking over 18 promoted checkpoints.
- Notes: Created on 2026-08-10. It includes the adapted URDF, task and reward patches, exact configuration snapshots, and 35 ordered experiment notes, while hardware firmware and ROS come from the upstream `mike4192/spotMicro` project. Policy weights are not included, the current gait still has rear-leg asymmetry, there is no explicit repository license, and zero stars were recorded at verification time.

### Berkeley-Humanoids/Berkeley-Humanoids-Buildfarm
- Link: https://github.com/Berkeley-Humanoids/Berkeley-Humanoids-Buildfarm
- Category: toolkit / infrastructure
- Robot Type: humanoid / general
- Simulator: none
- Deploy: both
- Summary: Berkeley Humanoids' Conda buildfarm packages ROS Jazzy dependencies absent from RoboStack and publishes them to the `berkeley-humanoids` prefix.dev channel for binary consumption by downstream humanoid repositories.
- Notes: Created on 2026-08-09 and updated on 2026-08-10. The pixi/rattler workflow pins sources and toolchains, supports linux-64 and linux-aarch64, and handles dependency chains such as EtherCAT and MuJoCo ROS 2 packages through a temporary local channel. This is infrastructure rather than a locomotion controller; it has no explicit license and had zero stars at verification time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new high-confidence lab or professor source was selected today. The KYON fault-tolerant locomotion paper is a useful new output from IIT's Humanoids and Human-Centered Mechatronics Research Line, but IIT legged-robotics groups and Nikos Tsagarakis are already represented in the source network, so this is treated as a research update rather than a new master-list candidate.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-10 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role owns RL locomotion controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms, combining formal safety mechanisms, sim-to-real pipelines, and model-based whole-body control. The official page remains accessible and lists a Pasadena base salary range of USD 167,100-226,100.

</details>
