**English** | [中文](../zh/drafts/legged-daily-2026-06-18.md)
# Legged Daily - 2026-06-18

## Summary
- Kine2Go adds a high-signal Unitree Go2 dataset and an end-to-end retargeting/imitation pipeline: animal/quadruped mocap is converted into Go2-compatible trajectories, policies, and rollouts.
- VENOM is relevant for cross-embodiment humanoid motion tracking: a GPT-style tracker is trained on multi-humanoid states/actions/rewards without splitting upper/lower body control.
- A new dual-vs-unified critic comparison gives a compact result for humanoid loco-manipulation RL: dual critics outperform unified critics on Unitree G1 reaching while walking.
- Recent open-source signals are strongest around practical Isaac/Genesis legged RL tooling: Kine2Go, Quadrrl, and Go2 push-recovery baselines.
- EPFL BioRob has active Fall 2026 PhD/Postdoc openings connecting humanoid robots, neuromechanics, bio-inspired locomotion, and reinforcement learning.

<details>
<summary><strong>New Papers</strong></summary>

### Kine2Go: Kinematic dataset for the Unitree Go2 robot with diverse gaits and motions
- Link: https://arxiv.org/abs/2606.14433
- Source: arXiv
- Date: 2026-06-12
- Authors: Władysław Pałucki, Paweł Siwak, Krzysztof Ciebiera, Marek Cygan
- Topics: quadruped locomotion / Unitree Go2 / dataset / imitation learning / reinforcement learning / motion retargeting
- Summary: Presents Kine2Go, a Unitree Go2 kinematic trajectory dataset with 800 diverse gait/motion trajectories derived from 40 policies, plus a pipeline that retargets motions from other quadruped morphologies and trains RL policies to follow them.
- Notes: Strong long-term dataset/tooling candidate because it links paper, code pipeline, and Hugging Face artifacts for Go2 imitation-learning workflows.

### VENOM: Versatile Embodied Network for Omni-bodied Motion tracking
- Link: https://arxiv.org/abs/2606.16696
- Source: arXiv
- Date: 2026-06-15
- Authors: Siddharth Padmanabhan, Kazuki Miyazawa, Takato Horii
- Topics: humanoid / full-body motion tracking / cross-embodiment learning / demonstration learning / GPT-style policy
- Summary: Proposes VENOM, a GPT-based cross-embodiment full-body motion tracker for multiple humanoids in simulation, trained from multi-humanoid states, actions, and rewards without decomposing the controller into upper-body and lower-body modules.
- Notes: Useful for tracking the shift from per-robot humanoid motion trackers toward shared multi-embodiment policy models.

### Critic Architecture Matters: Dual vs. Unified Critics for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.11891
- Source: arXiv / ICRA 2026 RL4IL Workshop
- Date: 2026-06-10
- Authors: Mehmet Turan Yardımcı
- Topics: humanoid loco-manipulation / reinforcement learning / multi-objective critics / Unitree G1 / Isaac Lab
- Summary: Compares unified and dual critic architectures for Unitree G1 loco-manipulation in Isaac Lab; dual critics reach targets faster, improve throughput, and achieve higher validated reach rates than a unified critic under the reported curriculum.
- Notes: Directly relevant to multi-critic reward decomposition and RL fine-tuning of imitation-learned humanoid manipulation policies.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### nomagiclab/kine2go-pipeline
- Link: https://github.com/nomagiclab/kine2go-pipeline
- Category: retargeting / dataset / RL / toolkit
- Robot Type: quadruped
- Simulator: Genesis
- Deploy: sim / data
- Summary: End-to-end pipeline for retargeting AI4Animation dog, Vienna Horse Data Collection, and Solo8 motions into Unitree Go2 trajectories, training PPO imitation policies, and generating rollout datasets.
- Notes: Companion tooling for arXiv:2606.14433; artifacts are published as the Kine2Go dataset on Hugging Face.

### lbnmahs/quadrrl
- Link: https://github.com/lbnmahs/quadrrl
- Category: RL / benchmark / simulator toolkit
- Robot Type: quadruped / wheeled-legged quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Isaac Lab-based quadruped locomotion training and benchmarking suite covering multiple legged and wheeled-legged robots, including ANYmal C/D, Spot, Unitree Go2/B2, Go2W/B2W, and other platforms.
- Notes: Useful as a comparative training/evaluation suite rather than a single-method research codebase; supports RSL-RL, RL Games, SKRL, and HARL according to the README.

### BrandoUlissi/isaaclab-go2-locomotion
- Link: https://github.com/BrandoUlissi/isaaclab-go2-locomotion
- Category: RL / control / reproducibility baseline
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Practical Unitree Go2 velocity-tracking and push-recovery PPO baseline in Isaac Lab, with documented training runs, disturbance curricula, and replay/evaluation scripts.
- Notes: The repository positions itself as a portfolio/reproducibility project rather than a paper release, but the push-recovery setup is useful as an engineering reference.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### EPFL BioRob / Auke Ijspeert
- Institution: EPFL
- Homepage: https://www.epfl.ch/labs/biorob/
- Lab / Department: Biorobotics Laboratory
- Key Topics: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- Notes: The lab is advertising a Fall 2026 project on investigating and leveraging human locomotion neuromechanics using humanoid robots, with objectives spanning neuromechanical simulation, spinal/supraspinal control models, and bio-inspired RL locomotion controllers.

### No Magic Lab / University of Warsaw robotics signal
- Institution: University of Warsaw / No Magic Lab-affiliated source signal
- Homepage: https://nomagiclab.github.io/kine2go-pipeline/
- GitHub: https://github.com/nomagiclab/kine2go-pipeline
- Key Topics: quadruped / motion retargeting / Unitree Go2 / imitation learning / Genesis RL
- Notes: Kine2Go is worth tracking as a source cluster because it combines arXiv paper, executable pipeline, and dataset artifacts for Go2 demonstration-data generation.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRob / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: rolling / applications considered continuously until filled
- Topics: humanoid / neuromechanics / locomotion / reinforcement learning / bio-inspired control
- Status: active
- Notes: Fall 2026 opening for one Postdoc and one PhD student on human locomotion neuromechanics with humanoid robots; preferred start around September 2026. PhD applicants must also be accepted by the EPFL doctoral school.

</details>
