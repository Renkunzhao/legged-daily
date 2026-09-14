**English** | [中文](../zh/drafts/legged-daily-2026-09-14.md)
# Legged Daily - 2026-09-14

## Summary
- DWMP separates humanoid proprioception and egocentric depth into Koopman and recurrent-state-space world models, then fuses both latent representations for Unitree G1 obstacle traversal.
- CLAW amortizes test-time world-model adaptation: a hypernetwork generates LoRA adapters from seconds of interaction data across locomotion and manipulation environment families.
- A multi-model global planner couples traversability-aware Heading-Aware A* with a Pure Pursuit controller that switches kinematic models, including simulation validation on the Artaban quadruped.
- Two newly created repositories provide complementary quadruped resources: contact/slip-risk-gated Isaac Gym training for Unitree Go2, and a ROS 2 Jazzy/Gazebo Harmonic indoor navigation stack with SLAM, Nav2, and a procedurally authored office.
- No new high-confidence, actionable job opening was selected today; existing tracked opportunities remain in `jobs.md` and should be rechecked at their official sources before application.

<details>
<summary><strong>New Papers</strong></summary>

### DWMP: Leveraging Dual World Models for Humanoid Obstacle Traversal
- Link: https://arxiv.org/abs/2609.12347
- Source: arXiv
- Date: 2026-09-11
- Authors: Rongjun Jin, Jianming Ma, Yue Gao
- Topics: humanoid locomotion / obstacle traversal / world models / depth perception / teacher-student learning
- Summary: Separates proprioceptive dynamics and egocentric depth into a Koopman-based dynamics world model and an RSSM-based visual world model, then feeds their fused latent representation to a student policy for obstacle-aware action generation.
- Notes: The authors report about a 10% simulation success-rate improvement over strong teacher-student baselines and physical deployment on a Unitree G1 across randomized ceiling, bar, and narrow-passage layouts. These are author-reported results and were not independently reproduced in this run.

### Amortized Low-Rank Adaptation for Model-Based Reinforcement Learning
- Link: https://arxiv.org/abs/2609.12278
- Source: arXiv
- Date: 2026-09-11
- Authors: Fernando Palafox, David Fridovich-Keil
- Topics: model-based reinforcement learning / world models / test-time adaptation / LoRA / locomotion
- Summary: Introduces CLAW, a context-conditioned hypernetwork that turns a small batch of test-time transitions into LoRA adapters for a frozen world model, aiming to combine fast in-context inference with expressive weight-space adaptation.
- Notes: Evaluation spans locomotion and manipulation families with changes in dynamics, embodiment, and reward. The authors report stronger online adaptation than gradient-based and in-context baselines using only seconds of test-time data; the paper is broadly relevant to legged adaptation rather than a dedicated hardware-legged study.

### Global Path Planner with Multi-Model Switching
- Link: https://arxiv.org/abs/2609.13015
- Source: arXiv / accepted IFAC paper
- Date: 2026-09-11
- Authors: Pietro Gori, Francesco Iotti, Eduard Zelenay, Rastislav Marko, Michele Pierallini, Franco Angelini, Gabriele Pannocchia, Manolo Garabini
- Topics: quadruped navigation / global path planning / traversability / kinematic-model switching / Pure Pursuit
- Summary: Builds a traversability graph, plans with a heading-aware A* objective, and tracks the route using a Pure Pursuit controller that switches among kinematic models according to terrain, robot state, and platform constraints.
- Notes: The abstract reports simulation validation on the Artaban quadruped and X3 quadrotor; the paper also discusses broader experiments, but this daily entry conservatively treats the explicit quadruped evidence as simulation-based. Results were not independently reproduced.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### lilaojiu182-star/CRG-SLR
- Link: https://github.com/lilaojiu182-star/CRG-SLR
- Category: reinforcement learning / locomotion / contact-risk modeling
- Robot Type: quadruped / Unitree Go2
- Simulator: NVIDIA Isaac Gym Preview 4
- Deploy: training code only; no evaluation project, checkpoints, or physical deployment pipeline included
- Summary: Releases a focused PPO training task that augments a proprioception-only locomotion policy with self-supervised foot-contact and slip-risk prediction, then gates each leg's action update according to predicted contact risk.
- Notes: Created 2026-09-14. The repository includes the Go2 environment and assets, policy, runner, rough-terrain curriculum, dynamics randomization, and reproducibility settings for 4,096 parallel environments. It uses CC BY-NC 4.0 because of inherited SLR material, so it is a non-commercial source-available research release rather than OSI-approved open source; no public manuscript identifier or frozen paper checkpoint was available at check time.

### btxviny/go2_nav
- Link: https://github.com/btxviny/go2_nav
- Category: navigation / simulation environment / ROS 2 integration
- Robot Type: quadruped / Unitree Go2
- Simulator: Gazebo Harmonic with a procedurally generated Blender office
- Deploy: simulation; ROS 2 Jazzy stack with SLAM, Nav2, KISS-ICP, ros2_control, and teleoperation, without physical Go2 deployment evidence
- Summary: Packages a repeatable indoor-navigation environment for Go2, combining a Blender-authored office, Gazebo simulation, lidar and camera sensing, mapping/localization, Nav2 point-to-point navigation, and documented launch workflows.
- Notes: Created 2026-09-13. The project includes a Docker build intended to verify installation and colcon compilation on clean Ubuntu 24.04; GUI/runtime behavior was not independently tested in this run. Its original `go2_office_sim` package, Blender scripts, and documentation are MIT-licensed, while vendored and submodule dependencies retain separate licenses.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Learning and Adaptive Robot Systems group signal at UT Austin
- Institution: The University of Texas at Austin
- Homepage: https://arxiv.org/abs/2609.12278
- Key Topics: model-based reinforcement learning / test-time adaptation / world models / locomotion / robot learning
- Notes: Fernando Palafox and David Fridovich-Keil released CLAW, extending the group's adaptation and decision-making signal toward near-instant world-model specialization with generated low-rank adapters. The locomotion experiments vary dynamics, embodiment, and reward, making this a useful source to watch for methods that could transfer to legged sim-to-real adaptation.

### University of Pisa–Panza Robotics–STU Bratislava planning collaboration
- Institution: University of Pisa / Panza Robotics, National Center of Robotics / Slovak University of Technology in Bratislava
- Homepage: https://arxiv.org/abs/2609.13015
- Key Topics: quadruped autonomy / traversability / global planning / adaptive kinematic models / control
- Notes: The cross-institution team released an IFAC-accepted planner that links terrain analysis, heading-aware graph search, and model-switching trajectory tracking, with Artaban quadruped simulation as one validation platform. It is a concrete collaboration signal around terrain-aware autonomy rather than a new hiring announcement.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence, actionable legged-robotics or humanoid opening was selected in this run. Search results were too noisy or duplicated already tracked organizations, so no unverified role was added. Existing watchlisted opportunities remain in `jobs.md`; applicants should confirm active status and deadlines on the official posting before applying.

</details>
