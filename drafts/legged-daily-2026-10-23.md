**English** | [中文](../zh/drafts/legged-daily-2026-10-23.md)
# Legged Daily - 2026-10-23

## Summary
- PRISM, formally published at ICML 2026 and newly indexed on arXiv on 2026-10-21, separates depth corruption into sensing invalidation and measurement inaccuracy; its real-robot experiments report 92.1% average downstream success.
- A2I-Calib++ actively excites legged robots to calibrate whole-body multi-IMU temporal offsets, extrinsics, and biases while improving robustness to measurement noise.
- RangeNav pretrains a compact 183K-parameter LiDAR range-image encoder with reconstruction, semantic, and BEV objectives; the paper is submitted to ICRA 2027 and remains under review.
- Amazon FAR has released the RPL training stack for perceptive humanoid locomotion, including expert RL, multi-depth distillation, shipped teachers, and MuJoCo sim2sim.
- IIT DLSLab's existing quadruped locomotion framework received a 2026-10-22 commit explicitly starting a more realistic D435 noise model; this is an in-progress update rather than a finished sensor model.
- ETH Zurich RSL's official openings page still lists rolling opportunities; the LAAS-CNRS safe-RL humanoid PhD entry is now stale because the official CNRS page says the offer is no longer available.

<details>
<summary><strong>New Papers</strong></summary>

### PRISM: Learning Realistic Depth via Physics-Grounded Noise Disentanglement with Semantic-Geometric Collaboration
- Link: https://proceedings.mlr.press/v306/liang26n.html
- Source: ICML 2026
- Date: 2026-10-21
- Authors: Xiujian Liang, Jiacheng Liu, Mingyang Sun, Qichen He, Anda Cheng, Cewu Lu, Jianhua Sun
- Topics: depth sensing / sensor noise / sim-to-real / perception / robot learning
- Summary: Separates realistic depth corruption into sensing invalidation and measurement inaccuracy, then combines physics-grounded noise generation with semantic-geometric priors so simulated depth better matches real sensors.
- Notes: Formally published in Proceedings of the 43rd International Conference on Machine Learning (PMLR 306, 2026); the arXiv version appeared on 2026-10-21 as arXiv:2610.29432. The paper reports 92.1% average success across downstream real-robot experiments. Particularly relevant to depth-camera invalid regions and boundary corruption because it models missing measurements separately from inaccurate valid measurements.

### A2I-Calib++: A Kinematics-Driven Anti-noise Active Calibration Framework for Whole-Body Multi-IMU Systems on Legged Robots
- Link: https://arxiv.org/abs/2610.29438
- Source: arXiv
- Date: 2026-10-21
- Authors: Fangyu Jiang, Chaoran Xiong, Kehui Ma, Zhen Sun, Zeyu Zhang, Ling Pei
- Topics: legged robotics / multi-IMU calibration / active excitation / proprioception / state estimation
- Summary: Jointly estimates temporal offsets, IMU extrinsics, and inertial biases by combining kinematics-driven active excitation, noise-aware trajectory design, and contact-constrained virtual-IMU fusion.
- Notes: Simulation and real-quadruped experiments report improved calibration accuracy, noise robustness, and proprioceptive odometry. No formal venue is publicly confirmed for A2I-Calib++ in this run; the predecessor A2I-Calib was accepted to IROS 2025.

### RangeNav: Task-Aligned LiDAR Range-Image Pretraining for Robot Navigation
- Link: https://arxiv.org/abs/2610.29845
- Source: arXiv
- Date: 2026-10-21
- Authors: Samuel Foo Enze, Manthan Patel, Fan Yang, Linus Kramer, Pascal Roth, Marco Hutter, Cesar Cadena
- Topics: legged robots / LiDAR / navigation / representation learning / sim-to-real
- Summary: Pretrains a lightweight LiDAR range-image encoder using reconstruction, semantic segmentation, and BEV prediction, then freezes it for downstream navigation-policy learning.
- Notes: The encoder has about 183K parameters; semantic-plus-BEV supervision improves success by 32.03 percentage points on training procedural scenes and 23.73 points on out-of-distribution realistic scenes versus reconstruction-only pretraining. Zero-shot hardware demonstrations use a Unitree B2-W. The paper states it is submitted to ICRA 2027 and under review; code and models are promised but were not found released in this run.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### amazon-far/RPL
- Link: https://github.com/amazon-far/RPL
- Category: RL / control / perceptive locomotion / distillation
- Robot Type: humanoid
- Simulator: Isaac Gym / MuJoCo
- Deploy: sim
- Summary: Official research release for RPL, covering per-terrain expert RL training, multi-depth student distillation, shipped teachers, ONNX export, and MuJoCo sim2sim.
- Notes: Initial public commit was 2026-10-16, with README updates through 2026-10-20. Built on Holosoma; the repository includes PPO-MA / DAgger-MA infrastructure, depth rendering, terrain experts, and a shipped student for sim2sim. The README labels the related paper as CoRL 2026. Apache-2.0.

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / control / sim-to-real / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Existing DLSLab quadruped locomotion stack for Aliengo, Go2, B2, A2, and HyQReal2, with RL training, state estimation, domain adaptation, MuJoCo sim2sim, and ROS 2 hardware deployment.
- Notes: Update to the existing repos.md entry: commit 92687729 on 2026-10-22 is titled "start to adding better d435 model noise," making the repository a useful live signal for realistic RealSense depth corruption. The README also lists DAgger depth-to-action distillation and depth-/LiDAR-to-heightmap modules as work in progress, done but not tested; do not treat the new D435 model as complete yet.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Robotic Systems Lab — ETH Zurich
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: legged locomotion / perception / navigation / reinforcement learning / MPC / field robotics
- Notes: RangeNav (arXiv:2610.29845) is a new LiDAR-navigation signal from authors including Marco Hutter and Cesar Cadena. The lab's official openings page continues to list rolling PhD, postdoc, research-staff/software, robot-design, embedded-systems, and electronics opportunities; this is an update to an existing tracked source rather than a new lab entry.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / locomotion / MPC / reinforcement learning / perception / navigation / robotics systems
- Status: active
- Notes: Revalidated today: the official RSL openings page still lists these role categories. This confirms the existing jobs.md entry remains active; it is not a newly discovered opening.

### Proposed Removal / Stale Item
- Current Status: expired / no longer actionable
- Reason: The LAAS-CNRS Gepetto Team safe-reinforcement-learning PhD had a 2026-07-31 deadline, and the official CNRS page now states that the requested offer is no longer available.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
