**English** | [中文](../zh/drafts/legged-daily-2026-07-16.md)
# Legged Daily - 2026-07-16

## Summary
- APT-RL combines trajectory-optimization pretraining, Transformer latent skills, reinforcement learning, and onboard perceptual distillation to run one terrain-conditioned multi-gait policy on KAIST HOUND, including high-speed outdoor traversal.
- EgoHTR releases a scene-aligned 4D human terrain-traversal dataset and reconstruction pipeline, then demonstrates reconstructed-reference deployment on a Unitree G1.
- No new repository met today's reproducibility and maturity bar: the two strongest projects provide project pages, but APT-RL exposes no public code link and EgoHTR's public site repository currently contains the website rather than the promised reconstruction pipeline or dataset release.
- No newly verified opening was added today; the tracked LAAS-CNRS humanoid-robotics PhD remains active with a July 31 deadline.

<details>
<summary><strong>New Papers</strong></summary>

### Agile perceptive multi-skill locomotion for quadrupedal robots in the wild
- Link: https://arxiv.org/abs/2607.13579
- Source: Science Robotics / arXiv
- Date: 2026-07-15
- Authors: Jun-Gill Kang, Jaehyun Park, Tae-Gyu Song, Joon-Ha Kim, Seungwoo Hong, Hae-Won Park
- Topics: quadruped / perceptive locomotion / reinforcement learning / gait transition / sim-to-real
- Summary: APT-RL pretrains Transformer-based latent locomotion skills on 180,000 trajectory-optimization samples, adapts them with reinforcement learning, and distills perception into a single onboard policy that autonomously selects and transitions between gaits across stairs, hurdles, stepping stones, gaps, forest debris, and other uneven terrain.
- Notes: Published in Science Robotics on 2026-07-15. The project reports 4.25 m/s over a 60 cm step, a 6 m/s instantaneous peak during a stair drop-down, and completed 1.1 km urban and 0.34 km forest routes using only onboard sensing and computation. Project page: https://skillquadsr.github.io/. No public code link was visible during review.

### EgoHTR: Egocentric 4D Demonstrations of Human Terrain Traversal
- Link: https://arxiv.org/abs/2607.13472
- Source: arXiv
- Date: 2026-07-15
- Authors: Alex Brandes, Haig Conti Georges Sajelian, Manthan Patel, Dominik Hollidt, Chenhao Li, Matthias Heyrman, Oliver Hausdoerfer, Manuel Kaufmann, Xi Wang, Jonas Frey, Angela P. Schoellig, Christian Holz, Marc Pollefeys, Marco Hutter
- Topics: humanoid / terrain traversal / human motion dataset / 4D reconstruction / imitation learning
- Summary: EgoHTR introduces a scene-aligned egocentric reconstruction pipeline and dataset with 55 human terrain-traversal sequences and more than 150,000 frames, connecting contextual human motion capture to perceptive locomotion policies and reconstructed-reference deployment on Unitree G1 hardware.
- Notes: Project page: https://egohtr.github.io/. The paper says the reconstruction pipeline is open source and designed for community extensions, but the public project-site repository checked today exposed website assets rather than a separately documented code or dataset release; release readiness should be rechecked.

</details>

<details>
<summary><strong>New Repos</strong></summary>

No new repository was selected today. Newly discovered candidates were omitted because they were report-only, website-only, or too incomplete to support a credible reproduction path.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Hae-Won Park / Dynamic Robot Control and Design Lab
- Institution: KAIST
- Homepage: https://skillquadsr.github.io/
- Google Scholar: https://scholar.google.com/citations?user=q7v_ewQAAAAJ&hl=en
- Lab / Department: Department of Mechanical Engineering
- Key Topics: quadruped / dynamic locomotion / perceptive control / reinforcement learning / robot design
- Notes: The APT-RL release adds a strong systems signal around fast, terrain-conditioned multi-skill locomotion on the in-house KAIST HOUND platform, including onboard perception, vibration-aware sensor integration, and kilometer-scale outdoor trials.
- Students and Representative Works:
  - [Jun-Gill Kang](https://jgkang1210.github.io) — [Agile perceptive multi-skill locomotion for quadrupedal robots in the wild](https://skillquadsr.github.io/)

### Marco Hutter / Robotic Systems Lab
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- Lab / Department: Robotic Systems Lab, Department of Mechanical and Process Engineering
- Key Topics: quadruped / humanoid / terrain traversal / perception / robot learning
- Notes: EgoHTR extends the lab's terrain-locomotion line toward scene-aligned human demonstrations: it combines egocentric wearable sensing and portable 3D scanning, benchmarks motion reconstruction, and deploys reconstructed reference motions on Unitree G1 hardware.
- Students and Representative Works:
  - [Alex Brandes](https://arxiv.org/search/cs?searchtype=author&query=Brandes%2C+A) — [EgoHTR](https://egohtr.github.io/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto Team — PhD in Humanoid Robotics
- Type: PhD
- Location: Toulouse, France
- Source: official website — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59
- Topics: humanoid / legged locomotion / reinforcement learning / MPC / whole-body control / safe control
- Status: active
- Notes: Rechecked on 2026-07-16; the official posting remains available and retains the July 31 deadline. The 36-month project combines learned discrete contact and gait decisions with online MPC for dynamically feasible whole-body motion, targeting PAL Robotics Kangaroo and/or Unitree humanoids.

</details>
