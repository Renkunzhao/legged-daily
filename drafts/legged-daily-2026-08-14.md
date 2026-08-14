**English** | [中文](../zh/drafts/legged-daily-2026-08-14.md)
# Legged Daily - 2026-08-14

Status: Draft only; awaiting confirmation before publication and master-list merge.

## Summary
- HumanTracker adds a 153-hour humanoid motion-tracking benchmark and a preference-aligned HumanScore metric designed to expose contact, support, and stability failures missed by framewise kinematic errors.
- HumanoidVLN evaluates vision-language navigation through physically executed bipedal locomotion across four humanoid embodiments in Isaac Sim, with a small Unitree G1 sim-to-real pilot.
- A new Unitree H1 robustness repository packages frozen-policy evaluation, controlled physics mismatch sweeps, multi-seed statistics, regression thresholds, and CPU-testable CI around Isaac Lab.
- RobotUniversityGiar is a broad educational G1 policy-training and switching stack with Genesis CPU/Apple Silicon support, while Torq-MPC is currently only an early ROBIO 2026 quadruped-jumping project placeholder.
- Li Yi's official publication page now lists HumanTracker as an ECCV 2026 work; USC's Dynamic Robotics and Control Lab is connected to HumanoidVLN and continues to advertise legged-robot student opportunities.
- The previously tracked LAAS-CNRS humanoid safe-RL PhD deadline has passed and should be removed from the active list after confirmation.

<details>
<summary><strong>New Papers</strong></summary>

### HumanTracker: Towards Comprehensive and Human-Aligned Motion Tracking Benchmark
- Link: [arXiv](https://arxiv.org/abs/2608.13555) · [Li Yi publication page](https://ericyi.github.io/)
- Source: arXiv / ECCV 2026
- Date: 2026-08-13
- Authors: Dairu Liu, Zekun Qi, Jiayu Zeng, Ruixi Yu, Yu Guan, Yintianrun Zhang, Xuchuan Chen, Sikai Liang, Zekai Li, Chenghuai Lin, Xinqiang Yu, Wenyao Zhang, He Wang, Li Yi
- Topics: humanoid / motion tracking / benchmark / contact quality / preference-aligned evaluation
- Summary: Introduces a humanoid tracking benchmark with roughly 153 hours of professionally performed optical motion trajectories across four motion families, plus HumanScore, a preference-aligned metric trained on 12,000 motion pairs to better identify unstable support, incorrect contacts, foot skating, and mistimed touch-downs.
- Notes: Accepted to ECCV 2026. The arXiv page and Li Yi's official publication page verify the paper, but no public code or benchmark-download link was found during this run.

### HumanoidVLN: A Physics-Grounded Simulator and Benchmark for Vision-Language Navigation Across Diverse Humanoid Embodiments
- Link: [arXiv](https://arxiv.org/abs/2608.12860) · [Project page](https://humanoid-vln.github.io/)
- Source: arXiv
- Date: 2026-08-13
- Authors: Quan-Dung Pham, Anh Dao, The-Anh Nguyen, Minh Nguyen-Dinh, Phuong Nam Dang, Tri Pham, Hung Tran, Bach Dao, Tuyen P. Le, Truong Nguyen, Quan Nguyen
- Topics: humanoid / vision-language navigation / Isaac Sim / locomotion / MPC / sim-to-real
- Summary: Builds a physics-grounded VLN benchmark in Isaac Sim where Unitree G1, Unitree H1, and two internal humanoids execute navigation through hierarchical RL locomotion with interchangeable PD or MPC path tracking, rather than kinematic teleportation.
- Notes: The paper reports 933 collision-aware reference episodes, tests four VLN models across four embodiments, and includes a 20-episode Unitree G1 sim-to-real pilot. The project is under Humanoids 2026 review; code, benchmark, and data are promised upon acceptance and are not yet publicly released.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### 22kashaf-khan/humanoid-simulation-robustness-benchmark
- Link: https://github.com/22kashaf-khan/humanoid-simulation-robustness-benchmark
- Category: benchmark / RL / validation / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab
- Deploy: sim
- Summary: A reproducible Unitree H1 locomotion validation framework that freezes a project-trained PPO policy and evaluates it under controlled contact-friction, whole-robot mass, and actuator-effort mismatch using survival, velocity-tracking, base-tilt, and joint-limit metrics.
- Notes: Created 2026-08-12; Python, 0 stars, no detected license at check time. The repository reports 55 runs and 5,500 episodes across 11 conditions and five seeds, includes checkpoint/config/result artifacts, 43 CPU-only tests, regression checks, and GitHub Actions CI; it is an engineering benchmark rather than a new locomotion algorithm or hardware validation.

### GIAR-UTN/RobotUniversityGiar
- Link: https://github.com/GIAR-UTN/RobotUniversityGiar
- Category: RL / control / education / toolkit
- Robot Type: humanoid
- Simulator: Genesis / Isaac Gym / Isaac Sim
- Deploy: both
- Summary: A course-oriented Unitree G1 stack that combines local or cloud PPO training, checkpoint operations, backend-agnostic policy supervision, safety-gated live policy switching, web control, and sim/real adapters, with a particular focus on CPU and Apple Silicon Genesis workflows.
- Notes: Created 2026-08-13; Python, BSD-3-Clause, 0 stars at check time. It builds on legged_gym, unitree_rl_gym, and LeggedGym-Ex; the real-hardware adapter is explicitly untested, so the current value is primarily educational and simulation/control plumbing rather than verified G1 deployment.

### lab-sun/Torq-MPC
- Link: https://github.com/lab-sun/Torq-MPC
- Category: MPC / control / project page
- Robot Type: quadruped
- Simulator: none disclosed
- Deploy: hardware demonstration / code not released
- Summary: Official placeholder for a ROBIO 2026 project on model predictive control with speed-dependent torque constraints for heavy-payload quadrupedal jumping, currently linking to a demonstration video.
- Notes: Created 2026-08-14; MIT, 0 stars at check time. The repository currently contains only a README and license, with no paper, implementation, robot details, or reproducibility instructions, so track it as an early signal rather than a usable code release.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Li Yi / Human-Centered 3D Vision and Robotics group
- Institution: Tsinghua University
- Homepage: https://ericyi.github.io/
- arXiv: https://arxiv.org/abs/2608.13555
- Lab / Department: Institute for Interdisciplinary Information Sciences
- Key Topics: humanoid / motion tracking / human-aligned evaluation / 3D perception / robot learning
- Notes: Li Yi's official publication page now lists HumanTracker as an ECCV 2026 paper. Together with the same group's Humanoid-GPT, LIMMT, Any2Track, and athletic-humanoid work, this reinforces the group as a high-signal source for humanoid motion tracking, datasets, and evaluation.
- Students and Representative Works:
  - [Zekun Qi](https://qizekun.github.io/) — [HumanTracker](https://arxiv.org/abs/2608.13555) / [Humanoid-GPT](https://qizekun.github.io/humanoid-gpt/)

### Quan Nguyen / Dynamic Robotics and Control Laboratory
- Institution: University of Southern California
- Homepage: https://sites.usc.edu/quann/
- arXiv: https://arxiv.org/abs/2608.12860
- Lab / Department: Viterbi School of Engineering / Aerospace and Mechanical Engineering
- Key Topics: humanoid / quadruped / wheel-legged robots / locomotion / nonlinear control / trajectory optimization / reinforcement learning
- Notes: HumanoidVLN adds a physics-grounded navigation benchmark spanning RL locomotion and PD/MPC tracking to this source network. The official lab page continues to describe agile and robust legged locomotion as its core focus and advertises aligned student opportunities.
- Students and Representative Works:
  - [Quan-Dung Pham](https://arxiv.org/search/cs?searchtype=author&query=Pham,+Q) — [HumanoidVLN](https://humanoid-vln.github.io/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### USC Dynamic Robotics and Control Laboratory
- Type: PhD / undergraduate or MS research volunteer
- Location: Los Angeles, California, USA
- Source: [official lab page](https://sites.usc.edu/quann/)
- Deadline: unknown / graduate admissions cycle
- Topics: legged robots / quadruped / humanoid / wheel-legged robots / control / optimization / planning / reinforcement learning
- Status: watching
- Notes: The lab says it is constantly looking for self-motivated students aligned with its research. Existing USC undergraduate and MS students may contact Quan Nguyen about research-volunteer work; prospective PhD students are directed to apply through USC AME and mention him. No project-specific funded opening or deadline was verified, so this is a lab-level opportunity signal rather than a confirmed vacancy.

### Proposed Removal / Stale Item
- Current Status: expired / no longer actionable
- Reason: The tracked LAAS-CNRS Gepetto PhD in humanoid safe reinforcement learning listed an application deadline of 2026-07-31 23:59, which has passed; it should no longer be surfaced as active unless the official team announces an extension or replacement call.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
