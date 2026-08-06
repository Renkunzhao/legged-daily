**English** | [中文](../zh/drafts/legged-daily-2026-08-06.md)
# Legged Daily - 2026-08-06

## Summary
- Two recent papers newly met the inclusion bar: LightParkour unifies perceptive locomotion and contact-rich humanoid parkour in one deployable depth policy, while FDDC introduces an onboard-computable dynamic-CoM observation and a reproducible single-leg-balance benchmark.
- FDDC is today's strongest reproducibility signal: its new Apache-2.0 repository includes training and evaluation code, a cross-simulator benchmark with adapters for eight released policies, data, a trained policy, Unitree G1 assets, and hardware deployment instructions.
- EngineAI released an official MIT-licensed GMR adaptation for PM01 and T800, supporting BVH, SMPL-X, AMASS, and OMOMO workflows with MuJoCo visualization and export to the standard GMR trajectory format.
- No 2026-08-06 arXiv submission in the screened cs.RO/cs.LG new lists clearly surpassed the relevance bar; the two paper entries below are high-signal recent items from August 1-3 that had not appeared in the previous daily draft.
- Light Origins is a new source worth watching for hardware-centered humanoid learning. Amazon Robotics Compass's Safe Locomotion role remains active on its official careers page.

<details>
<summary><strong>New Papers</strong></summary>

### Growing Humanoid Parkour Skills through Real2Sim2Real
- Link: https://light-loco-parkour.github.io/
- Source: official project page / paper PDF
- Date: 2026-08-03
- Authors: Hongming Chen, Zhuoran Li, Hongxi Wang, Jiangpeng Hu, Ziliang Li, Peize Liu, QingRui Zhao, Xuhao Liu, Liang Pan, Ximin Lyu, Yuntao Ma, Tingxiang Fan
- Topics: humanoid parkour / perceptive locomotion / whole-body control / skill distillation / real-to-sim-to-real / depth policy
- Summary: LightParkour grounds short human-motion clips in physics, expands each seed skill across terrain variations, and distills locomotion plus contact-rich whole-body parkour into a single deployable policy driven by onboard depth perception.
- Notes: The official page reports one policy running locomotion and parkour on Lightbot 0 and shows hardware behaviors including climbing, jumping, vaulting, and obstacle negotiation. Results are currently supported by the authors' project page and paper PDF; no arXiv record was verified today, and the newly created third-party GitHub implementation contains only a minimal placeholder rather than a usable release.

### First Deployable Dynamic-CoM: A Unified Policy and Method-Agnostic Benchmark for Humanoid Single-Leg Balance
- Link: https://arxiv.org/abs/2608.00500
- Source: arXiv
- Date: 2026-08-01
- Authors: Yikai Zhou, Xingyun Wang, Jieming Cui, Bozhou Chen, Yikai Fan, Yixin Zhu, Wenxin Li
- Topics: humanoid balance / dynamic center of mass / capture point / reinforcement learning / sim-to-sim benchmark / sim-to-real / Unitree G1
- Summary: FDDC reconstructs a support-foot-relative dynamic-CoM observation from encoders and IMU without requiring unavailable base linear velocity, then pairs it with postural-control-inspired rewards to train a hardware-deployable single-leg-balance policy.
- Notes: The authors report clean balance on 86 of 90 held-out motions across nine pose classes and real Unitree G1 transfer, while eight released general policies score 0 of 90 under the benchmark's clean-balance criterion. These remain author-reported preprint results, but the full benchmark and policy stack were released on 2026-08-06.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### FDDC
- Link: https://github.com/zhouyikai888/FDDC
- Category: RL / benchmark / dataset / deployment
- Robot Type: humanoid
- Simulator: MuJoCo plus a distinct sim-to-sim evaluation environment
- Deploy: both
- Summary: Official Apache-2.0 implementation of First Deployable Dynamic-CoM, including training and evaluation code, a method-agnostic single-leg-balance benchmark, adapters for eight released humanoid policies, stratified motion data, a trained policy, Unitree G1 assets, and hardware deployment support.
- Notes: Created on 2026-08-06. This is a substantive release rather than a paper-only stub; reported benchmark scores and hardware performance should still be independently reproduced.

### EngineAI GMR
- Link: https://github.com/engineai-robotics/GMR
- Category: retargeting / toolkit / viewer
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: data / sim
- Summary: EngineAI's official MIT-licensed adaptation of General Motion Retargeting converts BVH and SMPL-X-family human motions into trajectories for the PM01 and T800 humanoids, with MuJoCo visualization and standard GMR PKL export.
- Notes: Created on 2026-08-05. It supports LAFAN1 BVH, SMPL-X, AMASS, and OMOMO workflows and includes both robot model assets; SMPL-X body models and some motion datasets must be downloaded separately under their own licenses.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Light Origins Robotics Team
- Institution: Light Origins
- Homepage: https://light-loco-parkour.github.io/
- YouTube: https://youtu.be/96Rfm7OmHjY
- Lab / Department: Robotics team
- Key Topics: humanoid parkour / perceptive locomotion / whole-body control / motion learning / skill distillation / real-to-sim-to-real
- Notes: LightParkour is a strong new hardware-centered signal: the team presents a unified onboard depth policy spanning ordinary locomotion and contact-rich parkour on its Lightbot 0 humanoid. Track the group for a public paper index, official code release, and follow-up technical reports; the only GitHub implementation found today is third-party and currently incomplete.
- Students and Representative Works:
  - [Hongming Chen et al.](https://light-loco-parkour.github.io/) — [Growing Humanoid Parkour Skills through Real2Sim2Real](https://light-loco-parkour.github.io/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-06 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role owns learning-based controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms. It explicitly combines RL and sim-to-real with formal safety mechanisms and model-based whole-body control; the official page remains accessible today.

</details>
