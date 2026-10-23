**English** | [中文](../zh/drafts/legged-daily-2026-10-23.md)
# Legged Daily - 2026-10-23

## Summary
- User-requested supplementary references: LOAD combines explicit inertial estimation and implicit dynamics features for narrow-beam traversal; SuperMimic uses a differentiable world model for humanoid tracking (CoRL 2026 Oral); FIBER learns unified latent-space loco-manipulation planning.
- PRISM models depth invalidation separately from measurement inaccuracy (ICML 2026); A2I-Calib++ targets noise-robust whole-body multi-IMU calibration.
- RangeNav pretrains a compact 183K-parameter LiDAR range-image encoder with reconstruction, semantic, and BEV objectives; the paper is submitted to ICRA 2027 and remains under review.
- Amazon FAR has released the RPL training stack for perceptive humanoid locomotion (expert RL, multi-depth distillation, shipped teachers, MuJoCo sim2sim); IIT DLSLab's existing quadruped framework got a 2026-10-22 commit starting a more realistic D435 noise model, still in progress.
- Refresh (10:00 CST): SuperMimic has no official code, but independent reproductions appeared within a day: zita-ch/supermimic_vibed (Isaac Lab 3 kit-less + MuJoCo-Warp) reports 0.829 LAFAN1 return with 0/40 failed clips in about 1.5 GPU-hours; UniLab- and mjlab-based reproductions report similar LAFAN1 numbers.
- ETH Zurich RobotX is recruiting for its 2027 PhD and Postdoctoral Fellowships (both due 2026-11-27), explicitly covering legged locomotion and humanoids; RSL's rolling opportunities remain listed, while the LAAS-CNRS safe-RL PhD offer has expired.

<details>
<summary><strong>New Papers</strong></summary>

### LOAD: Locomotion with Online Awareness of Dynamics for Precision Footholds
- Link: https://arxiv.org/abs/2610.17930
- Source: arXiv
- Date: 2026-10-13
- Authors: Kunzhao Ren, Zhishuo Zhu, Xiaobin Xiong
- Topics: explicit inertial estimation / implicit dynamics adaptation / narrow-beam traversal / perceptive locomotion
- Summary: Combines explicit torso inertial estimates and implicit dynamics history features with height-map-teacher to depth-student distillation for precision locomotion under unknown payloads.
- Notes: arXiv preprint; no accepted venue is stated on the public arXiv page. Hardware results include a unilateral 6 kg payload on a 10 cm beam, a unilateral 9 kg payload on a 15 cm beam, and an evenly distributed 11 kg payload on a 15 cm beam. Added by user request as a supplementary reference, rather than a new release on this date.

### SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model
- Link: https://arxiv.org/abs/2610.28480
- Source: arXiv
- Date: 2026-10-20
- Authors: Qiayuan Liao, Yiyang Shao, Junfeng Long, Kevin Zakka, Roberto Horowitz, Pieter Abbeel, Koushil Sreenath
- Topics: humanoid / differentiable world model / model-based learning / motion tracking / sim-to-real
- Summary: Fits one differentiable world model from rigid-body simulator transitions and trains a general motion-tracking policy through analytic gradients over short imagined rollouts; transfers to a physical Unitree G1.
- Notes: Accepted at CoRL 2026 (Oral), as stated on arXiv; proceedings publication was not verified. The paper reports surpassing its SONIC baseline return in 3 hours on one GPU, with 25 failures among 129,514 benchmark motions; these are paper-reported benchmark results. Project: https://supermimic.github.io/. Already included in the 2026-10-22 draft; retained here as a user-requested supplementary reference.

### FIBER: Action-Aligned Latent Planning for Versatile Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.24675
- Source: arXiv
- Date: 2026-10-17
- Authors: Yutang Lin, Guanya Shi, C. Karen Liu
- Topics: humanoid / loco-manipulation / behavioral foundation model / latent planning / offline learning
- Summary: Projects task-specific experts into the executable latent space of a frozen behavioral foundation model by matching local control responses, then trains one offline perceptive flow planner for box pickup, door opening, and grasping.
- Notes: arXiv preprint; v2 was posted on 2026-10-20, with no accepted venue stated on arXiv. Reports 42.0% mean simulation success versus 11.6% for projected latent replay and 3.5% for kinematic planning, plus real Unitree G1 demonstrations. Project: https://fiberaa.github.io/; its code link is marked coming soon. Added by user request as a supplementary reference.

### PRISM: Learning Realistic Depth via Physics-Grounded Noise Disentanglement with Semantic-Geometric Collaboration
- Link: https://proceedings.mlr.press/v306/liang26n.html
- Source: ICML 2026
- Date: 2026-10-21
- Authors: Xiujian Liang, Jiacheng Liu, Mingyang Sun, Qichen He, Anda Cheng, Cewu Lu, Jianhua Sun
- Topics: depth sensing / sensor noise / sim-to-real / perception / robot learning
- Summary: Separates realistic depth corruption into sensing invalidation and measurement inaccuracy, then combines physics-grounded noise generation with semantic-geometric priors so simulated depth better matches real sensors.
- Notes: Formally published at ICML in July 2026 (PMLR 306, 2026); the 2026-10-21 date above refers to the subsequent arXiv posting (arXiv:2610.29432), not the conference publication date. The paper reports 92.1% average success across downstream real-robot experiments. Particularly relevant to depth-camera invalid regions and boundary corruption because it models missing measurements separately from inaccurate valid measurements.

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
- Notes: Initial public commit was 2026-10-16, with README updates through 2026-10-20. Built on Holosoma; the repository includes PPO-MA / DAgger-MA infrastructure, depth rendering, terrain experts, and a shipped student for sim2sim. The README labels the related paper as CoRL 2026. This is a research release: training currently uses Isaac Gym because Isaac Sim force perturbations are not supported; integration into Holosoma mainline is a separate effort. Apache-2.0.

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / control / sim-to-real / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Existing DLSLab quadruped locomotion stack for Aliengo, Go2, B2, A2, and HyQReal2, with RL training, state estimation, domain adaptation, MuJoCo sim2sim, and ROS 2 hardware deployment.
- Notes: Update to the existing repos.md entry: commit [92687729](https://github.com/iit-DLSLab/basic-locomotion-isaaclab/commit/92687729f3b85ca4c88f87d075f64c1ff99a0777) on 2026-10-22 is titled "start to adding better d435 model noise," making the repository a useful live signal for realistic RealSense depth corruption. The README also lists DAgger depth-to-action distillation and depth-/LiDAR-to-heightmap modules as work in progress, done but not tested; do not treat the new D435 model as complete yet.

### zita-ch/supermimic_vibed
- Link: https://github.com/zita-ch/supermimic_vibed
- Category: RL / model-based learning / motion tracking / world model
- Robot Type: humanoid
- Simulator: Isaac Lab / MuJoCo-Warp
- Deploy: sim
- Summary: Unofficial from-paper reproduction of SuperMimic on Isaac Lab 3 kit-less with the Newton MuJoCo-Warp solver: a learned differentiable world model plus short-horizon BPTT policy training for Unitree G1 tracking of 40 LAFAN1 clips.
- Notes: Created 2026-10-21 by Chong Zhang (ETH Zurich, per README); MIT. README reports evaluation return 0.829 with 0/40 failed clips after 1.47 h on one RTX PRO 6000, against the paper's 0.82 in 1.2 h on an H100. The author states it was "speed-vibecoded in 1 hour" with an AI assistant and is unreviewed, and that no official SuperMimic code is released. Related independent reproductions found via GitHub API: [Motphys/Uni-SuperMimic](https://github.com/Motphys/Uni-SuperMimic) (UniLab 1.5.0 with mjwarp / MuJoCo / Motrix backends, README reports 0.827 and 0/40 failures at 12k iterations; Apache-2.0) and [CuboiLeo/SuperMimic-Reproduced](https://github.com/CuboiLeo/SuperMimic-Reproduced) (mjlab, includes a BONES-SEED 129.9k-clip pipeline and multi-GPU training; README notes its best LAFAN1 numbers use extra anchor-relative observations not in the paper; MIT). All README numbers are self-reported and not independently verified.

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

### ETH Zurich RobotX — PhD Fellowship 2027
- Type: PhD
- Location: Zurich, Switzerland
- Source: official ETH Zurich careers page — https://jobs.ethz.ch/job/view/JOPG_ethz_zBtPwWHnM0fumyTFso
- Deadline: 2026-11-27
- Topics: legged locomotion / humanoid / whole-body control / RL / perception / robot learning / manipulation
- Status: active
- Notes: Funded 2027-entry doctoral fellowship across ETH RobotX labs: applicants may nominate up to three professors, with research areas explicitly including robotic locomotion and manipulation, humanoid whole-body control, and safe robotics. Applicants need a relevant Master's degree completed by August 2027; apply through the official online portal, not by email. This is distinct from the RSL's ongoing general hiring.

### ETH Zurich RobotX — Postdoctoral Fellowship
- Type: Postdoc
- Location: Zurich, Switzerland
- Source: official ETH Zurich careers page — https://jobs.ethz.ch/job/view/JOPG_ethz_58u057ys6BxuEciK5P
- Deadline: 2026-11-27
- Topics: legged locomotion / humanoid / whole-body control / RL / perception / manipulation / motion planning
- Status: active
- Notes: Separate from the RobotX PhD Fellowship: applicants choose up to three professors for a 2027-start research position, requiring a relevant doctoral degree completed by August 2027. The official posting describes a one-year postdoc contract, typically extended; applications go through the online portal rather than email.

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official website — https://rsl.ethz.ch/the-lab/open-positions.html
- Deadline: rolling / unknown
- Topics: legged robots / locomotion / MPC / reinforcement learning / perception / navigation / robotics systems
- Status: active
- Notes: Revalidated today: the official RSL openings page still lists these role categories. This confirms the existing jobs.md entry remains active; it is not a newly discovered opening.

### Proposed Removal / Stale Item
- Current Status: expired / no longer actionable
- Reason: The LAAS-CNRS Gepetto Team safe-reinforcement-learning PhD had a 2026-07-31 deadline, and the official CNRS page now states that the requested offer is no longer available.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
