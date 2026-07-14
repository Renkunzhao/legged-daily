**English** | [中文](../zh/drafts/legged-daily-2026-07-14.md)
# Legged Daily - 2026-07-14

## Summary
- Today's strongest paper signals are directly legged: flowable-slope bipedal terradynamics, symmetry/Koopman-assisted RL for legged locomotion, and tactile-informed quadruped loco-manipulation.
- The bipedal slope paper is especially useful as a reminder that morphology and terrain manipulation can be part of the locomotion policy/design space, not only a disturbance to reject.
- SKooP is a high-signal learning-method paper because it combines morphological symmetry and learned Koopman predictions, using the predictions as privileged critic observations for faster and more transferable legged RL.
- Repository signals are practical today: an Isaac Lab fault-tolerant quadruped locomotion environment, a Unitree G1 linear MPC/WBID locomotion stack, and a MuJoCo convex-MPC biped implementation.
- Job tracking needs one correction: EPFL BioRob's humanoid-neuromechanics opening page now shows a CLOSED label in its summary, so the existing active/watching entry should be reviewed before surfacing it again as active.

<details>
<summary><strong>New Papers</strong></summary>

### Robust bipedal locomotion on flowable slopes via foot-driven terrain manipulation
- Link: https://arxiv.org/abs/2607.11855
- Source: arXiv
- Date: 2026-07-13
- Authors: Deniz Kerimoglu, Junnosuke Kamohara, Jiyeon Maeng, Ziwon Yoon, Seth Hutchinson, Ye Zhao, Daniel I. Goldman
- Topics: bipedal locomotion / granular terrain / terradynamics / foot morphology / terrain manipulation
- Summary: Studies bipedal locomotion on granular slopes using a small robophysical biped with cleated feet, showing that intermediate cleat spacing can shape substrate stresses and improve locomotion while overly sparse or dense cleats degrade performance.
- Notes: High relevance for legged robots operating on deformable outdoor terrain; the key signal is that foot design and terrain response control can become active locomotion mechanisms rather than only robustness problems.

### SKooP: Symmetric Koopman Predictions for Faster and More Generalizable Legged Robot Locomotion with Reinforcement Learning
- Link: https://arxiv.org/abs/2607.11624
- Source: arXiv
- Date: 2026-07-13
- Authors: Evelyn D'Elia, Weishu Zhan, Giulio Turrisi, Giulio Romualdi, Giuseppe L'Erario, Raffaello Camoriano, Wei Pan, Daniele Pucci
- Topics: legged locomotion / reinforcement learning / symmetry / Koopman models / sample efficiency / sim-to-real transfer
- Summary: Introduces SKooP, which learns a Koopman dynamics model alongside the locomotion policy, uses Koopman predictions as privileged critic observations, and adds group symmetries to actor, critic, encoder, and decoder networks for more equivariant legged RL.
- Notes: Strong candidate for the long-term paper list if follow-up artifacts or benchmark details are useful; also connects to iit-DLSLab-style work on sample-efficient and transferable locomotion learning.

### TAC-LOCO: Unified Whole-Body Control for Quadrupedal TACtile-Informed LOCO-Manipulation
- Link: https://arxiv.org/abs/2607.10132
- Source: arXiv
- Date: 2026-07-11
- Authors: Muqun Hu, Yuhao Zhou, Kabir Ray Malik, Chi Lin, Won Suk Lee, Yu She, Yan Gu
- Topics: quadruped / loco-manipulation / tactile sensing / whole-body control / reinforcement learning / sim-to-real
- Summary: Proposes TAC-LOCO, a tactile-augmented unified RL controller that fuses tactile-array latent features with proprioception to control a Unitree Go2, arm, and gripper during dynamic loco-manipulation under changing external interactions.
- Notes: Reports zero-shot hardware deployment on Unitree Go2 with WidowX 250 and tactile gripper, including reduced grasp force and improved object stability under load changes and release events.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### fault-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- Category: RL / locomotion / simulator / deployment
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Isaac Lab DirectEnv for quadrupedal locomotion under motor failures, supporting Aliengo and Go2 flat/rough blind and rough-vision environments, sim-to-sim in MuJoCo, and ROS2 sim-to-real deployment paths.
- Notes: README links concurrent state estimation, rapid motor adaptation, and Mixture-of-Experts RL for fault-tolerant locomotion; practical follow-up source for robust quadruped locomotion under degraded actuation.

### g1_locomotion
- Link: https://github.com/ioloizou/g1_locomotion
- Category: MPC / whole-body control / simulator
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: Master's-thesis implementation of a linear Unitree G1 locomotion stack combining Single Rigid Body Dynamics with Whole-Body Inverse Dynamics in a cascaded control architecture, with a straight-line walking MuJoCo demo.
- Notes: README explicitly says it has not yet been tested on the physical robot; useful as a compact reference implementation for linear MPC/WBID on Unitree G1 rather than a deployment-ready stack.

### convex-mpc-biped
- Link: https://github.com/ispaik06/convex-mpc-biped
- Category: MPC / control / simulator
- Robot Type: humanoid / biped
- Simulator: MuJoCo
- Deploy: sim
- Summary: C++17 MuJoCo implementation of convex MPC over a single-rigid-body model for humanoid/biped locomotion, using contact-wrench optimization, Raibert-style swing-foot planning, and OSQP/Eigen-based infrastructure.
- Notes: Recent, small repository; track as an educational or prototype-grade convex-MPC implementation unless hardware validation or broader robot support appears.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Dynamic Legged Systems Lab / IIT
- Institution: Istituto Italiano di Tecnologia
- Homepage: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- GitHub: https://github.com/iit-DLSLab
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: quadruped / locomotion / fault tolerance / reinforcement learning / Isaac Lab / MuJoCo / ROS2 deployment
- Notes: The new fault-locomotion-isaaclab repository is a concrete source signal around motor-failure robustness, sim-to-sim, and sim-to-real quadruped locomotion, and is tied to the arXiv work “Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion”.

### Georgia Tech / bipedal granular locomotion collaboration signal
- Institution: Georgia Institute of Technology and collaborators
- Homepage: https://arxiv.org/abs/2607.11855
- Lab / Department: paper source / collaboration network
- Key Topics: bipedal locomotion / granular media / terradynamics / foot-terrain interaction
- Notes: The flowable-slope biped paper by Deniz Kerimoglu et al. is a useful source-network signal around Daniel I. Goldman, Ye Zhao, and collaborators for legged locomotion on deformable substrates.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: unknown / review needed
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: watching
- Notes: Official openings page still contains the humanoid-neuromechanics project description, but its summary now labels the opening as CLOSED and the postdoc application paragraph says positions are now closed. Existing master-list status should be reviewed before continuing to mark it active.

### Proposed Removal / Stale Item
- Current Status: possibly stale / no longer actionable
- Reason: EPFL BioRob humanoid-neuromechanics opening was previously tracked as active, but the official page now shows a CLOSED marker in the summary and says the positions are now closed in the postdoc section; the PhD text still contains older rolling-style instructions, so this needs manual confirmation before removal.
- Source Checked: https://www.epfl.ch/labs/biorob/openings/

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / motion planning / MPC / reinforcement learning / perception / navigation / robot design / ROS / C++
- Status: active
- Notes: Official RSL page continues to list rolling openings across PhD, postdoc, research staff/software engineering, robot design, embedded systems, and electronics, with explicit relevance to legged robots, mobile manipulators, field robotics, control, learning, planning, and deployment.

</details>
