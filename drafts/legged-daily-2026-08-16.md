**English** | [中文](../zh/drafts/legged-daily-2026-08-16.md)
# Legged Daily - 2026-08-16

## Summary
- No new high-signal legged-robotics paper was selected today. The latest relevant arXiv monitoring feeds still ended on August 13 at run time, consistent with the weekend submission gap.
- `RIMKit` is the strongest repository signal: a Korea University Robot Intelligence Lab toolkit that retargets SOMA human motion to eleven humanoid platforms through one contact-aware MuJoCo pipeline.
- `atec_locomotion_checkpoint` preserves a reproducible Isaac Lab rough-terrain locomotion training lineage for a Unitree B2 with Piper arm, including checkpoints, exports, resolved configurations, provenance hashes, and verification scripts.
- Korea University's Robot Intelligence Lab is a useful new source-network candidate for humanoid/quadruped motion generation, retargeting, robot foundation models, HRI, and dexterous manipulation.
- NVIDIA's Isaac Loco-Manipulation team has an active Shanghai-based 2026 machine-learning internship focused on humanoid loco-manipulation, GR00T/Cosmos, Isaac Lab/Newton workflows, sim-to-real, and on-robot validation.

<details>
<summary><strong>New Papers</strong></summary>

No new paper was selected today. At run time, the focused robotics arXiv monitoring feed had no legged-specific records later than 2026-08-13, and broader searches did not surface a sufficiently recent paper that cleared the relevance and source-verification bar.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### RIMKit
- Link: https://github.com/tmjeong1103/RIMKit
- Category: retargeting / toolkit / viewer
- Robot Type: humanoid — Unitree G1/H1/H2/R1, ROBOTIS K1, Apptronik Apollo, LimX Oli, Fourier N1, PNDbotics ADAM Lite, Booster T1, ENGINEAI PM01
- Simulator: MuJoCo
- Deploy: sim / browser / data
- Summary: A unified motion-retargeting toolkit that converts Kimodo or GEM-X SOMA human motion into contact-aware whole-body motion for eleven humanoid robots, with CLI, Python, browser demo, safe NPZ export, and rendered previews.
- Notes: Created 2026-08-10 and actively updated through 2026-08-16; developed at Korea University's Robot Intelligence Lab. The current CoRe pipeline includes collision refinement and grounding, a compiled C++ backend with Python fallback, sixteen example motions, and Apache-2.0 source licensing. Generated motions should be validated in simulation before hardware use.

### atec_locomotion_checkpoint
- Link: https://github.com/JizhuoChen/atec_locomotion_checkpoint
- Category: RL / control / reproducibility snapshot
- Robot Type: quadruped mobile manipulator — Unitree B2 + AgileX Piper
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim / data
- Summary: A preserved rough-terrain locomotion training framework and checkpoint lineage for a B2-Piper platform, covering flat pretraining, heading-aware rough-terrain transfer, and fine-grained full-state continuation.
- Notes: Created 2026-08-15 and updated 2026-08-16. It provides exact checkpoint hashes, TorchScript and ONNX exports, resolved YAML configurations, TensorBoard events, provenance manifests, terrain assets, verification tooling, and a 2,048-environment PPO relaunch script. The maintainer notes that stochastic retraining is not expected to reproduce byte-identical final weights because all simulator and GPU RNG state was not saved. MIT licensed.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Robot Intelligence Lab — Sungjoon Choi and Kyungjae Lee
- Institution: Korea University
- Homepage: https://sites.google.com/view/sungjoon-choi/home
- GitHub: https://github.com/sjchoi86
- Lab / Department: Robot Intelligence Lab; Department of Artificial Intelligence and Department of Statistics
- Key Topics: humanoid / quadruped / motion generation / motion retargeting / robot foundation models / human-robot interaction / dexterous manipulation
- Notes: Proposed new source-network addition. The lab officially lists natural motion generation for humanoids and quadrupeds, socially and physically interactive companion robots, and dexterous robotic hands. The newly surfaced RIMKit repository gives a concrete, actively maintained signal around multi-platform humanoid motion retargeting.
- Students and Representative Works:
  - [Taemoon Jeong](https://taemoon.notion.site/taemoon-page) — [RIMKit](https://github.com/tmjeong1103/RIMKit)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### NVIDIA — Isaac Loco-Manipulation Team
- Type: Machine Learning Internship — Humanoid Robotics, 2026
- Location: Shanghai, China
- Source: official careers page — https://jobs.nvidia.com/careers/job/893395444508
- Deadline: unknown
- Topics: humanoid loco-manipulation / mobile manipulation / GR00T / Cosmos / Isaac Lab / Newton / reinforcement learning / imitation learning / sim-to-real / whole-body control
- Status: active
- Notes: Proposed new opportunity addition. The role targets current Master's or PhD students and covers algorithm development from simulation and synthetic-data workflows through sim-to-real transfer and on-robot validation. Preferred signals include humanoid experience, real-robot testing, C++/Python, PyTorch/JAX/TensorFlow, Isaac Sim/Lab or MuJoCo, foundation models, 3D perception, and dexterous bimanual or whole-body control research. The official page is live; no explicit closing date was visible.

No stale-item removal was identified today.

</details>
