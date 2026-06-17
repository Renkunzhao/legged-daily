**English** | [中文](../zh/drafts/legged-daily-2026-06-17.md)
# Legged Daily - 2026-06-17

## Summary
- arXiv recent feed surfaced several humanoid learning/control papers from June 15-16; the strongest daily picks are a hierarchical whole-body benchmark, disturbance-aware humanoid locomotion training, and terrain-adaptive quadruped locomotion without gait priors.
- RSS 2026 pages are live for multiple high-signal legged/humanoid papers, including vision-based humanoid locomotion, Human2LocoMan, PRIME, and MoE quadruped sim-to-real predictability; these are worth follow-up in the master paper queue.
- Repository signal is mixed but useful: IIT DLS has a mature IsaacLab quadruped locomotion stack, SRL-Locomotion releases a physics-guided jumping framework, and a small Unitree G1 PPO repo is reproducibility-oriented.
- Lab/job signals: CUHK Legged Robot Lab is actively seeking Fall 2027 PhD applicants plus RA/engineer candidates; EPFL BioRob has a Fall 2026 humanoid neuromechanics PhD/Postdoc call; ETH RSL continues rolling openings across PhD/Postdoc/research-engineer roles.

<details>
<summary><strong>New Papers</strong></summary>

### HumanoidArena: Benchmarking Egocentric Hierarchical Whole-body Learning
- Link: http://arxiv.org/abs/2606.17833v1
- Source: arXiv cs.RO
- Date: 2026-06-16
- Authors: Taowen Wang, Zikang Xie, Bin Yang, Yunheng Wang, Zizhao Yuan, Yuetong Fang, Yixiao Feng, Yichi Wang, et al.
- Topics: humanoid, whole-body learning, hierarchical control, benchmark, egocentric tasks
- Summary: Introduces a benchmark for egocentric hierarchical whole-body humanoid learning, targeting the coupling between high-level task decisions and low-level dynamic execution.
- Notes: High long-term relevance as a benchmark-style paper for humanoid policy evaluation and task/control hierarchy design.

### ADAPT: Analytical Disturbance-Aware Policy Training for Humanoid Locomotion
- Link: http://arxiv.org/abs/2606.16542v1
- Source: arXiv cs.RO
- Date: 2026-06-15
- Authors: Bofan Lyu, Jindou Jia, Kuangji Zuo, Yanshuo Lu, Shijia Han, Gen Li, Boyu Ma, Jingliang Li, et al.
- Topics: humanoid, locomotion, disturbance rejection, reinforcement learning, force interaction
- Summary: Proposes analytical disturbance-aware training for humanoid locomotion policies that must remain stable and accurate under unexpected external contacts.
- Notes: Relevant for force-interactive humanoid deployment where simple domain randomization may be insufficient.

### LoComposition: Terrain-Adaptive Energy-Efficient Quadruped Locomotion without Gait Priors
- Link: http://arxiv.org/abs/2606.15896v1
- Source: arXiv cs.RO
- Date: 2026-06-14
- Authors: Loukas Kordos, Leonard T. Franz, Simon Rappenecker, Oliver Hausdoerfer, Angela P. Schoellig, Pavel Kolev, Georg Martius
- Topics: quadruped, locomotion, energy efficiency, terrain adaptation, reinforcement learning
- Summary: Separates task rewards, operational constraints, terrain adaptation, and gait preferences instead of folding them into one dense reward, aiming for energy-efficient adaptive quadruped locomotion without explicit gait priors.
- Notes: Good candidate for the curated paper list because it addresses reward decomposition and energy-aware locomotion design.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / simulator / deployment toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab, MuJoCo
- Deploy: both
- Summary: IsaacLab extension from IIT Dynamic Legged Systems Lab for quadruped locomotion tasks across Aliengo, Go2, B2, and HyQReal2, including sim-to-sim and ROS2 sim-to-real deployment pipelines.
- Notes: Mature and high-signal compared with most daily GitHub hits; includes rapid motor adaptation, morphological symmetries, AMP, and robot-parameter identification hooks.

### Kr1shu01/SRL-Locomotion
- Link: https://github.com/Kr1shu01/SRL-Locomotion
- Category: RL / control
- Robot Type: quadruped / biped
- Simulator: Isaac Gym, MuJoCo, Unity
- Deploy: sim / partial hardware reference
- Summary: Official implementation of SRL, a physics-guided reinforcement-learning framework combining SLIP feedforward motion generation, RL feedback control, adaptive fusion, and curriculum learning for agile robot jumping.
- Notes: README reports validation on Unitree Go2 and X02-lite across jumping tasks; repository notes that some platform-specific deployment infrastructure and pretrained models are not included.

### JJJEEERRR/g1-locomotion-rl
- Link: https://github.com/JJJEEERRR/g1-locomotion-rl
- Category: RL / reproducibility
- Robot Type: humanoid
- Simulator: MuJoCo Playground / MJX / Brax
- Deploy: sim
- Summary: Reproducible PPO locomotion project for the 29-DoF Unitree G1, with YAML-driven experiments, documented reward terms, domain randomization, rollout rendering, and reported 150M-step training results.
- Notes: Small repo and not an official lab release, but useful as a transparent G1 training/reproduction reference.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### CUHK Legged Robot Lab
- Institution: The Chinese University of Hong Kong
- Homepage: https://cuhkleggedrobotlab.github.io/
- Lab / Department: Department of Mechanical and Automation Engineering; supervised by Prof. Liu Yun-Hui
- Key Topics: quadruped, locomotion, whole-body loco-manipulation, perception, navigation, safe actuator/system design
- Notes: Lab homepage states active search for Fall 2027 PhD applicants plus multiple RA and engineer openings. Recent 2026 news includes launch of the Hong Kong Embodied AI Lab and an RSS 2026 acceptance on voltage-constrained actuation.

### RSS 2026 legged / humanoid paper pages
- Institution: Robotics: Science and Systems 2026 program
- Homepage: https://roboticsconference.org/program/papers/
- Key Topics: humanoid, quadruped, locomotion, loco-manipulation, sim-to-real, motion estimation
- Notes: Program pages are live for several relevant papers, including “Now You See That: Learning End-to-End Humanoid Locomotion from Raw Pixels” (Paper 27), “PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots” (Paper 29), “Human2LocoMan” (Paper 122), and MoE robust quadrupedal locomotion predictability (Paper 156). Treat as a follow-up source for master-list insertion, not as a single lab entry.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRob
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: rolling until filled
- Topics: humanoid, human locomotion neuromechanics, bio-inspired control, reinforcement learning
- Status: active
- Notes: Fall 2026 project on investigating and leveraging human locomotion neuromechanics using humanoid robots, with one Postdoc and one PhD position; applications considered continuously, good start date around September 2026.

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Engineer / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling / unknown
- Topics: legged robots, mobile manipulation, MPC, reinforcement learning, perception, navigation, teleoperation, robotic systems
- Status: active
- Notes: Official openings page lists multiple rolling opportunities, including research staff/software engineers for legged robots, mobile manipulators, and field deployment systems.

### CUHK Legged Robot Lab
- Type: PhD / RA / Engineer
- Location: Hong Kong
- Source: official lab page
- Deadline: Fall 2027 PhD cycle / RA and engineer timing unknown
- Topics: legged locomotion, loco-manipulation, perception and navigation, actuator/system design
- Status: active
- Notes: Lab homepage explicitly states active search for self-motivated Fall 2027 PhD applicants and multiple RA/engineer openings.

</details>
