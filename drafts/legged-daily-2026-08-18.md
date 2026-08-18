**English** | [中文](../zh/drafts/legged-daily-2026-08-18.md)
# Legged Daily - 2026-08-18

## Summary
- `HAF` adapts generalist flow-matching VLAs to humanoid whole-body loco-manipulation with staged locomotion/head, waist, and manipulation action generation plus compact spectral-latent offline-to-online RL; the project reports seven real-world tasks.
- `TACL` replaces handcrafted terrain curricula with policy-conditioned trajectory difficulty estimation and automatic task sampling directly on raw unstructured maps, reporting a 56.3% success-rate gain over direct training.
- `RB-TRG` adds oriented-body and turn-aware risk to sparse terrain-graph planning for wheeled-legged robots; paired MuJoCo tests raise end-to-end success from 51.5% to 68.5%, and an Apache-2.0 core planner is available.
- A new MJLab-based DroidUp E1 repository provides AMP and mimic-learning tasks plus MuJoCo ONNX sim-to-sim runners, but it is a simulation-stage release with no repository license declared.
- ShanghaiTech's Mobile Autonomous Robotic Systems Lab is a useful new source-network signal around wheeled-legged autonomy, mapping, planning, and full-stack field deployment; no new actionable hiring opportunity was selected.

<details>
<summary><strong>New Papers</strong></summary>

### HAF: Adapting Generalist VLAs to Humanoid Whole-Body Loco-manipulation via Hierarchical Action Flow and Spectral Latent RL
- Link: [arXiv](https://arxiv.org/abs/2608.16837) · [Project page](https://grange007.github.io/HAF/)
- Source: arXiv
- Date: 2026-08-17
- Authors: Langzhe Gu, Chengkai Hou, Meng Li, Xinhua Wang, Jiaming Liu, et al.
- Topics: humanoid / whole-body loco-manipulation / VLA / flow matching / offline-to-online RL
- Summary: Introduces a two-part humanoid adaptation framework in which HAF-VLA generates interdependent locomotion, waist, and dual-arm actions through three hierarchical denoising stages, while HAF-Steer refines a frozen VLA through SAC in a DCT-compressed flow-noise latent space.
- Notes: The official project reports seven real-world long-horizon loco-manipulation tasks and an average HAF-VLA success rate of 70.5% versus 53.3% for pi0.5 across its benchmark. No official code repository was verified today.

### Trajectory-Level Automatic Curriculum Learning for Legged Locomotion on Unstructured Terrain
- Link: https://arxiv.org/abs/2608.16164
- Source: arXiv
- Date: 2026-08-17
- Authors: Rocky Liu, Tengyu Liu, Baoxiong Jia, Fangwei Zhong, Xinyi Tong, Hongzhao Xie, Siyuan Huang
- Topics: legged locomotion / reinforcement learning / automatic curriculum / unstructured terrain / sim-to-real
- Summary: Proposes TACL, a closed-loop curriculum framework that learns policy-conditioned trajectory difficulty from rollout outcomes and uses evaluator-guided MH-MCMC to sample capability-matched waypoint tasks directly on unstructured height maps.
- Notes: The paper reports a 56.3% trajectory-success improvement over direct training, an 18.5% gain over handcrafted curriculum on the hardest tasks, and up to 39.74% improvement for varied approach directions. No official code release was verified today.

### Robot-Body-Aware Traversal Risk Graph Planning for Wheeled-Legged Robots in Complex Terrain
- Link: [arXiv](https://arxiv.org/abs/2608.16433) · [Code](https://github.com/ZhiqiaoGuo/RB-TRG)
- Source: arXiv
- Date: 2026-08-17
- Authors: Zhiqiao Guo, Bichi Zhang, Sören Schwertfeger
- Topics: wheeled-legged robots / terrain planning / traversal risk / A* / LiDAR navigation
- Summary: Extends sparse Traversal Risk Graph planning with an oriented rectangular body footprint evaluated along edges and yaw sweeps, incorporating support variation, lateral inclination, terrain interference, and unknown-map exposure into heading-conditioned A* transitions.
- Notes: Paired MuJoCo trials raise end-to-end success from 51.5% to 68.5% at a 2.3% mean path-length increase. The paper also reports Go2-W deployment in a full LiDAR stack that received Best Autonomy and Best Mobility at the IEEE ICRA 2026 Legged Robot Challenges.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### RB-TRG
- Link: https://github.com/ZhiqiaoGuo/RB-TRG
- Category: motion planning / toolkit
- Robot Type: wheeled-legged
- Simulator: none in release
- Deploy: software / hardware method validation in paper
- Summary: An Apache-2.0 Python implementation of robot-body-aware Traversal Risk Graph scoring and deterministic ordered-pair A* search over elevation grids and preconstructed terrain graphs.
- Notes: Created 2026-08-16 and linked by the paper. The release includes the core NumPy planner, a synthetic demo, tests, and the preprint, but explicitly excludes terrain-graph construction, simulation and execution pipelines, controllers, datasets, scene assets, evaluation scripts, and comparison harnesses.

### DroidUpE1_mjlab
- Link: https://github.com/Anwei-Saw/DroidUpE1_mjlab
- Category: RL / imitation learning / control / toolkit
- Robot Type: humanoid — DroidUp E1 21-DOF
- Simulator: MJLab / MuJoCo
- Deploy: sim
- Summary: A newly released DroidUp E1 locomotion workspace with velocity-commanded walk/run AMP, full-body mimic tracking, motion-data conversion and replay tools, bundled training artifacts, ONNX policies, and MuJoCo sim-to-sim runners.
- Notes: Created 2026-08-18. The README documents 4,096-environment training and keyboard-driven MuJoCo evaluation, but no physical deployment is claimed and GitHub reports no repository license; bundled data, weights, robot assets, and the local `rsl_rl` checkout therefore require separate provenance and reuse checks.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Sören Schwertfeger / Mobile Autonomous Robotic Systems Lab
- Institution: ShanghaiTech University
- Homepage: https://robotics.shanghaitech.edu.cn/
- Google Scholar: https://scholar.google.com/citations?user=Y2olJ9kAAAAJ&hl=en
- Lab / Department: Mobile Autonomous Robotic Systems Lab, School of Information Science and Technology / STAR Center
- Key Topics: mobile robotics / mapping / autonomy / terrain planning / search and rescue / wheeled-legged robots
- Notes: RB-TRG adds a strong legged-robotics signal to the lab's established mapping and autonomous-navigation work: the paper couples body-aware terrain-graph planning with MuJoCo evaluation and a full-stack Go2-W LiDAR deployment. The official lab homepage currently states that no 2026 graduate-student quota remains.
- Students and Representative Works:
  - [Zhiqiao Guo](https://github.com/ZhiqiaoGuo) — [Robot-Body-Aware Traversal Risk Graph Planning for Wheeled-Legged Robots in Complex Terrain](https://arxiv.org/abs/2608.16433)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence, directly relevant hiring signal was selected today. Official and targeted checks did not surface a newly posted legged-robotics opening with enough current, specific, and independently verifiable details to improve on the active opportunities already tracked in `jobs.md`.

ShanghaiTech MARS Lab's official homepage explicitly states that it has no remaining quota for 2026 graduate students, so it is recorded as a source-status note rather than an actionable opportunity.

No stale-item removal was identified today.

</details>
