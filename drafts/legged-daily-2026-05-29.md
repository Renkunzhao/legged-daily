**English** | [中文](../zh/drafts/legged-daily-2026-05-29.md)
# Legged Daily - 2026-05-29

## Summary
- Humanoid locomotion moved strongly toward high-dynamic and whole-body settings today: SPRINT reports zero-shot sim-to-real sprinting on Unitree G1 at a peak 6 m/s using frequency-adaptive spectral priors.
- HumanoidMimicGen is a high-signal humanoid loco-manipulation data paper: it generates large demonstration sets from a few source demos via whole-body planning and reports stronger real-world policy performance when co-training with generated data.
- ETH Zurich RSL surfaced a technical report on making SAC competitive with PPO for massively parallel legged locomotion training, relevant for future online adaptation and hardware fine-tuning.
- New repository signals are concentrated around humanoid loco-manipulation resources: WholeBodyVLA, SoccerLab, and PHUMA all provide useful tracking points for data, skills, and benchmark/tooling ecosystems.
- ETH Zurich RSL continues to list active PhD, postdoc, research staff/software engineer, robot design, and embedded systems openings tied to legged robots, mobile manipulation, control, learning, planning, and real-world deployment.

<details>
<summary><strong>New Papers</strong></summary>

### SPRINT: Efficient Spectral Priors for Humanoid Athletic Sprints
- Link: https://arxiv.org/abs/2605.28549
- Source: arXiv
- Date: 2026-05-27
- Authors: Yantong Wei, Kaihong Huang, Hainan Pan, Jiawei Luo, Jiawei Zhou, Ziyan Mai, Zhiwen Zeng, Yaonan Wang, Huimin Lu
- Topics: humanoid / sprinting / spectral priors / imitation learning / reinforcement learning / sim-to-real / Unitree G1
- Summary: Introduces frequency-adaptive spectral priors that derive feasible humanoid joint trajectories from only five reference motion sequences and guide a locomotion policy across walking, jogging, and sprinting.
- Notes: The abstract reports zero-shot sim-to-real transfer on Unitree G1, peak sprinting velocity of 6 m/s, and seamless gait transitions; the project page is anonymous at discovery time, so authorship and assets should be rechecked before master-list insertion.

### HumanoidMimicGen: Data Generation for Loco-Manipulation via Whole-Body Planning
- Link: https://arxiv.org/abs/2605.27724
- Source: arXiv
- Date: 2026-05-26
- Authors: Kevin Lin, Ajay Mandlekar, Caelan Reed Garrett, Nikita Chernyadev, Yu Fang, Runyu Ding, Yuqi Xie, Justin Tran, Linxi Fan, Yuke Zhu
- Topics: humanoid / loco-manipulation / imitation learning / demonstration generation / whole-body planning / Unitree G1
- Summary: Generates humanoid loco-manipulation demonstrations by adapting contact-rich whole-body skills from a few source demos to new object poses, interleaving arm skills with locomotion and manipulation planning.
- Notes: The project page reports a simulated G1 benchmark with nine industrial-style tasks and shows that co-training real-world policies with generated data improves real-world success by 20% over real-only training.

### Bridging the Gap: Enabling Soft Actor Critic for High Performance Legged Locomotion
- Link: https://arxiv.org/abs/2605.24975
- Source: arXiv
- Date: 2026-05-24
- Authors: Gianluca Sabatini, Chenhao Li, Marco Hutter
- Topics: legged locomotion / reinforcement learning / Soft Actor-Critic / PPO / IsaacLab / online adaptation
- Summary: Identifies why SAC underperforms PPO in massively parallel legged-locomotion training and adds policy initialization, timeout-aware critic targets, and multi-step returns to close the empirical gap.
- Notes: The HTML version states this is a technical report accompanying an open-source RSL-RL-SAC release, but an official code URL was not verified during this run; follow up on the RSL-RL ecosystem before adding repository links.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### WholeBodyVLA
- Link: https://github.com/OpenDriveLab/WholebodyVLA
- Category: toolkit / resource list / VLA / loco-manipulation
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Resource repository for an ICLR 2026 humanoid Vision-Language-Action framework that learns latent actions from action-free egocentric videos and combines them with a locomotion-oriented RL policy for whole-body loco-manipulation.
- Notes: The README explicitly says there is no concrete open-source code timeline yet; currently best treated as a project/resource hub and literature watchlist rather than an executable codebase.

### SoccerLab
- Link: https://github.com/Renforce-Dynamics/soccerLab
- Category: RL / simulator / toolkit
- Robot Type: humanoid / legged
- Simulator: IsaacLab / MuJoCo-Warp / MJLab
- Deploy: sim
- Summary: Full-stack humanoid soccer platform for recovery, locomotion, kicking, dribbling, multi-agent composition, and finite-state-machine skill switching across IsaacLab and MJLab backends.
- Notes: The repository is under active development and includes fall recovery, AMP-guided kicking, RSL-RL PPO dribbling, Unitree G1-related locomotion baselines, and multi-agent soccer task structure.

### PHUMA
- Link: https://github.com/DAVIAN-Robotics/PHUMA
- Category: dataset / retargeting / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / ProtoMotions
- Deploy: data
- Summary: Code and dataset pipeline for PHUMA, a physically grounded humanoid locomotion dataset built from large-scale human motion data using curation and physics-constrained retargeting.
- Notes: The repository links an arXiv paper, project page, Hugging Face dataset, pre-built G1 and H1-2 data, and notes native support in NVIDIA ProtoMotions for training policies directly on PHUMA.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### NVIDIA / UT Austin HumanoidMimicGen team
- Institution: NVIDIA; The University of Texas at Austin
- Homepage: https://humanoidmimicgen.github.io/
- arXiv: https://arxiv.org/abs/2605.27724
- Key Topics: humanoid / loco-manipulation / imitation learning / synthetic data generation / whole-body planning / VLA data
- Notes: The project is a strong lab/source signal for scalable humanoid loco-manipulation data: it connects simulated G1 benchmarks, generated demonstrations, and sim-plus-real co-training rather than only reporting a controller.

### OpenDriveLab WholeBodyVLA team
- Institution: OpenDriveLab and collaborators; verify exact affiliations before master-list insertion
- Homepage: https://opendrivelab.com/wholebodyvla
- GitHub: https://github.com/OpenDriveLab/WholebodyVLA
- Key Topics: humanoid / Vision-Language-Action / latent action learning / loco-manipulation / egocentric video
- Notes: WholeBodyVLA is useful to track as a humanoid VLA hub: the repository curates related 2025-2026 humanoid loco-manipulation work and exposes the authors' direction around latent action learning from manipulation-aware locomotion videos.

### ETH Zurich Robotic Systems Lab
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- Lab / Department: Robotic Systems Lab
- Key Topics: legged robots / mobile manipulation / MPC / reinforcement learning / perception / field robotics / robot design
- Notes: RSL appears both in today's SAC paper and in official active openings; continue tracking for algorithm releases around RSL-RL, IsaacLab, ANYmal, and real-world legged deployment.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Engineer / Software Engineer / Robot Design Research Staff / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / navigation / actuation / systems
- Status: active
- Notes: Official RSL openings page lists continuous PhD and postdoc searches plus research staff/software engineering roles for legged robots, mobile manipulators, excavator machines, real-world robotic challenges, industrial demonstrations, and search-and-rescue deployment; applications are through linked ETH external forms, not email.

</details>
