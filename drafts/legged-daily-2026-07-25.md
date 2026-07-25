**English** | [中文](../zh/drafts/legged-daily-2026-07-25.md)
# Legged Daily - 2026-07-25

## Summary
- Two previously untracked papers were selected: a VR-plus-RL tele-loco-manipulation stack for the miniature ROBOTIS OP3, and DEED, a data-efficient post-training workflow for a Unitree G1-Edu retail task.
- Two implementation repositories met the bar: a newly published ROS 2 SLAM/localization/navigation stack for AgiBot Lingxi X2, and an MJLab AMP locomotion codebase for Unitree G1 updated today with training, evaluation, and MuJoCo sim-to-sim paths.
- The University of Louisville miniature-humanoid effort is useful for accessible full-body telepresence research; HIVE Robots and the Technical University of Denmark form a new applied humanoid VLA deployment signal.
- No new high-confidence recruiting opening was verified today. The previously tracked LAAS-CNRS/JRL humanoid PhD remains the nearest actionable deadline, 2026-07-31.

<details>
<summary><strong>New Papers</strong></summary>

### Towards Miniature Humanoid Tele-Loco-Manipulation Using Virtual Reality and Reinforcement Learning
- Link: https://arxiv.org/abs/2607.20399
- Source: arXiv
- Date: 2026-07-22
- Authors: Nicolas Kosanovic, Jordan Dowdy, Jean Chagas Vaz
- Topics: miniature humanoid / teleoperation / loco-manipulation / reinforcement learning / virtual reality / compliant control
- Summary: A full-body telepresence stack combines VR upper-body retargeting with RL walking and balance control on a ROBOTIS OP3, aiming to bring tele-loco-manipulation research to a smaller and more accessible humanoid platform.
- Notes: The robot walked at up to 0.45 m/s independently of arm motion. In the reported cube-relocation test, an expert operator moved two 40 g cubes within ten minutes while the robot traveled about 5 m. The paper describes Unity/ROS communication, inverse-kinematics arm control, RL lower-body control, and joint-side impedance; no paper-specific public implementation repository was identified during verification.

### Closing the Lab-to-Store Gap: A Data-Efficient Post-Training and Experience-Driven Learning VLA Framework for Retail Humanoids
- Link: https://arxiv.org/abs/2607.20345
- Source: arXiv
- Date: 2026-07-22
- Authors: Roger Sala Sisó, Tiago Silvério, Jakob Sand, Tran Nguyen Le
- Topics: humanoid manipulation / vision-language-action / post-training / experience-driven learning / retail robotics / Unitree G1
- Summary: DEED is a systems-level workflow for adapting GR00T N1.6 to supermarket shelf restocking on a Unitree G1-Edu through frequency alignment, curated demonstrations, task-relevant visual highlighting, reduced VLA dependence, experience-driven refinement, and latent-space distribution analysis.
- Notes: The authors argue that reliable deployment depends more on data and system integration than on changing the model architecture, and report turning a failed naive fine-tuning setup into a capable policy with a single GPU. The experiment primarily exercises the arm and torso while retaining Unitree's locomotion controller, so this is most relevant as a humanoid deployment and mobile-manipulation systems signal rather than a new learned locomotion method. No public paper-specific code repository was found during verification.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Nova-Valley/agibot-x2-navigation
- Link: https://github.com/Nova-Valley/agibot-x2-navigation
- Category: perception / SLAM / localization / navigation / toolkit
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: A ROS 2 Humble navigation workspace for the AgiBot Lingxi X2, covering lidar and IMU correction, Spark FAST-LIO mapping, PCD processing, NDT-OMP localization, OctoMap projection, Nav2 planning and obstacle avoidance, and conversion of `/cmd_vel` into X2 AIMDK locomotion commands.
- Notes: The MIT-licensed C++ repository was created on 2026-07-24 and provides a hardware-oriented, end-to-end integration guide for Ubuntu 22.04. It explicitly warns that it sends commands to a real robot and recommends staged validation with supervision and an available emergency stop.

### yhx1203/humanoid_amp_mjlab
- Link: https://github.com/yhx1203/humanoid_amp_mjlab
- Category: reinforcement learning / locomotion / imitation learning
- Robot Type: humanoid
- Simulator: MuJoCo / MJLab
- Deploy: sim
- Summary: An Apache-2.0 reinforcement-learning codebase for AMP-based Unitree G1 locomotion, with motion preview, parallel training, evaluation through a Viser viewer, included checkpoints, and a MuJoCo sim-to-sim workflow using Unitree SDK2 Python.
- Notes: The repository was updated on 2026-07-25. Its current documentation covers `Unitree-G1-AMP-Flat` training with 4,096 environments and wireless/joystick-driven sim-to-sim evaluation, but does not document a direct physical-robot deployment path.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Jean Chagas Vaz / miniature humanoid telepresence group
- Institution: University of Louisville, USA
- Homepage: https://arxiv.org/abs/2607.20399
- arXiv: https://arxiv.org/abs/2607.20399
- Lab / Department: Department of Electrical and Computer Engineering
- Key Topics: miniature humanoids / VR teleoperation / reinforcement-learning locomotion / compliant control / loco-manipulation
- Notes: This work is a useful signal for lower-cost, accessible humanoid research: the group rebuilt the OP3 control stack around compliant full-body telepresence rather than relying on an expensive full-scale humanoid. The reported system joins VR retargeting, balance-aware RL locomotion, and real-hardware cube manipulation.
- Students and Representative Works:
  - [Nicolas Kosanovic](https://arxiv.org/search/cs?searchtype=author&query=Kosanovic,+N) — [Towards Miniature Humanoid Tele-Loco-Manipulation Using Virtual Reality and Reinforcement Learning](https://arxiv.org/abs/2607.20399)

### HIVE Robots / Technical University of Denmark collaboration
- Institution: HIVE Robots and Technical University of Denmark, Denmark
- Homepage: https://arxiv.org/abs/2607.20345
- arXiv: https://arxiv.org/abs/2607.20345
- Lab / Department: HIVE Robots / DTU Department of Engineering Technology
- Key Topics: humanoid manipulation / VLA post-training / data curation / experience-driven learning / retail deployment
- Notes: DEED is a concrete applied signal around bringing foundation VLA policies onto a real Unitree G1-Edu in a store-like environment. The collaboration is worth tracking for deployment engineering, real-world data feedback, and practical evaluation of humanoid foundation-model policies.
- Students and Representative Works:
  - [Roger Sala Sisó](https://arxiv.org/search/cs?searchtype=author&query=Sala+Siso,+R) — [Closing the Lab-to-Store Gap](https://arxiv.org/abs/2607.20345)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence recruiting signal was verified today.

### LAAS-CNRS Gepetto / CNRS-AIST JRL — PhD in Humanoid Robotics
- Type: PhD
- Location: Toulouse, France, with part of the work at JRL in Tsukuba, Japan
- Source: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59 local posting time
- Topics: humanoid locomotion / reinforcement learning / online MPC / whole-body control / safe control
- Status: active; previously tracked, deadline reminder
- Notes: This remains the nearest verified deadline in the tracker. The project combines RL for discrete high-level contact and gait decisions with online MPC for continuous whole-body feasibility and safety.

</details>
