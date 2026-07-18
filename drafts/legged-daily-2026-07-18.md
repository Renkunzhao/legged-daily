**English** | [中文](../zh/drafts/legged-daily-2026-07-18.md)
# Legged Daily - 2026-07-18

## Summary
- No new arXiv robotics listing appeared on Saturday; today's paper selections are two high-relevance humanoid works from the current weekly batch that were not included in the previous daily draft.
- Semantic-WBC routes live music or speech into imitation-learned whole-body skills and validates the orchestration pipeline on a physical Unitree G1.
- A second Sapienza work integrates a temporal depth encoder into a Booster T1 reinforcement-learning policy for opponent-aware humanoid soccer dribbling, but currently reports simulation results only.
- The official semantic-WBC repository provides a documented split robot/PC deployment bundle and MuJoCo path, though demo-specific assets are not yet available through a public release and repository-level licensing remains unclear.
- Sapienza's Lab RoCoCo is a useful new humanoid-learning source to track; IHMC is also advertising a full-time legged robotics software and autonomy engineer role covering humanoid autonomy, VLA integration, navigation, and loco-manipulation.

<details>
<summary><strong>New Papers</strong></summary>

### Semantic Audio-driven Understanding for Dynamic Humanoid Whole Body Control
- Link: https://arxiv.org/abs/2607.14182
- Source: RoboCup Symposium 2026 / arXiv
- Date: 2026-07-15
- Authors: J. M. A. Marcelo, M. Brienza, E. Bugli, L. Comito, D. Nardi, D. D. Bloisi, V. Suriani
- Topics: humanoid / whole-body control / reinforcement learning / audio grounding / skill orchestration / sim-to-real
- Summary: The system classifies continuous audio into music or speech, aligns music through fingerprinting and semantic embeddings or grounds speech into a discrete imitation-learned skill library, then schedules the selected whole-body policy through a shared reinforcement-learning control pipeline.
- Notes: Accepted at the 29th RoboCup International Symposium and validated in simulation and on a physical Unitree G1. The contribution is mainly semantic skill selection and orchestration over an existing multi-policy control stack rather than a new low-level locomotion learner. Project page: https://lab-rococo-sapienza.github.io/semantic-WBC/.

### Vision-Based Dribbling for Humanoid Soccer via Privileged Representation Learning
- Link: https://arxiv.org/abs/2607.12702
- Source: arXiv
- Date: 2026-07-14
- Authors: Flavio Maiorana, Valerio Spagnoli, Eugenio Bugli, Flavio Volpi, Daniele Affinita, Vincenzo Suriani, Daniele Nardi, Luca Iocchi
- Topics: humanoid / loco-manipulation / soccer / reinforcement learning / depth perception / privileged learning
- Summary: A temporal depth encoder is embedded into a reinforcement-learning policy through a task-specific projection layer, allowing a simulated Booster T1 humanoid to dribble toward targets and react to obstacles or an active opponent directly from depth observations without explicit scene-state estimation.
- Notes: The paper reports 100% success in nominal target-driven dribbling, 96% with one static obstacle, and 46% against an active ball-attacker. Results are simulation-only, and the lab's associated `learning-to-dribble` repository currently contains only a README and license rather than implementation code.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### semantic-WBC
- Link: https://github.com/Lab-RoCoCo-Sapienza/semantic-WBC
- Category: control / RL / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: An official standalone deployment bundle for audio-driven Unitree G1 whole-body skills, with Python code, G1 configurations, ONNX policy execution, a split robot/PC TCP command pipeline, local audio fingerprinting, simulation scripts, and hardware safety guidance.
- Notes: The repository was substantially prepared for release on 2026-07-15 and is built on RoboJuDo/BeyondMimic components. Base assets can be pulled from upstream, but the README says demo-specific ONNX and audio extras still await a GitHub release or separate URL. No repository-level SPDX license is declared; users should inspect upstream and bundled third-party licenses before reuse.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Lab RoCoCo / Sapienza University of Rome
- Institution: Sapienza University of Rome
- Homepage: https://lab-rococo-sapienza.github.io/semantic-WBC/
- GitHub: https://github.com/Lab-RoCoCo-Sapienza
- Lab / Department: Department of Computer, Control, and Management Engineering
- Key Topics: humanoid / robot learning / whole-body control / reinforcement learning / loco-manipulation / perception
- Notes: The lab's current public output includes two closely related humanoid-learning directions: real Unitree G1 audio-conditioned whole-body skill orchestration and depth-based Booster T1 soccer dribbling. The official GitHub organization also exposes robot-learning and perception projects, making it a useful source for future code and project releases.
- Students and Representative Works:
  - [Michele Brienza](https://arxiv.org/abs/2607.14182) — [Semantic Audio-driven Understanding for Dynamic Humanoid Whole Body Control](https://lab-rococo-sapienza.github.io/semantic-WBC/)
  - [Flavio Maiorana](https://arxiv.org/abs/2607.12702) — [Vision-Based Dribbling for Humanoid Soccer via Privileged Representation Learning](https://arxiv.org/abs/2607.12702)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Proposed Addition — IHMC Robotics Team: Legged Robotics Software and Autonomy Engineer
- Type: Research Engineer
- Location: Pensacola, Florida, United States
- Source: official website — https://www.ihmc.us/2026-software-autonomy-engineer/
- Deadline: unknown
- Topics: humanoid / legged robotics / autonomy / perception / navigation / loco-manipulation / VLA / ROS 2 / reinforcement learning
- Status: active
- Notes: Full-time paid role developing autonomous and semi-autonomous capabilities for humanoid and legged platforms such as Alex. Responsibilities span semantic scene understanding, exploration, planning, navigation, loco-manipulation, VLA or multimodal integration, language interaction, simulation, and hardware field testing. Applications are submitted by email with a resume, cover letter, completed questionnaire, and three references; US work authorization or eligibility to obtain it is required.

</details>
