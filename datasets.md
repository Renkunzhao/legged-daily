**English** | [中文](zh/datasets.md)
# Datasets

> Long-term curated dataset list for legged robotics: robot-ready motion data, human motion capture, videos, optimization-generated references, field logs, and physical calibration data.

---

<details>
<summary><strong>Robot-Ready Motion Data</strong></summary>

### BONES-SEED
- Link: https://huggingface.co/datasets/bones-studio/seed
- Category: human mocap / robot motion
- Subject: human / humanoid (Unitree G1)
- Content: 142,220 annotated motions from 522 performers, about 288 h at 120 fps; includes a stunts group with flips (e.g. flip_090, flip_180, flip_360, flip_from_wall)
- Format: SOMA proportional and uniform BVH; Unitree G1 MuJoCo-compatible CSV
- Access: gated (license agreement)
- License: bones-seed-license; free for academic use and for companies under USD 1M revenue
- Summary: Large human-motion library whose G1 retargets (provided by NVIDIA) are the training data of SONIC and SuperMimic.
- Notes: SuperMimic filters it to 129,514 clips (264.56 h) for flat-ground tracking.

### unilab-motions
- Link: https://huggingface.co/datasets/unilabsim/unilab-motions
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: G1 tracking clips including flip_360_001__A304 (backflip), flip_from_wall_104__A304 (wall flip) and tictacflip, in 29- and 23-DoF variants
- Format: NPZ (fps, joint_pos, joint_vel, body_pos_w, body_quat_w, body_lin_vel_w, body_ang_vel_w)
- Access: open
- License: Apache-2.0 on Hugging Face; the clips appear to be derived from BONES-SEED, whose terms likely still apply
- Summary: Ready-to-track G1 flip references used by UniLab's flip and wall-flip tracking tasks.

### any4hdmi-g1-amass-hard
- Link: https://huggingface.co/datasets/elijahgalahad/any4hdmi-g1-amass-hard
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: 23 CMU clips retargeted to G1, including side flip 90_08, front handsprings 90_14/15, "monkey backflip" 90_19, cartwheels and dive-rolls
- Format: NPZ, 50 Hz, 36-D qpos
- Access: open
- License: not stated; derived from AMASS
- Summary: The only public G1 retarget set found that keeps CMU flips; common AMASS-to-G1 sets filter them out.

### Unitree LAFAN1 Retargeting Dataset
- Link: https://huggingface.co/datasets/lvhaidong/LAFAN1_Retargeting_Dataset
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: 40 retargeted LAFAN1 clips (walking, running, jumps, fall-and-get-up); no flips
- Format: CSV, 30 fps
- Access: open
- License: BSD-3 for the retarget; the underlying LAFAN1 is CC BY-NC-ND
- Summary: The de facto clip set behind the GMR retargeting protocol and many G1 tracking baselines.

### AMASS Retargeted for G1
- Link: https://huggingface.co/datasets/ember-lab-berkeley/AMASS_Retargeted_for_G1
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: about 17.7k AMASS clips retargeted to G1; acrobatic CMU subjects are mostly filtered out
- Format: NPZ
- Access: open
- License: tagged CC-BY-4.0; AMASS terms still apply
- Summary: Large general-purpose G1 motion set for whole-body tracking pretraining.

### KungFuAthleteBot
- Link: https://github.com/NPCLEI/KungFuAthleteBot
- Category: video-derived motion / robot motion
- Subject: human / humanoid (Unitree G1)
- Content: 848 clips from national-level wushu training videos, including 12 backflips and aerial jumps
- Format: GVHMR SMPL-H and G1 qpos at 30 fps (data on https://huggingface.co/datasets/LuluCao/KungfuAthleteBot)
- Access: open; no raw video
- License: research use; MIT promised on acceptance
- Summary: Video-to-G1 pipeline (GVHMR then GMR) that repairs the root trajectory during flight with a ballistic parabola.

### Humanoid-X
- Link: https://huggingface.co/datasets/USC-PSI-Lab/Humanoid-X
- Category: video-derived motion / robot motion
- Subject: human / humanoid (Unitree H1)
- Content: about 164k internet clips lifted to SMPL and retargeted to H1; includes trampoline, backflip and somersault classes from Kinetics
- Format: SMPL and robot pose files; source videos as YouTube IDs only
- Access: open
- License: not stated
- Summary: Very large but noisy video-derived motion set; useful as a baseline and stress test for acrobatic reconstruction.

### ZEST G1 Motion Data
- Link: https://doi.org/10.5281/zenodo.21135719
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: G1 reference trajectories for cartwheel, box jump, box climb, ballet and table tennis, plus hardware tracking logs
- Format: HDF5, CSV, pkl
- Access: open
- License: CC-BY-4.0
- Summary: Data release accompanying ZEST (Science Robotics), which transfers athletic skills from mocap, video and animation to hardware zero-shot.

### OmniRetarget Dataset
- Link: https://huggingface.co/datasets/omniretarget/OmniRetarget_Dataset
- Category: robot motion
- Subject: humanoid (Unitree G1)
- Content: about 0.5 h of interaction, terrain and parkour-style retargeted motions; no flips
- Format: NPZ
- Access: open
- License: MIT
- Summary: Interaction-preserving retargets for loco-manipulation and terrain skills.

</details>

<details>
<summary><strong>Human Motion Capture</strong></summary>

### CMU Graphics Lab Motion Capture Database
- Link: http://mocap.cs.cmu.edu
- Category: human mocap
- Subject: human
- Content: subjects 85, 87, 88, 89 and 90 contain about 40 acrobatic trials: backflips, side flips, handsprings, a back flip with twist (90_12/13), cartwheels and rolls
- Format: C3D and ASF/AMC, 60 or 120 Hz
- Access: open
- License: free for all uses; no direct resale
- Summary: The most permissive source of real human flips; all flips start from the floor.
- Notes: Several of the cleanest backflips (87_03–05, 88_01/02/04, 89_03) are missing from AMASS, so use the raw files.

### AMASS
- Link: https://amass.is.tue.mpg.de
- Category: human mocap
- Subject: human
- Content: unified SMPL-H/SMPL-X refits of many mocap collections; acrobatic content limited to some CMU flips and cartwheels
- Format: SMPL-H / SMPL-X NPZ
- Access: registration
- License: non-commercial research; no redistribution
- Summary: Standard large-scale human motion source behind most humanoid retargeting datasets.

### FS-Jump3D
- Link: https://github.com/ryota-skating/FS-Jump3D
- Category: human mocap / video
- Subject: human
- Content: 253 figure-skating jumps by 4 skaters with 12 synchronized views at 60 fps
- Format: markerless C3D, JSON, video
- Access: open (Google Drive)
- License: CC BY-NC-SA 4.0
- Summary: Reference for fast rotation about the body's long axis (twists) with jump-phase labels.

### EgoHTR
- Link: https://huggingface.co/datasets/leggedrobotics/egohtr
- Category: human mocap / video
- Subject: human
- Content: 55 sequences (1.37 h) including 4 flip sequences and parkour, with scanned scenes and egocentric Aria video
- Format: IMU-suit SMPL-X ground truth, video
- Access: gated (manual approval)
- License: CC-BY-4.0
- Summary: One of the few public sets with ground-truth 3D for real flips.

</details>

<details>
<summary><strong>Video and Video-Derived Motion</strong></summary>

### Trampoline-AQA
- Link: https://github.com/mlxger/Trampoline
- Category: video
- Subject: human (trampoline)
- Content: 206 individual competition routines from 2018–2024 (Olympics, World Championships, Asian Games), about 3.06 h, 1080p 60 fps
- Format: video; scores, time of flight, horizontal displacement, number of skills
- Access: Google Drive download
- License: code CC-BY-4.0; footage is broadcast material
- Summary: Largest public real-trampoline video set; no skill boundaries or pose labels.

### AQA-7
- Link: http://rtis.oit.unlv.edu/datasets.html
- Category: video
- Subject: human (trampoline, diving, vault, big air)
- Content: 83 trampoline routines plus platform and synchronized 3 m springboard diving, vault, and big-air ski/snowboard events
- Format: video with judge scores
- Access: direct download
- License: research use
- Summary: Second public source of real trampoline footage, with a side view that tracks the athlete.

### FineDiving
- Link: https://github.com/xujinglin/FineDiving
- Category: video
- Subject: human (diving, including 3 m springboard)
- Content: 3,000 dives with 52 dive types and frame-level step boundaries (takeoff, flight, entry)
- Format: video; dive type, somersault count, twist count, position, scores
- Access: signed release agreement
- License: research use; code MIT
- Summary: Labels allow automatic checking of reconstructed rotation counts and flight windows.

### MTL-AQA
- Link: https://github.com/ParitoshParmar/MTL-AQA
- Category: video
- Subject: human (10 m platform, 3 m springboard)
- Content: 1,412 dives from 16 events
- Format: YouTube list with score, difficulty, position, somersault and twist annotations
- Access: open (YouTube-based)
- License: research use
- Summary: Diving clips with per-dive somersault and twist attributes.

### Diving48
- Link: http://www.svcl.ucsd.edu/projects/resound/dataset.html
- Category: video
- Subject: human (diving)
- Content: about 18k trimmed competition dives in 48 classes defined by takeoff, somersaults, twists and position
- Format: RGB video
- Access: direct download
- License: research use
- Summary: Large somersault/twist video set with class labels only.

### Motion-X++
- Link: https://huggingface.co/datasets/YuhongZhang/Motion-Xplusplus
- Category: video-derived motion
- Subject: human
- Content: large video-derived SMPL-X motion corpus; about 100 acrobatic clips (e.g. HAA500 trampoline and backflips, kungfu back flips)
- Format: SMPL-X, 30 fps
- Access: request form
- License: non-commercial, plus source-video licenses
- Summary: Additional video-derived flips for baselines; quality degrades on inverted poses.

</details>

<details>
<summary><strong>Optimization-Generated Acrobatics</strong></summary>

### Miller Somersault Optimal Control Solutions
- Link: https://data.mendeley.com/datasets/rz8t786st8
- Category: optimization-generated
- Subject: human (15-DoF biomechanical model)
- Content: 100 optimal-control solutions per formulation of a double straight back somersault with three twists (aerial phase only)
- Format: biorbd model and solution pickles
- Access: open
- License: CC BY 4.0; code at https://github.com/Ipuch/OnDynamicsForSomersaults (MIT)
- Summary: Physically consistent twisting-somersault flight phases at trampoline-like heights.

### energetic_somersault
- Link: https://github.com/Ipuch/energetic_somersault
- Category: optimization-generated
- Subject: human (15-DoF biomechanical model)
- Content: Miller somersault solved for jump heights of 3, 5, 10, 15, 20 and 25 m with several transcriptions (aerial phase only)
- Format: solution pickles (states, controls)
- Access: open
- License: MIT
- Summary: Height-parameterized flight-phase references; 3 m and 5 m cases match trampoline flight times.

### backflip_holonomic_tucking_constraint
- Link: https://github.com/EveCharbie/backflip_holonomic_tucking_constraint
- Category: optimization-generated
- Subject: human (planar 7–8 DoF model)
- Content: standing back tuck with propulsion, flight, tuck and landing; three contact variants with 20 multistart solutions each
- Format: pickles, biorbd models, videos
- Access: open
- License: CC-BY-4.0 via Zenodo (https://doi.org/10.5281/zenodo.14546204)
- Summary: Rare optimization-generated flip that includes ground contact phases.

### G1 Backflip Trajectory Optimization
- Link: https://github.com/ShahhhVihaan/backflip
- Category: optimization-generated
- Subject: humanoid (Unitree G1, 23 DoF)
- Content: kinodynamic trajectory-optimization backflip (push, flight, landing) tracked with whole-body control and MPC
- Format: trajectory pickle; CasADi and Pinocchio code
- Access: open
- License: not stated (work in progress)
- Summary: Model-generated G1 backflip without mocap.

</details>

<details>
<summary><strong>Robot Field Datasets</strong></summary>

### GrandTour
- Link: https://arxiv.org/abs/2602.18164
- Category: field logs
- Subject: quadruped (ANYmal-D)
- Content: large-scale multi-modal indoor and outdoor legged-robot recordings with high-precision ground truth
- Format: see starter repository https://github.com/leggedrobotics/grand_tour_dataset (Hugging Face and ROS1 examples)
- Access: open
- Summary: Real-world legged data for perception, state estimation and navigation.

</details>

<details>
<summary><strong>Physical Parameters and Calibration</strong></summary>

### FIG Apparatus Norms: Trampoline (TRA1)
- Link: https://www.gymnastics.sport/publicdir/rules/files/en_Apparatus%20Norms%20IV%20.pdf
- Category: physical parameters
- Subject: trampoline
- Content: drop test with a 60 kg, 40 cm sphere from 4.00 m onto the bed centre: required deflection 940–1010 mm and rebound 3310–3560 mm; spring step-test protocol
- Format: PDF standard
- Access: open
- Summary: Direct calibration target for simulated competition trampolines.
- Notes: A linear energy balance gives an effective centre stiffness of about 5.8–6.6 kN/m and a restitution coefficient of about 0.91–0.94 (derived, not stated in the standard).

### Competition Trampoline Stiffness (Qian et al. 2020)
- Link: https://pmc.ncbi.nlm.nih.gov/articles/PMC7386159/
- Category: physical parameters
- Subject: trampoline
- Content: 5.05 × 2.91 × 1.15 m competition trampoline; static loads of 20–260 kg give a linear centre stiffness of 5.69 kN/m; springs 0.70 / 1.10 kN/m; FE bed coupled with multibody simulation
- Format: journal article
- Access: open
- License: CC BY-NC-ND
- Summary: Measured stiffness values for a competition bed.

### Trampoline Bed Spring-Network Model (Jules_toile_A2022)
- Link: https://github.com/EveCharbie/Jules_toile_A2022
- Category: physical parameters
- Subject: trampoline
- Content: 15 × 9 mass grid with frame, in-bed and oblique springs fitted to motion-capture and force-plate static trials; bed mass 5 kg; damping not finalized
- Format: Python / CasADi code and fitted pickles
- Access: open
- License: not stated
- Summary: Closest open, experimentally fitted spatial model of a trampoline bed.

### MuJoCo Flex Trampoline Example
- Link: https://github.com/google-deepmind/mujoco/blob/main/model/flex/trampoline.xml
- Category: physical parameters
- Subject: trampoline (simulation)
- Content: 16 × 16 two-dimensional elastic flexcomp, 1.5 m square, pinned at the four corners
- Format: MJCF
- Access: open
- License: Apache-2.0
- Summary: Official starting point for an elastic-membrane trampoline in MuJoCo.

</details>
