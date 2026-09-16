**English** | [中文](../zh/drafts/legged-daily-2026-09-16.md)
# Legged Daily - 2026-09-16

## Summary
- Weave learns a single contact- and geometry-aware policy for Unitree G1 whole-body dexterous loco-manipulation from captured human-object interactions, and releases training code plus roughly 23 hours of physically executed robot-object rollouts.
- WholeBodyWAM extends pre-trained world-action priors to humanoid loco-manipulation through a unified semantic interface for heterogeneous whole-body controllers and coordination-aware attention.
- FZI's optimized feasible-wrench-polytope method reaches approximately 49–50 Hz stability analysis for arbitrary multi-contact configurations and is validated on the six-legged LAURON VI robot.
- Three recent repositories provide complementary assets: Weave's Isaac Lab training stack, SPOT's Unity/OpenXR teleoperation interface, and a reproducible Isaac Lab study of active and passive spinal yaw in a Go2-like quadruped.
- General Robotics lists an active full-time humanoid robotics engineer opening in Redmond focused on RL/IL, whole-body control, loco-manipulation, sim-to-real, and real-world deployment.

<details>
<summary><strong>New Papers</strong></summary>

### Weave: Learning Whole-Body Dexterous Loco-Manipulation from Human–Object Interactions
- Link: https://arxiv.org/abs/2609.16683
- Source: arXiv
- Date: 2026-09-15
- Authors: Liu Cao, Xingze Wu, Jingzhi Cui, Botian Xu, Mingzhi Pei, Ruoqu Chen, Mengdi Xu
- Topics: humanoid loco-manipulation / dexterous hands / human-object interaction / contact-aware retargeting / reinforcement learning
- Summary: Converts captured human-object interactions into executable robot-object references, then trains one contact- and geometry-aware policy to command 29 body joints and 12 actuated finger joints across nine objects and multiple interaction sequences.
- Notes: The authors report 92.5% success on trained interactions and 65.0% zero-additional-training success on unseen sequences. The project releases approximately 9,000 physically executed rollouts totaling about 23 hours, along with Isaac Lab training code; results were not independently reproduced in this run.

### WholeBodyWAM: Generalizing Pre-trained World–Action Priors to Humanoid Loco-Manipulation via WBC-Grounded Coordination
- Link: https://arxiv.org/abs/2609.16644
- Source: arXiv
- Date: 2026-09-15
- Authors: Zhuo Li, Yiming Yao, Jim Tan, Mengjie Jing, Zhipeng Dong, Fei Chen
- Topics: humanoid loco-manipulation / world-action models / whole-body control / diffusion transformer / cross-controller generalization
- Summary: Preserves a pre-trained visual-manipulation pathway while adding a Unified Whole-Body Controller interface and coordination-aware self-attention so one world-action model can predict visual dynamics, manipulation actions, and controller-grounded whole-body intents.
- Notes: Evaluation spans six simulation and eight real-world tasks with SONIC, AMO, and GEAR controller interfaces. The authors report 91.9% overall simulation success, stronger real-world out-of-distribution progress, and lower success-rate variance across controllers; no public code repository was identified during this run, and results were not independently reproduced.

### Optimized Wrench Polytope Analysis for Real-Time Stability Control of Legged Robots in Complex Multi-Contact Configurations
- Link: https://arxiv.org/abs/2609.17405
- Source: arXiv; submitted to IEEE ROBIO 2026
- Date: 2026-09-15
- Authors: Friedrich Graaf, Elias Birkefeld, Christian Eichmann, Elias Hofele, Tristan Schnell, Georg Heppner, Arne Roennau, Rüdiger Dillmann
- Topics: legged-robot stability / multi-contact control / feasible wrench polytope / torque control / six-legged robots
- Summary: Accelerates full actuatable-wrench-polytope evaluation for arbitrary 3D contact configurations, enabling the resulting pose-stability controller to run inside a regular control loop rather than as an offline analysis.
- Notes: The paper reports approximately 49–50 Hz evaluation for six-contact scenarios and simulation plus LAURON VI hardware validation, including wall-supported complex poses. The comparative claim that these scenarios are not achievable by other controllers is an author claim and was not independently verified.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### xiaohu-art/Weave
- Link: https://github.com/xiaohu-art/Weave
- Category: reinforcement learning / imitation learning / humanoid-object interaction / dataset / toolkit
- Robot Type: humanoid / Unitree G1 with Inspire dexterous hands
- Simulator: Isaac Lab / Isaac Sim
- Deploy: simulation training, evaluation, policy export, and physically executed rollout data; the public README does not provide a complete real-robot deployment procedure
- Summary: Releases the Weave training stack for multi-object whole-body dexterous loco-manipulation, with Hydra-configured RSL-RL/PPO training, evaluation and playback tools, motion data for nine objects, and TorchScript/ONNX export.
- Notes: Created 2026-09-10 and pushed on 2026-09-16 when checked. The repository requires about 30 GB for its workspace and uses Git LFS; no license was declared in GitHub metadata during this check.

### UMass-Embodied-AGI/SPOT-Unity
- Link: https://github.com/UMass-Embodied-AGI/SPOT-Unity
- Category: teleoperation / VR interface / data collection / viewer
- Robot Type: humanoid
- Simulator: Unity 6; robot training and teleoperation are handled by the related Genesis-Humanoid stack
- Deploy: VR/headset interface and hardware teleoperation support; streams OpenXR headset/controller poses over UDP and can locally record pose sequences
- Summary: Provides the Unity/OpenXR operator interface for SPOT long-horizon humanoid teleoperation, including binocular fisheye dome viewing, camera-IMU stabilization, 120 Hz pose streaming/recording, and a standalone Python receiver.
- Notes: Created and pushed on 2026-09-15 when checked; no license was declared in GitHub metadata. The receiver alone does not command a robot and must be integrated with Genesis-Humanoid for the complete robot workflow.

### sxngt/spine-quadruped-rl
- Link: https://github.com/sxngt/spine-quadruped-rl
- Category: reinforcement learning / robot morphology / locomotion benchmark / research toolkit
- Robot Type: quadruped / Go2-like rigid, active-spine, and passive-spine variants
- Simulator: Isaac Lab 2.1 / Isaac Sim 4.5
- Deploy: simulation and analysis only; no physical-robot deployment evidence is provided
- Summary: A reproducible master's-thesis codebase comparing rigid, actively actuated, and passive torsional-spring spinal yaw across walking, running, disturbance recovery, serpentine steering, and high-speed cutting with matched robot geometry and mass.
- Notes: Created and pushed on 2026-09-15 when checked; MIT licensed. It includes parametric URDF generation, RSL-RL PPO experiments, deterministic evaluation protocols, multi-seed statistical analysis, tests, findings, and documented reward-hacking failures; raw experiment data remains off-repository.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Tsinghua IIIS-led Weave collaboration
- Institution: Tsinghua University / Dalian University of Technology / The Chinese University of Hong Kong
- Homepage: https://xiaohu-art.github.io/Weave/
- arXiv: https://arxiv.org/abs/2609.16683
- GitHub: https://github.com/xiaohu-art/Weave
- Key Topics: dexterous humanoid loco-manipulation / human-object interaction / contact-aware retargeting / reinforcement learning / interaction datasets
- Notes: Liu Cao, Ruoqu Chen, Mengdi Xu and collaborators released a notably complete paper-project-code-data package around Unitree G1 plus dexterous hands. The combination of executable retargeting, multi-object policy learning, and physically executed contact-annotated rollouts makes this collaboration a useful source to monitor.

### CUHK–HKU–Peking University–Phi-Institute WholeBodyWAM collaboration
- Institution: The Chinese University of Hong Kong / The University of Hong Kong / Peking University / Phi-Institute
- Homepage: https://wholebodywam.github.io/
- arXiv: https://arxiv.org/abs/2609.16644
- Key Topics: humanoid loco-manipulation / world-action models / heterogeneous whole-body controllers / vision-language conditioning / sim-to-real
- Notes: Zhuo Li, Yiming Yao, Jim Tan, Mengjie Jing, Zhipeng Dong, and Fei Chen connect pre-trained world-action modeling with SONIC, AMO, and GEAR whole-body-controller interfaces. The project is a strong signal for controller-agnostic whole-body foundation-policy research, though code was not public in this check.

### FZI legged robotics and KIT MaiRo collaboration
- Institution: FZI Research Center for Information Technology / Karlsruhe Institute of Technology
- Homepage: https://www.fzi.de/en/research/research-divisions/intelligent-systems-and-production-engineering/
- arXiv: https://arxiv.org/abs/2609.17405
- Key Topics: multi-legged robots / stability analysis / multi-contact control / wrench polytopes / field robotics
- Notes: Friedrich Graaf, Elias Birkefeld, Christian Eichmann, Elias Hofele, Tristan Schnell, Georg Heppner, Arne Roennau, and Rüdiger Dillmann report real-time wrench-based stability control on LAURON VI. This is a useful non-humanoid signal for explicit model-based stability in difficult 3D contacts.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### General Robotics — Robotics Engineer, Humanoids Focus
- Type: Research Engineer / Robotics Engineer
- Location: Redmond, Washington, USA
- Source: official Ashby careers page — https://jobs.ashbyhq.com/generalrobotics/1acc15e9-f249-49c8-a0bb-5453da71327d
- Deadline: rolling / not stated
- Topics: humanoid loco-manipulation / reinforcement learning / imitation learning / whole-body control / simulation / sim-to-real / deployment
- Status: active
- Notes: Full-time role posted 2026-09-09. Responsibilities include training and deploying RL/IL policies for real-world loco-manipulation, building high-fidelity simulation environments, publishing/open-sourcing work, and owning the path from research to customer-site deployment. The page was listed and accepting applications when checked on 2026-09-16.

</details>
