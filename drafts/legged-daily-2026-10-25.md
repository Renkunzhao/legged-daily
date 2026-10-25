**English** | [中文](../zh/drafts/legged-daily-2026-10-25.md)
# Legged Daily - 2026-10-25

## Summary
- STAMP (arXiv, 2026-10-22) learns spatiotemporal alignment for stitching independently acquired humanoid motions and reports Unitree G1 / ROBOTIS K1 tracking tests plus physical demonstrations.
- STR (arXiv, 2026-10-21) gives retargeting extra optimization effort at interaction-critical frames and body parts; the authors evaluate on simulated G1 and physical R1.
- MPBRS (arXiv, 2026-10-21) reuses one potential-based reward-shaping design across nine humanoid morphologies instead of manually retuning each robot.
- GitHub API discovery found Isaac Lab locomotion policy exports for humanoid/quadruped/biped robots and two wheeled-legged RL / MuJoCo sim2sim codebases.
- The HuMeGo FlashPad dataset, listed as an unverified watch candidate yesterday, now has a directly inspectable public Hugging Face dataset card and files; ETH RSL's HOI-Retarget provides 13,904 retargeted G1/H2 interaction trajectories.
- TUM Autonomous Vehicle Systems Lab lists an active humanoid mobile-manipulation PhD position with an application deadline of 2026-11-15.

<details>
<summary><strong>New Papers</strong></summary>

### Robot Motion Transition with Human Motion Prior (STAMP)
- Link: https://arxiv.org/abs/2610.30817
- Source: arXiv preprint; no accepted conference or journal confirmed
- Date: 2026-10-22
- Authors: Taehyun Byun, Taemoon Jeong, Yoonbyung Chai, Woojin Wie, Insu Park, Kyungjae Lee, Sungjoon Choi
- Topics: humanoid / motion generation / motion tracking / transition synthesis / retargeting
- Summary: STAMP learns to select spatial positions, headings and transition durations before synthesizing human-prior motion between separately captured clips, then retargets sequences to robots for motion-tracking training.
- Notes: Evaluated on Unitree G1 and ROBOTIS K1; authors report real-robot long-horizon demonstrations. Project: https://childtoy.github.io/STAMP-project/ . Code availability not confirmed.

### Motion Retargeting with Spatiotemporal Preferences for Humanoid Loco-Manipulation (STR)
- Link: https://arxiv.org/abs/2610.30540
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-21
- Authors: Xiongbo Shi, Shihang Du, Zongyou Yu, Ao Zhou, Xudong Zhang, Ziyu Lin, Haodong Zhang, Junqiao Zhao, Guang Chen
- Topics: humanoid / motion retargeting / vision-language models / contact / whole-body RL
- Summary: Uses VLM-selected task-critical body parts and keyframes to allocate optimization computation; mechanics-aware contact anchoring improves body-object contacts, and spatiotemporal RL uses the resulting references.
- Notes: Authors test simulated Unitree G1 and real Unitree R1, reporting improved contact quality and downstream task execution; quantitative reproduction and code availability not independently checked.

### MPBRS: Multi-Potential-Based Reward Shaping for Unified Reward Configuration in Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.30334
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-21
- Authors: Van Chung Nguyen, Hung Manh La
- Topics: humanoid / reinforcement learning / reward shaping / locomotion / multi-embodiment
- Summary: Combines multiple potential-based reward terms into a reward structure with shared weights across nine humanoid robots; robot-specific joint and default-pose metadata substitute for per-robot reward redesign.
- Notes: Authors report reduced reward-weight tuning sensitivity. The abstract does not establish real-hardware validation. These papers are newly curated on Sunday 2026-10-25, not Sunday arXiv submissions.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### rjdelgadoq/h1v3-robotpolicies
- Link: https://github.com/rjdelgadoq/h1v3-robotpolicies
- Category: RL / locomotion / control / toolkit
- Robot Type: humanoid (asimov-1) / quadruped (v1x1) / biped (BDX-R)
- Simulator: NVIDIA Isaac Lab (v3.0.0-beta2.patch1)
- Deploy: sim / ROS2 teleoperation interface (hardware unverified)
- Summary: Isaac Lab PPO/AMP walking tasks, ROS2 velocity-command teleoperation bridges, training scripts and validated policy exports as PyTorch, safetensors and ONNX.
- Notes: Author reports matching ONNX / PyTorch outputs and includes sample checkpoints. Do not interpret ROS2 demos as independently confirmed physical deployment.

### Eriwdz/LocoWheeledLegged
- Link: https://github.com/Eriwdz/LocoWheeledLegged
- Category: RL / control / toolkit
- Robot Type: wheeled-legged quadruped (Unitree Go2W)
- Simulator: NVIDIA Isaac Lab
- Deploy: sim / sim-to-real interfaces; actual hardware testing unverified
- Summary: Go2W locomotion training workspace refining reward terms and PPO training stability, including action-rate clipping, height-sensor robustness and deployment configuration.
- Notes: Derivative engineering work referencing DreamWaQ/IsaacGym implementations; treat reported performance as author documentation, not an independent benchmark.

### liu-big/wheeled-dog-sim2sim
- Link: https://github.com/liu-big/wheeled-dog-sim2sim
- Category: RL / control / simulator / toolkit
- Robot Type: custom wheeled-legged quadruped (WheeledDogV2, 12 leg joints + 4 wheels)
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.1; MuJoCo
- Deploy: sim (Isaac training and MuJoCo sim2sim)
- Summary: Shares WheeledDogV2 URDF, rough-terrain/stair RL environments, training scripts, and a MuJoCo rollout with 57-dimensional observations and 16-dimensional actions.
- Notes: Includes 15 cm / 20 cm stair scenarios; physical deployment is not verified. Some training dependencies have third-party licenses.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### HOI-Retarget — Humanoid Human–Object Interaction Motion
- Link: https://huggingface.co/datasets/leggedrobotics/hoi-retarget
- Category: robot motion / optimization-generated / benchmark
- Subject: Unitree G1 (29 DoF) / Unitree H2 (31 DoF)
- Content: 13,904 motion-robot trajectories from 6,952 distinct interaction motions across five source motion-capture sets; 75 objects and 828.1 minutes per robot; frame-level foot/hand contact flags and object poses.
- Format: Hugging Face Parquet with robot joint/root trajectories, contact flags, object poses and preview videos
- Access: open dataset table and trajectories; some non-OMOMO object meshes require separate upstream authorization and are not redistributed
- License: CC BY-NC-SA 4.0 for the data (upstream derived licenses apply); code license is separate
- Summary: ETH RSL contact-centric retargeting data for humanoid manipulation and loco-manipulation with object geometry and robot-specific quality-control labels.
- Notes: 13,904 is the corpus count stated in the dataset card; 13,018 trajectories pass QC. OMOMO meshes are included but ParaHome/NeuralDome/CoRoleHOI/IMHD2 meshes must be obtained upstream.

### HuMeGo — Sim FlashPad (verified access update)
- Link: https://huggingface.co/datasets/ChenyuanC/HuMeGo-Sim-FlashPad
- Category: benchmark / robot motion
- Subject: simulated Unitree G1 with Dex3 hands
- Content: 100 expert demonstration episodes, 115,336 frames at 50 Hz; a flashing-light counting-memory manipulation task.
- Format: LeRobot v2.1 / Parquet + head-camera H.264 video, 640 x 360
- Access: open; Hugging Face dataset card, data studio and file browser independently accessible on 2026-10-25
- License: CC BY 4.0 (Hugging Face dataset card)
- Summary: Verifiable HuMeGo subset testing retention of transient visual cues before executing a goal manipulation action.
- Notes: Status update to the 2026-10-24 HuMeGo watch candidate, whose actual file availability could not then be confirmed. Only this subset has been checked independently; do not extrapolate access to every HuMeGo task.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Tongji University Physical Intelligence Lab — STR collaboration
- Institution: Tongji University / Shanghai Innovation Institute and collaborators
- Homepage: https://arxiv.org/abs/2610.30540
- Lab / Department: Physical Intelligence Lab / spatiotemporal retargeting collaboration
- Key Topics: humanoid / retargeting / VLM / contact-aware control / loco-manipulation
- Notes: STR (arXiv:2610.30540, 2026-10-21) links VLM-selected key stages, contact anchors and RL evaluation on G1 and R1; follow project/code release. The paper is the verified work source, not a verified independent lab website.

### Robotic Systems Lab — ETH Zurich (HOI-Retarget dataset)
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics
- Lab / Department: Robotic Systems Lab
- Key Topics: humanoid / contact retargeting / human-object interaction / motion data
- Notes: An update to an existing tracked lab, not a new lab. Public HOI-Retarget data adds 13,904 G1/H2 interaction trajectories with contact annotations: https://huggingface.co/datasets/leggedrobotics/hoi-retarget .

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Technical University of Munich — AVS Lab PhD in Humanoid Mobile Manipulation (newly found)
- Type: PhD / Research Associate (full-time TV-L E13, three-year contract)
- Location: Garching near Munich, Germany
- Source: official TUM AVS vacancy — https://www.mos.ed.tum.de/avs/karriere/humanoid-planning/
- Deadline: 2026-11-15
- Topics: humanoid / mobile manipulation / whole-body control / environment perception / motion planning / VLM / VLA
- Status: active
- Notes: Official ad specifies hands-on humanoid/quadruped research, a completed technical master's degree, and negotiation-level German and English. It lists a 2027-02-01 planned start. The page's weekday label for the November 15 deadline appears inconsistent with the calendar; use the numerical deadline and reconfirm directly before applying.

</details>
