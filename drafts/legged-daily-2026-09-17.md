**English** | [中文](../zh/drafts/legged-daily-2026-09-17.md)
# Legged Daily - 2026-09-17

## Summary
- PASSAGE scales scene-aligned humanoid traversal learning to 100 hours across 1,500 cluttered scenes and runs planning, mapping, and 50 Hz whole-body execution fully onboard.
- RecMorph uses topology-ordered bidirectional recurrence for one policy across varied bodies, with UNIMAL benchmarks, four quadruped platforms, and reported fall-free Go1/Go2 hardware trials.
- ETH Zürich's KINO uses whole-body and object keyframes as a compact interface between VLM planning and RL control, raising sparse-keyframe end-to-end success from 44% to 92% in the authors' evaluation.
- One high-signal official repository is included today: RecMorph provides reproducible MuJoCo/UNIMAL and Isaac Lab tracks rather than a minimal paper placeholder.
- The previously tracked LAAS-CNRS safe-RL humanoid PhD is now explicitly unavailable on the official portal and is proposed for removal from the active jobs list.

<details>
<summary><strong>New Papers</strong></summary>

### PASSAGE: Scaling Scene-Aligned Motion Learning for Perceptive Humanoid Traversal in Cluttered Environments
- Link: https://arxiv.org/abs/2609.18732
- Source: arXiv
- Date: 2026-09-16
- Authors: Yuxuan Ma, Zicheng Zeng, Chunlin Peng, Zhoujian Li, Zetong Zhao, Zhikai Zhang, Yunrui Lian, Han Xue, Sikai Liang, Weiyi Zhu, Mulin Chen, Chenghuai Lin, Jiayu Zeng, Yanwei An, Songan Zhang, Jiayuan Gu, Jilong Wang, Jingbo Wang, He Wang, Li Yi
- Topics: perceptive humanoid traversal / scene-aligned motion data / flow matching / whole-body tracking / onboard mapping
- Summary: Learns one perception-conditioned planner–tracker stack that selects and composes stepping-over, squeezing-past, and ducking-under behavior from scene-aligned demonstrations, without skill labels or obstacle-specific policies.
- Notes: The project reports 100 hours of VR/IMU-captured motion in 1,500 cluttered scenes; scaling data from 6 to 100 hours raises mean contact-free success from 48.1% to 68.9%, and the final augmented model reaches 70.3%. The deployed system uses onboard 3D LiDAR, online mapping, 6.25 Hz planning, and 50 Hz tracking on Jetson AGX Orin across 50 unseen physical layouts. These are author-reported results and were not independently reproduced.

### RecMorph: Topology-Guided Spatial Recurrence for Generalized Morphology Control
- Link: https://arxiv.org/abs/2609.18359
- Source: arXiv
- Date: 2026-09-16
- Authors: Quanrui Rao, Yong Liu, Xueming Xiao, Yingbo Luo, Kun Wu, Zhenyu Xu, Meibao Yao
- Topics: generalized morphology control / quadruped locomotion / recurrent policies / topology-aware learning / sim-to-real
- Summary: Serializes a robot's kinematic tree with a depth-first traversal and applies shared bidirectional recurrence so one policy can transform and communicate limb information with linear token complexity at fixed width and depth.
- Notes: Evaluation covers five UNIMAL tasks and a shared-policy benchmark for Go1, Go2, ANYmal-B, and ANYmal-C. The authors report 43.5% lower nominal velocity RMSE than specialist MLPs and 40 physical Go1/Go2 trials without falls; public code is available, but the results were not independently reproduced.

### A Keyframe Interface for VLM Planning and Whole-Body Control in Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2609.18869
- Source: arXiv
- Date: 2026-09-16
- Authors: Fatemeh Zargarbashi, Jin Cheng, Tianxu An, Stelian Coros
- Topics: humanoid loco-manipulation / vision-language planning / keyframes / reinforcement learning / whole-body control
- Summary: Introduces KINO, a hierarchy in which a VLM selects task-relevant whole-body and object keyframes, scene retargeting adapts them, and a keyframe-conditioned RL policy executes joint-level actions on a Unitree G1.
- Notes: A saliency-based training sampler targets semantically important manipulation stages and raises the authors' reported sparse-keyframe end-to-end success from 44% to 92%. Evaluation includes simulated and real one- and two-handed pickup, transport, and placement; no public code repository was identified during this run.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### quanruirao/RecMorph
- Link: https://github.com/quanruirao/RecMorph
- Category: reinforcement learning / generalized control / locomotion benchmark / research toolkit
- Robot Type: general morphologies / quadrupeds including Go1, Go2, ANYmal-B, and ANYmal-C
- Simulator: MuJoCo / UNIMAL; Isaac Lab 0.41.3 / Isaac Sim 4.5
- Deploy: simulation training and evaluation plus paper-reported shared-policy deployment on physical Go1 and Go2
- Summary: Official RecMorph implementation with two reproducible tracks: five morphology-general UNIMAL tasks and one shared Isaac Lab controller across four standard quadrupeds, including specialist baselines and friction-sweep evaluation.
- Notes: Created 2026-09-13 and last pushed 2026-09-15 when checked. The repository documents exact environments, launchers, seeds, budgets, smoke tests, deterministic evaluation, and zero-shot suites; generated checkpoints and logs are excluded, and GitHub metadata did not declare a repository license during this check.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Galbot-led PASSAGE collaboration
- Institution: Galbot / Shanghai Qi Zhi Institute / ShanghaiTech University / Zhongguancun Academy / Shanghai Jiao Tong University / National University of Singapore / Tsinghua University / Peking University
- Homepage: https://galaxygeneralrobotics.github.io/PASSAGE/
- arXiv: https://arxiv.org/abs/2609.18732
- Key Topics: perceptive humanoid traversal / scene-aligned motion capture / generative planning / whole-body control / onboard autonomy
- Notes: The collaboration links a large scene-aligned human-motion collection pipeline to a fully onboard humanoid traversal stack. The scale study and 50 unseen physical layouts make it a strong signal for data-centric perceptive locomotion and integrated deployment research.

### Jilin University-led RecMorph collaboration
- Institution: Jilin University / State Key Laboratory of Special Vehicle Design and Manufacturing Integration Technology / Changchun University of Science and Technology
- arXiv: https://arxiv.org/abs/2609.18359
- GitHub: https://github.com/quanruirao/RecMorph
- Key Topics: generalized morphology control / cross-platform quadruped locomotion / topology-aware policies / recurrent architectures / hardware transfer
- Notes: Quanrui Rao, Meibao Yao, and collaborators connect procedural-body benchmarks to shared control of standard quadruped platforms and release both experimental tracks. This is a useful group to watch for embodiment-general policy architectures and reproducible cross-robot control.

### ETH Zürich Computational Robotics Lab — KINO
- Institution: ETH Zürich
- Homepage: https://crl.ethz.ch/
- arXiv: https://arxiv.org/abs/2609.18869
- Lab / Department: Computational Robotics Lab
- Key Topics: humanoid loco-manipulation / VLM planning / reinforcement learning / whole-body control / keyframe interfaces
- Notes: Fatemeh Zargarbashi, Jin Cheng, Tianxu An, and Stelian Coros use sparse motion keyframes to separate semantic planning from high-frequency humanoid control. The interface is notable because it constrains the VLM to structured selections while retaining a dynamically trained low-level policy.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team, PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / no longer actionable
- Reason: The application deadline was 2026-07-31, and the official CNRS portal now explicitly states that the requested offer is no longer available.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Notes: Remove this item from the active jobs list after confirmation. No comparably strong new active legged-robotics opening was verified from an official source in this run; existing watchlist opportunities remain unchanged.

</details>
