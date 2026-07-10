**English** | [中文](../zh/drafts/legged-daily-2026-07-10.md)
# Legged Daily - 2026-07-10

## Summary
- Contact-rich humanoid loco-manipulation is the clearest high-signal paper theme today: ContactMimic adds explicit body-part contact commands to humanoid motion tracking and reports real-world Unitree G1 contact-control validation.
- Extreme-slope humanoid locomotion remains active: HumoSlope uses slope-adaptive ZMP regularization and biomechanical reward gating for blind, proprioceptive traversal of steep grass slopes.
- Interactive humanoid teleoperation is becoming a data-collection interface: a Vision Pro + LLM-assisted Unitree H1 system combines voice locomotion commands, VR manipulation retargeting, and multimodal logging.
- Repository signal is moderate rather than fresh-breaking: the best actionable repo today is an Isaac Lab / Unitree Go2 locomotion baseline with a June push-recovery release and explicit robustness curriculum details.
- Lab/source tracking update: ContactMimic points to Saurabh Gupta’s group as a useful humanoid loco-manipulation source; the STL quadruped locomotion project page is worth watching as a CoRL 2026 submission signal.
- Job signal: no newly verified legged-specific opening was found today; keep existing active watchlist items, with no proposed removals from this run.

<details>
<summary><strong>New Papers</strong></summary>

### ContactMimic: Humanoid Object Interaction via Contact Control
- Link: https://arxiv.org/abs/2607.08742
- Source: arXiv
- Date: 2026-07-09
- Authors: Xinyao Li, Xialin He, Runpei Dong, Saurabh Gupta
- Topics: humanoid / loco-manipulation / contact control / motion tracking / sim-to-real
- Summary: Introduces ContactMimic, a humanoid learning framework that tracks explicit part-level binary contact commands in addition to keypoint trajectories, enabling the same pose motion to produce or suppress physical contact as commanded.
- Notes: Project page reports Unitree G1 real-world validation across five contact-rich motions and emphasizes that keypoint-only tracking is insufficient for tasks such as sitting, wiping, pushing, and leaning.

### Physics-Guided Biomechanical Gait Adaptation for Humanoid Locomotion on Extreme Sloped Terrains
- Link: https://arxiv.org/abs/2607.07830
- Source: arXiv
- Date: 2026-07-08
- Authors: Xuanyu Chen, Mohan Liu, Dengchen Mei, Zhihao Gu, Haitian Zhang, Kaimin Mao, Haiyue Zhu, Shijun Yan, Lin Wang
- Topics: humanoid / locomotion / reinforcement learning / slope traversal / sim-to-real / proprioceptive control
- Summary: Presents HumoSlope, a two-stage physics-guided framework that combines slope-adaptive ZMP regularization with a biomechanical slope gait adapter to reduce crouched-gait degeneration on steep slopes.
- Notes: The paper reports blind outdoor traversal of grass slopes up to 62.7% / 32.1 degrees using a deployed actor that relies on proprioception rather than online exteroceptive sensing.

### Immersive Social Interaction with VR and LLM-Assisted Humanoids
- Link: https://arxiv.org/abs/2607.07430
- Source: arXiv
- Date: 2026-07-08
- Authors: Niraj Pudasaini, Geeta Chandra Raju Bethala, Pranav Doma, Anthony Tzes, Yi Fang
- Topics: humanoid / teleoperation / VR / LLM-assisted control / locomotion commands / data collection
- Summary: Describes an Apple Vision Pro based teleoperation system for Unitree H1 that combines voice-controlled locomotion, VR manipulation retargeting, dexterous-hand control, and bidirectional social interaction.
- Notes: Reported novice-user evaluations include 80% object-manipulation success and 70% social cube-passing success; the multimodal logs are positioned as future imitation-learning data.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### BrandoUlissi/isaaclab-go2-locomotion
- Link: https://github.com/BrandoUlissi/isaaclab-go2-locomotion
- Category: RL / control / training baseline
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Unitree Go2 reinforcement-learning locomotion baseline in NVIDIA Isaac Lab, with PPO training, deterministic replay scripts, TensorBoard plotting, and documented push-recovery extension.
- Notes: Latest verified release `v0.2.0-pushrecovery` was published on 2026-06-03 and adds mixed impulsive/sustained disturbance curricula; the release reports 87.5% recovery under 120 N peak impulse loads in simulation.

### CMUYUY/legged-gym-in-isaac-lab
- Link: https://github.com/CMUYUY/legged-gym-in-isaac-lab
- Category: RL / simulator migration / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: Migrates the classic `legged_gym` ANYmal-C rough-terrain reinforcement-learning setup from Isaac Gym style APIs to NVIDIA Isaac Lab, including DirectRLEnv, USD assets, observations/actions/rewards, and RSL-RL training glue.
- Notes: Not a fresh 2026-07 update, but useful as a reference for teams porting older Isaac Gym legged-locomotion code to Isaac Lab.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Saurabh Gupta / UIUC Robotics and Embodied AI
- Institution: University of Illinois Urbana-Champaign
- Homepage: https://saurabhg.web.illinois.edu/
- arXiv: https://arxiv.org/abs/2607.08742
- Lab / Department: Robotics and Embodied AI research group / UIUC Computer Science
- Key Topics: humanoid / loco-manipulation / embodied AI / contact-rich interaction / robot learning
- Notes: ContactMimic adds a strong humanoid contact-control signal from this author network; track follow-up project pages and code releases around contact-conditioned humanoid motion tracking.
- Students and Representative Works:
  - [Xinyao Li](https://lixinyao11.github.io/contactmimic-page/) — [ContactMimic: Humanoid Object Interaction via Contact Control](https://arxiv.org/abs/2607.08742)

### STL-based Quadruped Locomotion Project
- Institution: unknown / anonymous CoRL 2026 submission
- Homepage: https://stl-locomotion.github.io/
- Lab / Department: unknown
- Key Topics: quadruped / reinforcement learning / temporal logic specifications / reward shaping / gait control / MuJoCo XLA
- Notes: Project page presents a CoRL 2026 submission on Signal Temporal Logic reward shaping for Barkour quadruped locomotion in MJX. Because authors are anonymous, treat this as a source-watch signal rather than a confirmed lab entry until authorship is public.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No newly verified legged-specific opening found today
- Type: watching
- Location: unknown
- Source: current daily search / existing `jobs.md` watchlist
- Deadline: unknown
- Topics: locomotion / humanoid / quadruped / RL / MPC / robot learning
- Status: watching
- Notes: Search was affected by bot-detection on some web-search queries, so this run did not add a new job. Existing active entries in `jobs.md` remain the best opportunities to monitor, especially EPFL Biorobotics, ETH RSL, RoMI Lab, CUHK Legged Robot Lab, Legged AI Lab / Shanghai Innovation Institute, Field AI, NVIDIA GEAR, and Amazon robotics roles.

</details>
