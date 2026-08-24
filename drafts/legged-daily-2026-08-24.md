**English** | [中文](../zh/drafts/legged-daily-2026-08-24.md)
# Legged Daily - 2026-08-24

## Summary
- `DECOWAM` factorizes camera ego-motion, legged-base motion, and arm motion in a whole-body world-action model; it also introduces the real-robot ARMDOG dataset and reports 79 closed-loop trials per method.
- A hierarchical imitation/RL system enables a quadruped to select vision-conditioned dynamic skills for autonomous aerial traversal through a narrow gate; the paper provides a real-robot video but no verified code release.
- A Unitree G1 stand-up policy adapts a hard-ground human demonstration to MuJoCo soft contact through staged fine-tuning and explicit recovery rewards; the accompanying repository releases evaluation code, a trained policy, reference motion, and robot assets.
- Two additional substantive code releases passed the inclusion threshold: an experimental mjlab/MuJoCo-Warp port of ETH RSL's PACE system-identification workflow, and KAIST DRCD's C++/RaiSim DC-PBTO trajectory optimizer.
- No new high-confidence, actionable legged-robotics job opening was selected today; lab signals come from the KAIST DRCD code release and a new IIT Kanpur humanoid-recovery paper/repository pair.

<details>
<summary><strong>New Papers</strong></summary>

### DECOWAM: Decoupled Whole-Body World-Action Model for Legged Mobile Manipulation
- Link: https://arxiv.org/abs/2608.20114
- Source: arXiv
- Date: 2026-08-20; v2 updated 2026-08-21
- Authors: Siyuan Ma, Boshi Zhang, Yutian Zhang, Qinglian Wu, Jiaqi Zhai, Dong Wei, Qiaojun Yu
- Topics: legged mobile manipulation / world-action model / whole-body coordination / video prediction / robot dataset
- Summary: Separates camera ego-motion, base action, and arm action through dedicated conditioning pathways in a parameter-efficient world-action model, and introduces ARMDOG with synchronized video, whole-body state/action, and language.
- Notes: The paper reports 21.7% lower action MSE than FastWAM with 25.95M trainable adaptation parameters. Across 79 closed-loop trials per method, DECOWAM had the strongest observed whole-body coordination and base-displacement robustness, while completion remained comparable to the strongest baseline. No official project or code release was verified today.

### Learning Highly Dynamic Skills Transition for Quadruped Jumping Through Constrained Space
- Link: [arXiv](https://arxiv.org/abs/2608.19977) · [Video](https://youtu.be/_VexqlQd-t4)
- Source: arXiv; journal reference: Advanced Robotics Research (2025)
- Date: 2026-08-20
- Authors: Zeren Luo, Jiahui Zhang, Yimin Han, Ji Ma, Minghao Lu, Ioannis Havoutis, Peng Lu
- Topics: quadruped / dynamic locomotion / hierarchical reinforcement learning / imitation learning / vision / obstacle traversal
- Summary: Trains a library of animal-inspired low-level skills through imitation and a vision-conditioned high-level controller that selects capability-aware, collision-free transitions for autonomous aerial traversal through a narrow gate.
- Notes: The authors position this as an early autonomous agile gate-traversal demonstration for a ground-walking robot and report extension to other dynamic tasks. A real-robot video is linked from the paper source; no official code repository was verified.

### Demonstration-Guided Humanoid Stand-Up on an Emulated Deformable Surface
- Link: [arXiv](https://arxiv.org/abs/2608.20852) · [Code](https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid) · [Video](https://youtu.be/c04fnMCDdd8)
- Source: arXiv / official code repository
- Date: 2026-08-21
- Authors: Aniruddh Kushwah, Vyankatesh Ashtekar, Ashish Dutta
- Topics: humanoid / Unitree G1 / stand-up recovery / reinforcement learning / deformable terrain / reference tracking
- Summary: Uses residual joint-position control, reference tracking, and explicit recovery objectives to adapt a human stand-up demonstration from hard ground to an emulated compliant MuJoCo contact model.
- Notes: The simulation policy reaches the target upright posture with approximately 40 mm maximum contact penetration. Ablations show that reference tracking alone does not ensure recovery; the released evaluation is deterministic and simulation-only, and the surface is a soft-contact approximation rather than a full deformable-material model.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### fan-ziqi/pace-sim2real-mjlab
- Link: https://github.com/fan-ziqi/pace-sim2real-mjlab
- Category: sim-to-real / system identification / toolkit
- Robot Type: quadruped — bundled ANYmal-D workflow; extension points for other robots and actuators
- Simulator: mjlab / MuJoCo-Warp
- Deploy: simulation fitting with real excitation-data input; intended to improve later hardware policy transfer
- Summary: Ports ETH RSL's PACE actuator/joint-dynamics identification workflow from Isaac Lab to mjlab while preserving task IDs, package imports, data artifacts, CMA-ES logs, and runner interfaces.
- Notes: Created 2026-08-24 and marked experimental by the maintainer. It estimates armature, damping, Coulomb friction, encoder bias, and command delay; the repository includes static/API tests and an integration test, but meaningful large-population fitting remains GPU-oriented. Apache-2.0 is stated in the README, while the GitHub API currently reports a non-standard license classification.

### DrcdKAIST/DC-PBTO
- Link: https://github.com/DrcdKAIST/DC-PBTO
- Category: trajectory optimization / control / toolkit
- Robot Type: quadruped — bundled Hound configuration
- Simulator: RaiSim; MATLAB-generated analytical dynamics; C++ online solver
- Deploy: simulation / trajectory generation
- Summary: Releases a C++ phase-based trajectory optimizer that jointly optimizes body motion, feet, contact forces, and phase durations using a reduced-order rigid-body model, Bezier parameterizations, and SQP.
- Notes: Created 2026-08-20 by KAIST's Dynamic Robot Control and Design Lab under MIT. The repository supports multiple analytic terrains and pins qpSWIFT, but requires RaiSim and may require MATLAB with Symbolic Math Toolbox and MATLAB Coder when generated force libraries are absent.

### andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- Link: https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- Category: reinforcement learning / evaluation / dataset
- Robot Type: humanoid — Unitree G1
- Simulator: MuJoCo
- Deploy: simulation evaluation
- Summary: Provides evaluation code, a trained PPO policy, normalization statistics, a retargeted human reference motion, Unitree G1 XML/assets, and media for compliant-ground fallen-to-standing recovery.
- Notes: MIT-licensed and created 2026-07-14, with the related paper submitted on 2026-08-21. The release reproduces a deterministic evaluation rather than the full training curriculum; large artifacts may require Git LFS, and the MuJoCo passive viewer needs a graphical/OpenGL environment.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Hae-Won Park / Dynamic Robot Control and Design Lab
- Institution: Korea Advanced Institute of Science and Technology (KAIST)
- Homepage: https://drcd.kaist.ac.kr/
- GitHub: https://github.com/DrcdKAIST
- Lab / Department: Dynamic Robot Control and Design Lab
- Key Topics: quadruped / trajectory optimization / dynamics / control / locomotion
- Notes: The already tracked lab released `DC-PBTO` on 2026-08-20: a substantive MIT-licensed C++/RaiSim implementation tied to its RA-L paper on dynamically consistent trajectory optimization through contact-point decomposition.

### Ashish Dutta / IIT Kanpur Mechanical Engineering
- Institution: Indian Institute of Technology Kanpur
- arXiv: https://arxiv.org/abs/2608.20852
- GitHub: https://github.com/andireposit/Stand-Up-Motion-on-Compliant-Surface-for-Humanoid
- Lab / Department: Department of Mechanical Engineering
- Key Topics: humanoid / stand-up recovery / reinforcement learning / compliant contact / motion retargeting
- Notes: The new Unitree G1 stand-up paper and evaluation repository form a useful source signal for contact-rich humanoid recovery. The current evidence is simulation-only, but includes released policy and evaluation assets rather than paper-only claims.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence, actionable legged-robotics job opportunity was selected today. No proposed stale-item removal is included in this draft.

</details>
