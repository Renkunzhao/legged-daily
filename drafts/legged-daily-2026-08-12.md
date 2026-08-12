# Legged Daily Draft — 2026-08-12

Status: Draft only; awaiting confirmation before merge into master lists.

## Daily summary

- Two fresh arXiv papers passed the relevance bar: AECNav demonstrates training-free open-vocabulary object navigation at roughly 5 Hz with 95% success in 40 physical-quadruped trials; Hip Energized Monopedal Hopping provides an analytically grounded energy-regulation strategy validated on the Penn Jerboa at up to 1.77 m/s.
- Three newly created GitHub repositories are worth early inspection: a broad MuJoCo-based quadruped motion-retargeting toolkit, a VIVE-to-GR00T Sonic / Unitree G1 whole-body teleoperation pipeline, and a compact G1 complex-terrain AMP-PPO course project.
- The paper stream gives a useful lab signal around Daniel Koditschek's Penn legged-locomotion line, while the GitHub stream shows strong practitioner activity around reusable Unitree G1/Go2 data and deployment pipelines.
- No newly posted, high-confidence job opening surpassed the tracked set. Amazon Robotics Compass's official Safe Locomotion role remains active as of today's check and is still pending confirmation for master-list addition.

## Papers

### 1. AECNav: Active Evidence Consolidation for Efficient Zero-Shot Open-Vocabulary Object Navigation

- Authors: Guanlin Liu, Shaobin Ling, Renyuan Liu, Zeying Gong, Junjie Hu
- Date: 2026-08-11 (arXiv v1)
- Links: [arXiv](https://arxiv.org/abs/2608.10817)
- Summary: A training-free zero-shot object-goal navigation pipeline that shares visual encoding across reasoning stages, accumulates cluster-level log-odds evidence, treats missing expected detections as negative evidence, and actively chooses frontiers for information gain. The abstract reports 84.7%, 57.3%, and 51.3% success on HM3D-v2, HM3D-OVON, and MP3D, plus 95% success over 40 physical-quadruped trials at roughly 5 Hz.
- Why it matters: This is a concrete bridge from open-vocabulary perception to online decision-making on a legged platform, with both latency and false-positive confirmation addressed explicitly.
- Caveat: The physical-robot result is reported in the abstract; code is promised only upon acceptance and is not yet linked.

### 2. Hip Energized Monopedal Hopping

- Authors: Shane Rozen-Levy, Griffon McMahon, Daniel Koditschek
- Date: 2026-08-11 (arXiv v1)
- Links: [arXiv](https://arxiv.org/abs/2608.10387)
- Summary: The paper recruits pitch-stabilization reaction torque to compensate damping losses in a pitch-unlocked planar monoped. A stepping policy allocates energy between radial and angular dynamics, while hybrid averaging yields closed-form fixed-point and eigenvalue predictions. Experiments on the Penn Jerboa report stable hopping from 1.02 to 1.77 m/s, or 5.10 to 8.85 leg lengths/s.
- Why it matters: It is an unusually interpretable locomotion-control contribution: the controller, energetic mechanism, stability analysis, simulation, and hardware behavior are tied together rather than treated as separate layers.
- Caveat: The platform is planar and monopedal, so direct transfer to 3D quadrupeds or humanoids is not demonstrated.

## Repositories

### 1. Lain-Ego0/GQMR — General Quadruped Motion Retargeting

- Link: https://github.com/Lain-Ego0/GQMR
- Created / checked: 2026-08-11 / 2026-08-12
- Snapshot: Python, MIT, 4 stars, 1 fork at check time.
- What it is: A MuJoCo-centered quadruped retargeting toolkit with a motion schema, safe NPZ I/O, GUI, streaming capture, multi-view triangulation, motion-quality checks, and AMP/DeepMimic export. The README lists built-in models for Unitree Go2/Go1/A1/A2/B2, ANYmal C, and Deep Robotics Lite3.
- Why it matters: It aims at the messy middle between animal/human pose data and reusable legged-policy training assets, with reproducible test motions and multi-robot batch evaluation.
- Caveat: This is a very new personal repository with no CI enabled and limited independent validation; bundled assets and dataset-license boundaries should be reviewed before reuse.

### 2. zhangwencong317/HTC_VIVE_Whole_Body_Tracking

- Link: https://github.com/zhangwencong317/HTC_VIVE_Whole_Body_Tracking
- Created / checked: 2026-08-12 / 2026-08-12
- Snapshot: Python, Apache-2.0, 1 star at check time; sample data is separately CC BY-NC-SA 4.0.
- What it is: A documented low-latency pipeline from HTC VIVE trackers through calibration, Pinocchio IK and SMPL packing into NVIDIA GR00T Sonic, with MuJoCo replay and Unitree G1 deployment paths. It includes a production C++ bridge, sample recordings, networking checks, and explicit real-robot safety procedures.
- Why it matters: The repository exposes practical integration details—tracker roles, calibration, Windows/Linux networking, Jetson deployment, offline replay—that are often missing from whole-body teleoperation releases.
- Caveat: It depends on a compatible GR00T WholeBodyControl setup and specific hardware/software versions; real-G1 behavior is claimed by the README but was not independently reproduced in this run.

### 3. ytq0198/Unitree-G1

- Link: https://github.com/ytq0198/Unitree-G1
- Created / checked: 2026-08-12 / 2026-08-12
- Snapshot: Python, 2 stars, no repository license detected at check time.
- What it is: A compact course project for direct 29-DoF Unitree G1 control on procedurally generated complex terrain using AMP-PPO, waypoint observations, height-scan or depth policies, smoothness/style constraints, and repeated-random-start evaluation in mjlab.
- Why it matters: The repository is small but unusually explicit about experiment commands and measured simulator scaling, making it potentially useful as a readable G1 terrain-navigation baseline.
- Caveat: No license, checkpoints, videos, TensorBoard logs, or final quantitative results are included; treat it as an early educational implementation rather than a validated research release.

## Lab / professor signals

### Penn Engineering / Kod*lab — Daniel Koditschek and Penn Jerboa

- Signal: The new Penn Jerboa paper continues a hardware-backed, analytically grounded legged-locomotion line centered on hybrid dynamics and energetic regulation.
- Why watch: For readers interested in interpretable alternatives or complements to end-to-end RL, this group remains a strong source on templates, anchors, gait stability, and controller-mechanism co-design.
- Source: https://arxiv.org/abs/2608.10387
- Caveat: This is a publication signal, not a newly announced opening or lab recruitment notice.

### Unitree-centered open-source integration activity

- Signal: Two same-day repositories expose concrete G1 workflows—VIVE whole-body teleoperation via GR00T Sonic and AMP-PPO terrain navigation—while GQMR targets reusable motion assets across several quadruped families.
- Why watch: The ecosystem is shifting from isolated policy demos toward reusable data conversion, replay, calibration, evaluation, and deployment tooling.
- Caveat: These are early community releases, not confirmed institutional lab announcements.

## Hiring / opportunity signals

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion

- Location: Pasadena, California, USA
- Official link: https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Status: Official page active when checked on 2026-08-12; previously proposed, not newly discovered today.
- Relevance: Physical quadruped/humanoid RL deployment, sim-to-real, formal safety constraints, whole-body control, terrain-aware locomotion, and failure-mode analysis.
- Caveat: Senior profile requiring a PhD or substantial applied-research experience, including multiple years of RL on physical robotic systems.

No additional newly posted opportunity met the official-source and relevance threshold today.

## Proposed master-list changes — confirmation required

- Add papers 1–2 to `papers.md` and `zh/papers.md`?
- Add repositories 1–3 to `repos.md` and `zh/repos.md`?
- Add or strengthen the Penn Engineering / Daniel Koditschek source in `labs.md` and `zh/labs.md`?
- Add the already tracked Amazon Robotics Compass Safe Locomotion role to `jobs.md` and `zh/jobs.md`?

Please confirm all or specify item numbers. No formal master-list merge has been made.
