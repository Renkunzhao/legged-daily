**English** | [中文](../zh/drafts/legged-daily-2026-10-26.md)
# Legged Daily - 2026-10-26

## Summary
- Refresh (afternoon run): ViT-H (arXiv, 2026-10-23; PKU / BIGAI) generates humanoid reference motion directly from monocular video with a diffusion model and post-trains it with tracking-outcome DPO; real-time G1 video teleoperation is reported.
- RPL (CoRL 2026, arXiv revised 2026-10-04) combines terrain-specific expert training with multi-depth transformer distillation for bidirectional humanoid terrain locomotion; the official Amazon FAR code is already tracked in repos.md.
- Refresh: CoCarry (arXiv, 2026-10-23; SII / Tongji / TUM) retargets two-person cooperative carrying onto two humanoids with shared-object contact structure; its raw two-person mocap is public on Hugging Face (license not stated).
- Refresh: TeleAI released official NEXUS perceptive whole-body teleoperation code with a G1 ONNX model; an NJU SuperMimic reproduction adds a full G1 sim-to-real stack and a real ~46 s dance. A MuJoCo G1 whole-body MPC/TSID implementation is also listed (sim only).
- Newly verified Hugging Face releases include HIW-500 real Unitree G1 household logs, NVIDIA GRAIL physics-validated G1 interaction trajectories, and MOSAIC G1 retargeted motions.
- Aarhus University's A3 Lab has a Physical AI PhD opening closing 2026-11-01; the position is broader robot foundation-model research rather than legged-locomotion specific.

<details>
<summary><strong>New Papers</strong></summary>

### ViT-H: Generative Video-To-Humanoid Control with Motion Tracking Feedback
- Link: https://arxiv.org/abs/2610.32966
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-23
- Authors: Zimo He, Tianyi Bian, Zizhong Yang, Hongjie Li, Nan Jiang, Jieming Cui, Baoxiong Jia, Yizhou Wang, Siyuan Huang, Yixin Zhu
- Topics: humanoid / video-to-motion / diffusion / motion tracking / DPO / teleoperation
- Summary: Replaces the reconstruction–retargeting–tracking pipeline with a diffusion model that generates humanoid reference motion directly from monocular video, post-trained via direct preference optimization on motion-tracking outcomes; an autoregressive variant supports real-time video teleoperation.
- Notes: Evaluated on Unitree G1; authors report sub-400 ms teleoperation latency (project page: ~250 ms average, RealSense D455 RGB) and favorable scaling with model and data size. Project: https://awfuact.github.io/vit-h/ . The linked code repository (github.com/mileret/ViT-H-release) returned 404 on 2026-10-26, so code availability is unconfirmed.

### RPL: Learning Robust Humanoid Perceptive Locomotion on Challenging Terrains
- Link: https://arxiv.org/abs/2602.03002
- Source: CoRL 2026 (official project); arXiv preprint first submitted 2026-02-03, revised 2026-10-04
- Date: 2026-10-04
- Authors: Yuanhang Zhang, Younggyo Seo, Juyue Chen, Yifu Yuan, Koushil Sreenath, Pieter Abbeel, Carmelo Sferrazza, Karen Liu, Rocky Duan, Guanya Shi
- Topics: humanoid / perceptive locomotion / multi-depth / teacher-student distillation / transformer / sim-to-real
- Summary: Trains privileged terrain experts and distills them into a multi-camera-depth transformer using command-conditioned depth feature scaling and random side masking for robust bidirectional locomotion on stairs, slopes and stepping stones.
- Notes: Official project https://rpl-humanoid.github.io/ reports real-hardware terrain and 2 kg payload demonstrations and about 5x more efficient depth rendering. The official code https://github.com/amazon-far/RPL was previously added to repos.md; this is a retrospective paper curation tied to its recent research release, not a new 2026-10-26 publication.

### CoCarry: Contact-Support-Structured Retargeting for Dual-Humanoid Cooperative Carrying
- Link: https://arxiv.org/abs/2610.32460
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-23
- Authors: Ziyu Lin, Shihang Du, Tianhang Wang, Xiaodong Liu, Runze Zhang, Zongyou Yu, Haodong Zhang, Alois Knoll, Guang Chen
- Topics: humanoid / multi-robot / motion retargeting / human-object interaction / cooperative carrying / dataset
- Summary: Introduces a two-person cooperative-carrying mocap dataset and a retargeting method that jointly refines two humanoids around one prescribed object trajectory using object-local hand anchors plus upper interaction / lower support structures.
- Notes: Authors report 0.9995 contact preservation and 67% / 71% less penetration duration than GMR / OmniRetarget on two AgiBot A3 humanoids, 0.9906 contact preservation on CORE4D with G1, and real two-A3 carrying experiments. The paper describes 220 sequences / 21 schemes; the raw two-person mocap is public at https://huggingface.co/datasets/sii-pi-lab/CoCarry (227 sequences / 23 categories, BVH ~120 Hz + 1080p video, open access, license not stated, no retargeted robot trajectories); it can be proposed as a dataset entry once licensing is clarified. Same group as STR (2026-10-25 draft).

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Gamma-Robot/NEXUS
- Link: https://github.com/Gamma-Robot/NEXUS
- Category: control / RL / teleoperation / motion data tooling
- Robot Type: humanoid (Unitree G1)
- Simulator: mjlab 1.5.2 (MuJoCo Warp)
- Deploy: sim (sim-to-sim and sim-to-real deployment code marked not yet released)
- Summary: Official code for NEXUS (arXiv:2609.39000): terrain-aware motion adaptation (contact detection, pelvis adjustment, keyframe IK), a privileged PPO teacher, and a depth-image perceptive student for terrain-adaptive whole-body teleoperation, plus a pretrained G1 ONNX policy.
- Notes: From TeleAI (China Telecom) / SJTU and collaborators; corresponding authors Weinan Zhang and Chenjia Bai. License: CC BY-NC 4.0 (LICENSE file). Includes paired flat/terrain example motions. Project: https://nexus-humanoid.github.io/ .

### NJU-R-L-Group-Embodied-Lab/SuperMimic-Repro-Sim2Real
- Link: https://github.com/NJU-R-L-Group-Embodied-Lab/SuperMimic-Repro-Sim2Real
- Category: control / world model / motion tracking / deployment
- Robot Type: humanoid (Unitree G1)
- Simulator: mjlab
- Deploy: both (ONNX + Unitree SDK real-robot deployment)
- Summary: Unofficial SuperMimic reproduction built on CuboiLeo/SuperMimic-Reproduced, adding BONES-SEED-scale training, custom dance motions, video-to-motion tools and a full G1 deployment stack; pretrained models and real-robot video are on GitHub Releases.
- Notes: README reports 0.56 strict-paper-setting score on LAFAN1 (paper 0.82), 0.93 on BONES-SEED (~130k clips, 46 failures), and a ~46 s real G1 dance with max 16.3° tilt deviation. MIT license; datasets not redistributed. Unaffiliated with the SuperMimic authors.

### tanmay2002/unitree-g1-whole-body-control
- Link: https://github.com/tanmay2002/unitree-g1-whole-body-control
- Category: MPC / whole-body control / planning / toolkit
- Robot Type: humanoid — Unitree G1 (23 controlled joints)
- Simulator: MuJoCo / Pinocchio / TSID
- Deploy: sim
- Summary: Closed-loop G1 pipeline pairing online Herdt/LIPM MPC for CoM and footstep placement with a 2 ms task-space inverse-dynamics QP; supports simultaneous arm tasks.
- Notes: University of Bonn student research project; authors report 12-step simulated walking at 0.2 m/s and no QP failures in the documented scenario. No physical-robot tests established.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### HIW-500: Humanoids In-the-Wild Dataset
- Link: https://huggingface.co/datasets/BitRobot/HIW-500
- Category: robot field datasets / robot motion / video
- Subject: Unitree G1 real humanoid in 12 Southeast Asian homes
- Content: Author-reported 500+ hours, 23K+ episodes, 10+ household tasks, about 10 TB raw data; joint states, wrist/head imagery, IMU, odometry and teleoperation actions.
- Format: raw ROS bag / MCAP; separate LeRobot export at https://huggingface.co/datasets/BitRobot/HIW-500-LeRobot
- Access: open — public files and dataset card; Hugging Face raw-data streaming preview currently fails with a schema-casting error
- License: CC BY 4.0 (dataset card)
- Summary: Large-scale real-world humanoid whole-body teleoperation trajectories across diverse household scenes, useful for long-horizon mobile manipulation and generalist motion learning.
- Notes: Newly curated from an existing 2026 data release, not asserted released today. Public file access is visible despite an unavailable raw-dataset table viewer.

### NVIDIA GRAIL Loco-Manipulation Trajectories
- Link: https://huggingface.co/datasets/nvidia/PhysicalAI-Robotics-Locomanipulation-GRAIL
- Category: robot motion / optimization-generated / video / benchmark
- Subject: Unitree G1 humanoid plus manipulated objects in simulated environments
- Content: Physics-validated human-object interaction trajectories spanning tabletop/ground manipulation, sitting, curbs, slopes and stairs; Hugging Face metadata lists roughly 2k train rows.
- Format: reconstructed SMPL-X plus object 6-DoF motion, retargeted robot/object trajectories, source videos, USD object assets
- Access: open — dataset files published; viewer fails for oversized row content
- License: CC BY-NC 4.0 for original motion data; bundled models, RoboCasa/ComAsset-derived meshes and other assets retain separate upstream terms
- Summary: End-to-end video-to-human-object-4D-to-G1 retargeted motions grounded by a sim-tracking policy, useful for humanoid interaction and whole-body reference data.
- Notes: Dataset page reports July 2026 updates; pretrained weights have license distinctions and the card contains inconsistent checkpoint-availability wording. Do not interpret all bundled assets as uniformly CC BY-NC 4.0.

### MOSAIC Human and G1 Motion Dataset
- Link: https://huggingface.co/datasets/BAAI-Humanoid/MOSAIC_Dataset
- Category: robot motion / human mocap / optimization-generated
- Subject: Unitree G1 retargeted motion and human optical/inertial/generated motion
- Content: Public repository files total approximately 45.9 GB; provides optical and inertial human MoCap plus GENMO-generated clips, and about 30 minutes each of PICO VR and Noitom adapter data.
- Format: human AMASS-style NPZ / MCAP; G1 retargeted NPZ; generated motions and text prompts
- Access: open — public dataset card and downloadable file browser
- License: CDLA-Permissive-2.0 (dataset card); source tools and motion data may have additional upstream terms
- Summary: Multi-source motion corpus and G1 retargeted clips for humanoid motion tracking, teleoperation and residual adaptation experiments.
- Notes: The Hugging Face viewer's 20 text rows are not the total motion-clip count; paper https://arxiv.org/abs/2602.08594 . Confirm upstream AMASS and other terms before redistribution.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Amazon Frontier AI & Robotics — RPL multi-institution collaboration
- Institution: Amazon FAR / Carnegie Mellon University / Stanford University / UC Berkeley
- Homepage: https://rpl-humanoid.github.io/
- GitHub: https://github.com/amazon-far/RPL
- Lab / Department: Amazon FAR (Frontier AI & Robotics) and university coauthors
- Key Topics: humanoid / perceptive locomotion / deep terrain perception / teacher-student distillation / sim-to-real
- Notes: Follow-up to an existing research network: CoRL 2026 RPL project and its official published code connect multi-view depth rendering, directional locomotion and physical humanoid terrain tests. Not a newly founded lab.

### Fukang Liu / Ye Zhao — Humanoid SRL collaboration
- Institution: Georgia Institute of Technology
- Homepage: https://fukangl.github.io/
- Lab / Department: Humanoid SRL author collaboration
- Key Topics: humanoid / physical interaction / morphology augmentation / contact optimization / whole-body RL
- Notes: Fukang Liu's publication page lists Humanoid SRL (arXiv:2610.25628, 2026-10-19) alongside Opt2VLA and Opt2Skill; the new tri-arm system connects contact planning and real-robot whole-body learning. The verified homepage is a researcher page, not a standalone lab portal.
- Students and Representative Works:
  - [Fukang Liu](https://fukangl.github.io/) — [Humanoid SRL](https://arxiv.org/abs/2610.25628)

### Chenjia Bai — TeleAI, China Telecom
- Institution: Institute of Artificial Intelligence, China Telecom (TeleAI)
- Homepage: https://baichenjia.github.io/
- GitHub: https://github.com/Gamma-Robot
- Lab / Department: Embodied AI Research Center, TeleAI
- Key Topics: humanoid / whole-body control / teleoperation / perception / RL
- Notes: Co-corresponding author (with Weinan Zhang, SJTU) of NEXUS, whose official code and G1 model were released 2026-10-23. Students and representative works omitted pending verification.

### Li Zhang — Logos Intelligence Lab, Fudan University
- Institution: Fudan University / Shanghai Innovation Institute
- Homepage: https://lzrobots.github.io/
- GitHub: https://github.com/LogosIntelligenceLab
- Lab / Department: Logos Intelligence Lab, School of Data Science
- Key Topics: humanoid / motion retargeting / physical AI
- Notes: Source network behind SMR (arXiv:2610.29169, 2026-10-21), a streaming humanoid retargeter distilled from semantic-conditioned physics experts; code not yet released (https://github.com/LogosIntelligenceLab/SMR holds only the project README).

### Siyuan Huang — Peking University / BIGAI (existing entry update)
- Institution: Peking University / BIGAI
- Homepage: https://siyuanhuang.com/
- Key Topics: humanoid / video-to-humanoid control / motion generation
- Notes: Update to an existing tracked entry: co-author of ViT-H (arXiv:2610.32966) with Yixin Zhu.

### Guang Chen group — SII PI Lab / Tongji (existing draft signal update)
- Institution: Tongji University / Shanghai Innovation Institute
- Lab / Department: Physical Intelligence Lab
- Key Topics: humanoid / retargeting / human-object interaction / multi-humanoid
- Notes: Second retargeting paper in a week (CoCarry after STR); Hugging Face organization https://huggingface.co/sii-pi-lab hosts the CoCarry data.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Aarhus University — A3 Lab PhD in Physical AI
- Type: PhD (three-year position)
- Location: Aarhus, Denmark
- Source: official Aarhus University posting — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: vision-language-action / world models / robot learning / adaptive foundation models / edge inference
- Status: active
- Notes: Supervised by Behzad Bozorgtabar and Qi Zhang; planned start 2027-01-01 or later. This is adjacent embodied/robot foundation-model research, not specifically a legged/humanoid locomotion role; the official application page asks for evidence of hands-on model development and a master's degree by enrollment. Newly discovered existing posting, not a newly opened position.

</details>
