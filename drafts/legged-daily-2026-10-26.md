**English** | [中文](../zh/drafts/legged-daily-2026-10-26.md)
# Legged Daily - 2026-10-26

## Summary
- RPL (CoRL 2026, arXiv revised 2026-10-04) combines terrain-specific expert training with multi-depth transformer distillation for bidirectional humanoid terrain locomotion; the official Amazon FAR research code was recently released and is already tracked in repos.md.
- Humanoid SRL (arXiv, 2026-10-19) augments a humanoid with an additional arm and combines trajectory optimization, goal-conditioned RL, and real-robot contact-rich loco-manipulation.
- ProTrav (arXiv, 2026-10-22) propagates spatially correlated elevation uncertainty into traversability distributions for risk-sensitive MPPI navigation; its legged-platform validation remains unverified.
- GitHub API review identified two independent SuperMimic G1/H2/A3 or G1-only reproduction workspaces and a new MuJoCo G1 whole-body MPC/TSID control implementation; none establishes real-hardware deployment.
- Newly verified Hugging Face releases include HIW-500 real Unitree G1 household logs, NVIDIA GRAIL physics-validated G1 interaction trajectories, and MOSAIC G1 retargeted motions.
- Aarhus University's A3 Lab has a Physical AI PhD opening closing 2026-11-01; the position is broader robot foundation-model research rather than legged-locomotion specific.

<details>
<summary><strong>New Papers</strong></summary>

### RPL: Learning Robust Humanoid Perceptive Locomotion on Challenging Terrains
- Link: https://arxiv.org/abs/2602.03002
- Source: CoRL 2026 (official project); arXiv preprint first submitted 2026-02-03, revised 2026-10-04
- Date: 2026-10-04
- Authors: Yuanhang Zhang, Younggyo Seo, Juyue Chen, Yifu Yuan, Koushil Sreenath, Pieter Abbeel, Carmelo Sferrazza, Karen Liu, Rocky Duan, Guanya Shi
- Topics: humanoid / perceptive locomotion / multi-depth / teacher-student distillation / transformer / sim-to-real
- Summary: Trains privileged terrain experts and distills them into a multi-camera-depth transformer using command-conditioned depth feature scaling and random side masking for robust bidirectional locomotion on stairs, slopes and stepping stones.
- Notes: Official project https://rpl-humanoid.github.io/ reports real-hardware terrain and 2 kg payload demonstrations and about 5x more efficient depth rendering. The official code https://github.com/amazon-far/RPL was previously added to repos.md; this is a retrospective paper curation tied to its recent research release, not a new 2026-10-26 publication.

### Humanoid SRL: Augmenting Humanoids with Supernumerary Limbs for Coordinated Loco-Manipulation
- Link: https://arxiv.org/abs/2610.25628
- Source: arXiv preprint; conference or journal acceptance not confirmed
- Date: 2026-10-19
- Authors: Fukang Liu, Feiyang Wu, Paul Barsa, Jaehwi Jang, Akshat Jain, Zhigen Zhao, Yipu Chen, Zhaoyuan Gu, Nikhil Vemuri, Anshul Chandaliya, Kaijie Zhu, Sean Lublinsky, Matthew Zhu, Tony G. Chen, Ye Zhao
- Topics: humanoid / morphology augmentation / contact-rich loco-manipulation / trajectory optimization / reinforcement learning
- Summary: Attaches a supernumerary arm to a humanoid and uses model-based trajectory optimization to teach goal-conditioned RL whole-body controllers for multi-contact tri-arm tasks.
- Notes: Authors report zero-shot sim-to-real control and selected vision-guided diffusion-policy demonstrations with real robot hardware; experimental videos linked from https://humanoid-srl.github.io/ . Publication venue and public training code remain unverified.

### ProTrav: Probabilistic Traversability with Elevation Uncertainty Propagation for Risk-aware Off-road Navigation
- Link: https://arxiv.org/abs/2610.30839
- Source: arXiv preprint; formal venue acceptance not confirmed
- Date: 2026-10-22
- Authors: Chuanlin Zuo, Miloš Prágr, Arun Kumar Singh, Mohammad Loni, Reza Ghabcheloo
- Topics: terrain perception / probabilistic elevation mapping / uncertainty propagation / traversability / MPPI
- Summary: Builds a probabilistic elevation field with a sparse variational Gaussian process, samples spatially correlated surface realizations, and passes traversability uncertainty to risk-aware MPPI planning.
- Notes: Authors report simulation navigation success greater than 90% versus a baseline below 40%, plus outdoor robot validation. This is adjacent terrain-perception work; the arXiv abstract does not identify a legged test platform.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### OMEGA-i/SuperMimicKit
- Link: https://github.com/OMEGA-i/SuperMimicKit
- Category: RL / motion tracking / differentiable simulation / retargeting / toolkit
- Robot Type: humanoid — Unitree G1 / Unitree H2 / Agibot A3
- Simulator: MuJoCo Warp; browser ONNX Runtime Web / WebGPU with MuJoCo WASM
- Deploy: sim / browser
- Summary: Independent, unofficial SuperMimic-style training framework with world-model and policy exports, UMR/SOMA retargeting, downloadable experimental ONNX previews, and browser playback.
- Notes: Preview release dated 2026-10-24. Its own G1 and H2 val37 test reports substantial failure counts (31/37 and 30/37); not author-official code and not a hardware controller. Motion data are not redistributed.

### tanmay2002/unitree-g1-whole-body-control
- Link: https://github.com/tanmay2002/unitree-g1-whole-body-control
- Category: MPC / whole-body control / planning / toolkit
- Robot Type: humanoid — Unitree G1 (23 controlled joints)
- Simulator: MuJoCo / Pinocchio / TSID
- Deploy: sim
- Summary: Closed-loop G1 pipeline pairing online Herdt/LIPM MPC for CoM and footstep placement with a 2 ms task-space inverse-dynamics QP; supports simultaneous arm tasks.
- Notes: University of Bonn student research project; authors report 12-step simulated walking at 0.2 m/s and no QP failures in the documented scenario. No physical-robot tests established.

### kangzejian1896/supermimic-g1-reproduction
- Link: https://github.com/kangzejian1896/supermimic-g1-reproduction
- Category: RL / differentiable world model / motion tracking / reproducibility
- Robot Type: humanoid — Unitree G1
- Simulator: MuJoCo Warp / mjlab
- Deploy: sim
- Summary: Independent SuperMimic G1 reproduction with 168k-iteration downloadable policy and world-model preview, evaluation scripts, reproducibility notes, and reference-versus-rollout videos.
- Notes: Released v0.2.0-168k around 2026-10-24; README reports training on 84,287 clips (170.11 hours) and selecting from 128 validation clips, with no separate final test. MIT code; weight terms are still pending clarification; not the official authors' implementation.

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
