**English** | [中文](../zh/drafts/legged-daily-2026-07-30.md)
# Legged Daily - 2026-07-30

## Summary
- Two new papers met the inclusion bar: a hardware-focused treatment of extreme actuator delay on a USD 300 quadruped, and a whole-body benchmark that separates VLM action decisions from low-level balance and motor execution.
- The cost-constrained quadruped paper is the strongest direct legged-robotics signal: it frames the Mini Pupper 2's measured 76 ms transport delay and missing velocity/torque feedback as a POMDP, then compares temporal policies and deployment-side observation reconstruction.
- HumanCLAW evaluates closed-loop whole-body decision making over 1,218 long-horizon episodes in 41 indoor scenes; the best of nine evaluated VLMs reaches only 16.8% success, exposing weak embodied self-awareness after target recognition.
- Three implementation repositories met the repo bar: the paper-linked Mini Pupper 2 training/deployment stack, a controlled Unitree G1 sim-to-real ablation suite with standalone ONNX export, and an Apache-2.0 Genesis/ROCm Go2 locomotion and benchmarking pipeline.
- HumanCLAW creates a new Meta–NTU–UW–Brown–Northwestern collaboration signal, but its official repository is currently a project page and release checklist rather than usable code. The previously tracked LAAS-CNRS Gepetto humanoid PhD remains active and closes tomorrow, 2026-07-31 at 23:59.

<details>
<summary><strong>New Papers</strong></summary>

### Reinforcement Learning on Cost-Constrained Quadrupedal Hardware
- Link: https://arxiv.org/abs/2607.26434
- Source: arXiv
- Date: 2026-07-29
- Authors: Javier C. Weddington, Bence P. Ölveczky, Stephen A. Baccus
- Topics: quadruped locomotion / reinforcement learning / sim-to-real / actuator delay / partial observability / low-cost hardware / Mini Pupper 2
- Summary: The paper studies locomotion on a roughly USD 300 Mini Pupper 2 whose brushed position servos expose a measured 76 ms transport delay and no velocity or torque feedback, treating deployment as a partially observable control problem and comparing feedforward, recurrent, and engineered observation-bridge approaches.
- Notes: A time-aware LSTM learns a self-sustaining rhythmic gait reported to tolerate an additional 320 ms latency perturbation. The released code includes Isaac Lab training, trained policies, servo models, and a Raspberry Pi deployment controller; the paper and repository report physical-robot walking.

### HumanCLAW: Can Vision-Language Models Act Through a Body?
- Link: https://arxiv.org/abs/2607.27180
- Source: arXiv
- Date: 2026-07-29
- Authors: Siyao Li, Jiawei Gu, Shuai Liu, Kairui Hu, Zekun Li, Linjie Li, Chengcheng Tang, Po-Chen Wu, Ivan Shugurov, Lingni Ma, Michael Zollhoefer, Sizhe An, Abhay Mittal, Amy Zhao, Ranjay Krishna, Manling Li, Ziwei Liu, Chuan Guo
- Topics: humanoid embodiment / vision-language models / whole-body skills / embodied navigation / benchmark / action intelligence
- Summary: HumanCLAW evaluates a frozen VLM's moment-to-moment whole-body decisions by translating atomic skill commands into continuous human motion with contact, collision, and gravity while factoring out balance and motor-tracking failures.
- Notes: HumanCLAW-Bench contains 1,218 long-horizon find–navigate–interact episodes across 41 indoor scenes. The strongest of nine evaluated VLMs reaches 16.8% success; the authors attribute many failures after target recognition to weak embodied self-awareness. This is adjacent to humanoid robotics rather than a physical-robot locomotion result, and the promised code, benchmark, and weights are not yet released.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### baccuslab/SpotDMouse — P2-Terrain_Challenge
- Link: https://github.com/baccuslab/SpotDMouse/tree/main/P2-Terrain_Challenge
- Category: reinforcement learning / sim-to-real / deployment / actuator modeling
- Robot Type: quadruped; Mini Pupper 2
- Simulator: NVIDIA Isaac Lab / Isaac Sim
- Deploy: both simulation and physical hardware through a Raspberry Pi 4 + ESP32 Mini Pupper stack
- Summary: The official implementation for “Reinforcement Learning on Cost-Constrained Quadrupedal Hardware,” providing the Isaac Lab environment, PPO configurations, trained LSTM and MLP policies, learned per-joint servo models, diagnostics, and the on-robot controller.
- Notes: This is a substantive implementation rather than a release placeholder. It explicitly models delayed brushed servos, includes reproducible servo-model training data and scripts, and links simulation and real-robot videos. The project directory was pushed on 2026-07-28; no repository-level license was detected at verification.

### Theo-guo00/optimus-loco
- Link: https://github.com/Theo-guo00/optimus-loco
- Category: reinforcement learning / locomotion / sim-to-real ablation / deployment export
- Robot Type: humanoid; Unitree G1
- Simulator: NVIDIA Isaac Lab / Isaac Sim with RSL-RL PPO
- Deploy: simulation plus standalone ONNX/TorchScript export; physical G1 deployment is not demonstrated
- Summary: A controlled G1 locomotion study covering a four-level domain-randomization ladder, push recovery, 0–40 ms action-latency modeling, perceptive rough-terrain locomotion, loco-manipulation, and standalone 50 Hz policy inference.
- Notes: The repository includes task configurations, delayed-action code, train/evaluation/export scripts, raw evaluation records, plots, and a write-up. The README reports three-seed latency ablations and training with 1,024 environments on one RTX 4060 8 GB GPU. It is usable research code, but “deployable” currently means exported runtime artifacts rather than verified hardware transfer; no repository license was detected.

### himanshu748/chaal
- Link: https://github.com/himanshu748/chaal
- Category: reinforcement learning / locomotion / simulator benchmarking / ROCm tooling
- Robot Type: quadruped; Unitree Go2
- Simulator: Genesis on the gs.amdgpu backend, with RSL-RL PPO on ROCm
- Deploy: simulation only
- Summary: An Apache-2.0 end-to-end Go2 velocity-tracking pipeline that trains physics and PPO from scratch on one AMD Radeon GPU and includes environment-count scaling, evaluation, raw benchmark JSON, diagnostics, and rendering tools.
- Notes: The README reports 4,096 parallel robots, 49.2 million environment steps in 8 minutes 41 seconds, and 0.096 m/s baseline tracking error. It also documents two reproducibility-relevant Genesis pitfalls involving headless OpenGL setup and paired-surface friction. The code is substantive, but no sim-to-real or physical-robot deployment is claimed.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### HumanCLAW collaboration network
- Institution: Meta; Nanyang Technological University; University of Washington; Brown University; Northwestern University
- Homepage: https://human-claw.github.io/
- arXiv: https://arxiv.org/abs/2607.27180
- GitHub: https://github.com/Human-CLAW/HumanCLAW
- Lab / Department: cross-institution embodied AI and whole-body motion collaboration
- Key Topics: humanoid embodiment / VLM action intelligence / whole-body skills / embodied navigation / physical interaction benchmarks
- Notes: The collaboration released HumanCLAW and a public leaderboard, creating a useful source network at the boundary of humanoid motion generation and general-purpose VLM decision making. Track the official repository for the promised harness, motion-generator weights, half-physics simulator, benchmark episodes, and evaluation tooling; as of 2026-07-30, these artifacts remain on the release checklist rather than in the repository.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto Team — PhD in Humanoid Robotics: Safe Reinforcement Learning
- Type: PhD
- Location: Toulouse, France, with part of the project at CNRS-AIST JRL in Tsukuba, Japan
- Source: official website — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59
- Topics: humanoid / legged locomotion / reinforcement learning / MPC / whole-body control / safe control
- Status: active; deadline reminder for a previously tracked opportunity
- Notes: Rechecked on 2026-07-30. The 36-month PhD starts on 2026-10-01 with listed remuneration of EUR 2,300 gross per month. The thesis combines RL-selected discrete contact, footstep, gait, and behavior decisions with online MPC for feasible continuous whole-body motion, with planned validation on PAL Robotics Kangaroo and/or Unitree H1/R1. This is not a new master-list addition; it is surfaced because the official deadline is tomorrow.

</details>
