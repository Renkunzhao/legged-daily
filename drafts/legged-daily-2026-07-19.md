**English** | [中文](../zh/drafts/legged-daily-2026-07-19.md)
# Legged Daily - 2026-07-19

## Summary
- PAKE is today's strongest paper signal: it learns a compact latent representation of redundant kinematic solutions and couples it with hierarchical RL for accurate quadruped-arm whole-body loco-manipulation.
- Stop to Decide provides an unusually deployment-oriented result on compute-limited quadruped inspection, showing that a climb-settle cadence avoids latency-induced stair-top overshoot on a Unitree Go2.
- QuadBoat broadens the morphology discussion by using an actively reconfigurable quadruped layout as an agile surface vehicle for water rescue rather than conventional terrestrial walking.
- Repository signals are selective: Asimov 1 exposes a substantial open humanoid hardware/simulation stack, while G1_RL_FootstepTracking is a new MuJoCo/PPO implementation for commanded omnidirectional footsteps.
- Menlo Research is recruiting a locomotion engineer/researcher to train and deploy bipedal policies on the open-source Asimov humanoid; no application deadline is stated.

<details>
<summary><strong>New Papers</strong></summary>

### PAKE: Learning Whole-Body Loco-Manipulation with Partial Kinematic Embeddings
- Link: https://arxiv.org/abs/2607.11041
- Source: arXiv
- Date: 2026-07-13
- Authors: Zhengmao He, Moonkyu Jung, Hyeongjun Kim, Jiseong Lee, Hui Zhang, Jemin Hwangbo, Jie Song
- Topics: quadruped / loco-manipulation / whole-body control / reinforcement learning / normalizing flows / sim-to-real
- Summary: Introduces a hierarchical framework in which a Kinematic Normalizing Flow encodes redundant torso-and-arm inverse-kinematic solutions, a high-level policy selects partial references in that latent space, and a low-level policy converts them into dynamically feasible full-body commands.
- Notes: Evaluated on a quadruped with a six-DoF arm; the paper reports 24 hardware episodes across eight tasks, including cart pulling, sweeping, charger insertion, and hanger placement, with 4.5 cm end-effector position error and 0.14 rad orientation error.

### Stop to Decide: Latency-Aware Proprioceptive Navigation Primitives for Mapping-Free Quadruped Inspection
- Link: https://arxiv.org/abs/2607.11204
- Source: arXiv
- Date: 2026-07-13
- Authors: Hanting Suo, Haonan Yan, Liang Wang, Aiguo Song
- Topics: quadruped / inspection / proprioceptive navigation / latency-aware control / stair traversal / mapping-free autonomy
- Summary: Develops a fully onboard, mapping-free and learning-free Unitree Go2 inspection stack whose climb-settle decision primitive remains reliable when shared Jetson Orin compute reduces the navigation loop to about 15 Hz.
- Notes: On the tested short-top stair platform, the settle-based protocol reduced pooled overshoot from 22/45 to 1/45 trials and the complete system finished the inspection course in 18/20 trials; results are limited to one course geometry, platform, and operator.

### Design and Control of the “QuadBoat”: A Quadruped Surface Vehicle for Drowning Rescue
- Link: https://arxiv.org/abs/2607.13633
- Source: arXiv
- Date: 2026-07-15
- Authors: Lianxin Zhang, Yihan Huang, Huihuan Qian
- Topics: quadruped morphology / unmanned surface vehicle / rescue robotics / model predictive control / visual tracking
- Summary: Presents an actively posture-adjustable quadruped-configured surface vehicle that combines inverse kinematics with cascaded MPC-PID control for agile water-surface motion, visual target tracking, and object retrieval.
- Notes: This is adjacent to conventional legged locomotion—the quadruped structure is used as a reconfigurable multi-hull watercraft—but it is a useful morphology-and-control signal for rescue robotics.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### asimov-1
- Link: https://github.com/asimovinc/asimov-1
- Category: hardware / simulator / control platform
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: Open-source files for building and simulating Asimov 1, a 1.2 m, 35 kg humanoid with 25 actuated DoFs, including mechanical CAD, electrical CAD, a MuJoCo model, wiring, schematics, PCB files, and onboard software.
- Notes: Hardware is licensed under CERN-OHL-S-2.0; the repository marks the locomotion policy and Asimov API as forthcoming, so this is a substantial open platform signal rather than a complete locomotion stack today.

### G1_RL_FootstepTracking
- Link: https://github.com/CYH-SWU/G1_RL_FootstepTracking
- Category: RL / locomotion / simulator
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: PPO-based omnidirectional footstep-tracking environment for the Unitree G1, using proprioception and commanded footstep positions/yaws to generate 12 leg-joint position increments for forward, backward, lateral, turning, curved, and standing behaviors.
- Notes: Includes curriculum terrain up to 5 cm steps, symmetry augmentation, tests, CI, and training/evaluation scripts; it is a new small simulation-only repository with no documented hardware deployment.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### PAKE collaboration network
- Institution: The Hong Kong University of Science and Technology (Guangzhou) / KAIST / ETH Zurich / HKUST
- Homepage: https://arxiv.org/abs/2607.11041
- Lab / Department: cross-institution paper collaboration
- Key Topics: quadruped / loco-manipulation / whole-body control / reinforcement learning / sim-to-real
- Notes: Zhengmao He, Moonkyu Jung, Jemin Hwangbo, Jie Song, and collaborators form a high-relevance source network around learned whole-body control and quadrupedal mobile manipulation; PAKE includes diverse real-hardware task validation.

### Menlo Research / Asimov
- Institution: Menlo Research
- Homepage: https://www.menlo.ai/
- GitHub: https://github.com/MenloResearch
- Lab / Department: Applied R&D / Asimov / Cyclotron locomotion team
- Key Topics: open-source humanoid / bipedal locomotion / reinforcement learning / simulation / sim-to-real / autonomy
- Notes: Menlo is publishing the Asimov 1 humanoid hardware and documentation while recruiting specifically for physical bipedal locomotion; the public repository currently exposes hardware and MuJoCo assets, with the locomotion policy still marked forthcoming.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Menlo Research / Cyclotron locomotion team
- Type: Robotics Engineer / Robotics Researcher, Locomotion
- Location: Singapore / hybrid; posting metadata also lists Singapore and Vietnam as eligible locations
- Source: official careers posting
- Deadline: unknown
- Topics: humanoid / bipedal locomotion / reinforcement learning / optimal control / simulation / sim-to-real / whole-body control
- Status: active
- Notes: The role develops controllers and learned policies for Asimov to walk, recover, climb stairs, and carry loads; responsibilities include training in Menlo's Uranus simulator, hardware deployment, telemetry analysis, autonomy-stack integration, and open-source Cyclotron tooling. Official posting: https://jobs.ashbyhq.com/menlo/b900cda7-1d4e-44c2-810d-3e5322ea1102

</details>
