**English** | [中文](../zh/drafts/legged-daily-2026-10-31.md)
# Legged Daily - 2026-10-31

## Summary
- TACOS derives per-footstep terrain-instability supervision from legged-state-estimator contact residuals, then trains a visual terrain predictor; its authors report outdoor ANYmal-D evaluation and a 50 m forest demonstration, with MIT-licensed code now available.
- FORGE (accepted to Humanoids 2026) couples an online reduced-order humanoid reference policy with a full-order tracker; a single Unitree G1 controller handles multidirectional speeds, turns, and one-leg hops on hardware.
- SONIC-K1 ports open-weight whole-body tracking to the 22-DoF Booster K1 with a reported roughly 100 GPU-hour training budget; simulation is strong, but real-robot stepping and turns are still limited.
- Newly inspected code includes the official TACOS release, SONIC-K1 training/evaluation tools and a third-party AME/AME-2-inspired G1 attention-map locomotion reproduction.
- ETH RSL updated the existing EgoHTR dataset on 2026-10-30 with full-length Unitree G1 retargeted motions in Isaac Lab and MuJoCo formats; the dataset remains gated under CC BY 4.0.
- A newly found official Boston Dynamics Spot RL role remains a job lead; the previously discovered Aarhus Physical AI PhD has a firm 2026-11-01 23:59 CET deadline.

<details>
<summary><strong>New Papers</strong></summary>

### TACOS: Terrain-Aware COntact Supervision for Visual Footstep Planning
- Link: https://arxiv.org/abs/2610.37806
- Source: arXiv preprint; submitted to ICRA 2027 (not a confirmed acceptance)
- Date: 2026-10-27
- Authors: Jean-Michel Fortin, William Larrivée-Hardy, Gabriel Jeanson, Olivier Gamache, Daniele De Martini, François Pomerleau, Philippe Giguère
- Topics: quadruped / footstep safety / contact-aware perception / self-supervision / terrain uncertainty / state estimation
- Summary: Projects a factor-graph legged-estimator contact-residual instability score back into earlier camera frames as labels for dense visual terrain prediction, comparing hindsight-based hard and causal soft supervisory signals.
- Notes: On 1,716 annotated foothold contacts the authors report 28% better severity ranking than their strongest baseline; a 50 m forest trial on outdoor terrain addresses mud/vegetation beyond geometry. Reproducibility code: https://github.com/norlab-ulaval/TACOS; uses GrandTour ANYmal-D data and DINOv3/DPT. Publication is not yet accepted.

### FORGE: Feasible Online Reduced-Order Reference Generation and Whole-Body Execution for Agile Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.37974
- Source: Humanoids 2026 (accepted; arXiv manuscript)
- Date: 2026-10-27
- Authors: Adrian B. Ghansah, Yujin An, Jeeseop Kim, Soon-Jo Chung
- Topics: humanoid / model-based priors / reduced-order dynamics / reference generation / RL / motion tracking
- Summary: First trains a command-conditioned reduced-order whole-body reference generator with single-rigid-body dynamics and humanoid kinematics, then trains a full-order tracker from online frozen-generator rollouts, permitting multiple locomotion modes under a unified interface.
- Notes: Hardware Unitree G1 demonstrations report commanded longitudinal speeds -2.0 to 2.8 m/s, lateral up to ±1.0 m/s, yaw up to ±3.0 rad/s, one-leg hopping and transitions. These are author-reported operating ranges, not certified performance guarantees. A full implementation was not verified.

### SONIC-K1: Porting a Universal Humanoid Motion Tracker to a Small Humanoid on a Single GPU
- Link: https://arxiv.org/abs/2610.39327
- Source: arXiv preprint (no confirmed peer-reviewed venue)
- Date: 2026-10-29
- Authors: Kyrylo Kolesnichenko, Jong-Hoon Kim
- Topics: humanoid / universal motion tracking / smaller embodiments / low-compute training / sim-to-real / control latency
- Summary: Adapts NVIDIA SONIC to the 22-DoF Booster K1, publishing a one-GPU training pipeline, open weights, MuJoCo evaluation scripts, and broad human-motion tracking capability.
- Notes: Authors report around 100 GPU-hours and 97.4% held-out success under SONIC's rule in MuJoCo; across-robot comparison to the original SONIC compute is not controlled. Preliminary K1 hardware tests track upper-body and slow motions but stepping/turning remain unreliable. Code: https://github.com/Kyk0/sonic-k1 ; weights: https://huggingface.co/Kyry10/sonic-k1.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### norlab-ulaval/TACOS
- Link: https://github.com/norlab-ulaval/TACOS
- Category: perception / self-supervised terrain labeling / visual foothold prediction / toolkit
- Robot Type: quadruped (ANYmal-D, with robot-specific kinematics replaceable)
- Simulator: none for primary pipeline; field data and offline ML training
- Deploy: data / real-robot research evaluation
- Summary: Reproducible GrandTour download, factor-graph contact-label generation, DINOv3+DPT model training, fold-wise validation and single-image instability-map inference.
- Notes: README includes a small two-run example, a documented CSV/PNG input schema, and command-line tools for labeling, training and evaluation. Repository code MIT; downloaded DINOv3 weights have a separate Meta license.

### Kyk0/sonic-k1
- Link: https://github.com/Kyk0/sonic-k1
- Category: RL / motion tracking / retargeting integration / benchmark / deployment tooling
- Robot Type: humanoid (Booster K1, 22 DoF)
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / preliminary hardware experiments
- Summary: Open SONIC-based K1 tracking system with pretrained PyTorch/ONNX weights, held-out motion evaluation, ten sample motions, model conversion and laptop-friendly MuJoCo playback.
- Notes: Fork of NVIDIA GR00T-WholeBodyControl, not an official NVIDIA K1 release. Code Apache-2.0; released weights CC BY-NC 4.0; underlying BONES-SEED motions require their own license and are not redistributed. Field-ready gait tracking is not established.

### msllqsj/AME_Locomotion_Quad
- Link: https://github.com/msllqsj/AME_Locomotion_Quad
- Category: RL / perceptive locomotion / attention heightmap encoder / reproduction
- Robot Type: humanoid (Unitree G1 29 DoF; repository name mentions Quad)
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.x
- Deploy: sim
- Summary: Independent reproduction of attention-based map encoding for terrain-aware locomotion with a custom RSL-RL Actor-Critic encoder, two-stage training scripts and two pretrained .pt checkpoints.
- Notes: Adds XYZ terrain inputs, strided CNN downsampling before attention, and optional global context inspired by AME-2. The maintainer reports qualitative gains without an independently controlled benchmark; not an official AME release and no hardware deployment was confirmed.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### EgoHTR — Updated G1 Retargeted Human-Terrain Motions (existing dataset entry)
- Link: https://huggingface.co/datasets/leggedrobotics/egohtr
- Category: human mocap / robot-ready motion / scanned-terrain video / optimization-generated
- Subject: human and humanoid (29-DoF Unitree G1)
- Content: 55 terrain-aligned 4D human sequences, now all retargeted full-length to G1 at 30 fps; original multimodal dataset includes egocentric video, IMU mocap and 3D scans, with approximately 763 GB hosted overall.
- Format: NPZ / SMPL-X / video / scene meshes / Isaac Lab USD / MuJoCo XML
- Access: gated (must sign in and accept access terms)
- License: CC BY 4.0, with explicit privacy/non-de-anonymization and dataset-update obligations
- Summary: On 2026-10-30 ETH RSL added two G1 motion variants: GMR retargeting with Isaac Lab scene assets and OmniRetarget nonpenetrating motions with MuJoCo scene assets, alongside corrections for footlock leakage and sequence issues.
- Notes: This is a verified access/release update to the existing EgoHTR entry in datasets.md, not a separate newly invented dataset. CoRL 2026 paper: https://arxiv.org/abs/2607.13472 ; pipeline: https://github.com/leggedrobotics/egohtr. The public card and file manifest exist, but authenticated downloading requires consent.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Northern Robotics Laboratory / Université Laval — TACOS
- Institution: Université Laval (collaboration with University of Oxford Mobile Robotics Group)
- arXiv: https://arxiv.org/abs/2610.37806
- GitHub: https://github.com/norlab-ulaval/TACOS
- Lab / Department: Northern Robotics Laboratory
- Key Topics: quadruped / footstep instability / traversability / self-supervised visual perception / state estimation
- Notes: New open-source work turns legged-estimator contact residuals into hindsight and causal visual supervisory labels, using the GrandTour field dataset and real outdoor tests.

### Soon-Jo Chung — Caltech, FORGE collaboration
- Institution: California Institute of Technology (with University of Texas at El Paso collaborator)
- arXiv: https://arxiv.org/abs/2610.37974
- Lab / Department: Control and Dynamical Systems
- Key Topics: humanoid / reduced-order dynamics / model-based guidance / agile locomotion / whole-body RL
- Notes: FORGE is accepted to Humanoids 2026 and reports one unified Unitree G1 reference generator/tracker for agile multimodal locomotion.

### Marco Hutter / ETH Zurich Robotic Systems Lab — EgoHTR release update
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics/egohtr
- Lab / Department: Robotic Systems Lab
- Key Topics: human-terrain reconstruction / humanoid locomotion / motion retargeting / terrain perception
- Notes: A previously tracked source released all 55 full-length G1 retargeted EgoHTR sequences on 2026-10-30 in two simulator-specific representations; watch possible use in perceptive whole-body tracking.

### Jemin Hwangbo / KAIST Robotics and AI Lab — RAIBO-Wagon
- Institution: Korea Advanced Institute of Science and Technology (KAIST)
- arXiv: https://arxiv.org/abs/2610.39267
- GitHub: https://github.com/InsungYang/raibo-wagon
- Lab / Department: Robotics and Artificial Intelligence Lab
- Key Topics: quadruped / towing dynamics / learned forward dynamics / flow matching / MPPI / field navigation
- Notes: New RAIBO-Wagon preprint (2026-10-29) combines learned dynamics, flow-matching initialization and MPPI, reporting 85% success across 40 confined-space outdoor trials with up to 40 kg towed; linked GitHub repository is a project page, not a confirmed open training implementation.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Boston Dynamics — Reinforcement Learning & Controls Research Scientist, Spot Behavior
- Type: Research Scientist / Research Engineer
- Location: Waltham, Massachusetts, USA
- Source: official Boston Dynamics Workday posting — https://bostondynamics.wd1.myworkdayjobs.com/Boston_Dynamics/job/Waltham-Office-POST/Reinforcement-Learning---Controls-Research-Scientist---Spot-Behavior_R2862
- Deadline: unknown
- Topics: quadruped / Spot / reinforcement learning / locomotion / control / Isaac Sim / MuJoCo / hardware deployment
- Status: watching
- Notes: Newly discovered existing official role for training and deploying RL mobility policies on Spot. The indexed job description includes controller tuning and sim-to-real integration, but the current apply flow was not independently verified.

### Aarhus University / Adaptive & Agentic AI (A3) Lab — Physical AI PhD (deadline reminder)
- Type: PhD
- Location: Aarhus, Denmark
- Source: official university announcement — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: robotics / VLA / world models / adaptation / physical AI
- Status: active
- Notes: Follow-up from an earlier draft, not a newly posted vacancy; tomorrow's deadline was rechecked on the university site. Adjacent embodied-robotics role, not specifically a legged locomotion opening.

</details>
