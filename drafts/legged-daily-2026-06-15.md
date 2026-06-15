**English** | [中文](../zh/drafts/legged-daily-2026-06-15.md)
# Legged Daily - 2026-06-15

## Summary
- Selected two fresh June 12 arXiv / RA-L legged-robot papers: force-guided fall recovery for armless bipedal-wheeled robots and attention-based proprioceptive state estimation for Unitree Go1.
- Kept one June 10 humanoid loco-manipulation RL paper because it gives a compact controlled comparison of dual vs. unified critics in Isaac Lab on Unitree G1.
- Selected two repositories/resources: a newly created Isaac Lab H1 rough-terrain locomotion project and an Isaac Lab quadruped-to-humanoid tutorial; both are practical but should be treated as community code rather than canonical baselines.
- Industry and lab signal: Figure announced Helix 02 as a full-body loco-manipulation VLA system; PSI Lab's RSS 2026 Ψ₀ page reinforces USC / NVIDIA / WorldEngine as a humanoid foundation-model source to watch.
- Recruiting signal: NC State HIER Lab lists expected 2027 PhD/postdoc openings in hierarchical RL whole-body control and humanoid tele whole-body control; Amazon Personal Robotics has an official 2026 PhD research intern/co-op posting that explicitly includes locomotion among several robotics areas.

<details>
<summary><strong>New Papers</strong></summary>

### Robust Fall Recovery for Armless Bipedal-Wheeled Robots Via Force-Guided Learning
- Link: https://arxiv.org/abs/2606.14270
- Source: arXiv / RA-L
- Date: 2026-06-12
- Authors: Haidong Hou, Zhangguo Yu, Tao Han, Hengbo Qi, Khaleel Ghazal, Yu Zhang, Yidong Du, Xuechao Chen, Fei Meng
- Topics: fall recovery / bipedal-wheeled robots / constrained reinforcement learning / teacher-student learning / humanoid generalization
- Summary: Introduces FTSR, a force-guided teacher-student RL framework with stage-wise rewards that teaches an armless bipedal-wheeled robot to recover from falls using only leg actuation, then deploys the policy on hardware and reports generalization to a high-DoF humanoid.
- Notes: Accepted by IEEE Robotics and Automation Letters, 2026. Project page listed by authors: https://2350575870.github.io/force-guided.github.io/ . High relevance for robust autonomy because recovery is a core failure-mode skill for real deployments.

### GAIT: Legged Robot Proprioceptive State Estimation with Attention over Inertial-Leg Tokens
- Link: https://arxiv.org/abs/2606.14160
- Source: arXiv
- Date: 2026-06-12
- Authors: Young-Rang Seo, Hajun Kim, Sangmin Kim, Dongyun Kang, Hae-Won Park
- Topics: proprioceptive state estimation / attention / inertial-leg tokens / contact uncertainty / quadruped locomotion
- Summary: Proposes tokenizing inertial and leg-wise measurements for an attention-based proprioceptive estimator, letting the network reweight sensor channels according to contact conditions without an explicit contact estimator.
- Notes: Evaluated on Unitree Go1, including debris terrain not modeled in simulation and unseen gait patterns; useful for tracking estimator designs that sit below learning-based locomotion policies.

### Critic Architecture Matters: Dual vs. Unified Critics for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.11891
- Source: arXiv / ICRA 2026 Workshop on Reinforcement Learning for Imitation Learning
- Date: 2026-06-10
- Authors: Mehmet Turan Yardımcı
- Topics: humanoid loco-manipulation / reinforcement learning / critic architecture / Isaac Lab / Unitree G1
- Summary: Compares unified and dual-critic RL designs for Unitree G1 loco-manipulation in Isaac Lab, reporting faster reaching, higher throughput, and higher validated reach rate for dual critics under a 13-level sequential curriculum.
- Notes: Concise workshop paper, but high-signal for implementation choices when RL fine-tuning imitation or manipulation policies together with locomotion objectives.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### egeozgul/humanoid-locomotion-isaaclab
- Link: https://github.com/egeozgul/humanoid-locomotion-isaaclab
- Category: RL / locomotion / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Community Isaac Lab project training a PPO rough-terrain locomotion policy for Unitree H1 with 4096 parallel environments, terrain curriculum, reward plots, and reported training metrics.
- Notes: README reports Isaac Lab 0.45.9 / Isaac Sim 5.0, RSL-RL 2.3.3, 393M timesteps, about 1h14m training time on RTX 5070 Ti, and 0.74% fall rate in its setup. GitHub API check: created 2026-06-12, updated 2026-06-12, 0 stars at check time.

### Lab-of-AI-and-Robotics/IsaacLab-Tutorial
- Link: https://github.com/Lab-of-AI-and-Robotics/IsaacLab-Tutorial/
- Category: tutorial / RL / locomotion / toolkit
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab
- Deploy: sim
- Summary: A multi-chapter Isaac Lab tutorial that walks from quadruped locomotion with Unitree Go2 toward humanoid locomotion with Unitree H1, intended as a practical learning path for legged-robot RL environments.
- Notes: Treat as educational material rather than a benchmark. GitHub API check: 9 stars, updated 2026-06-06.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Jaemin Lee — HIER Lab, NC State University
- Institution: North Carolina State University
- Homepage: https://hier-robotics.github.io/
- Lab / Department: Hybrid Intelligent Experimental Robotics Lab; Department of Mechanical and Aerospace Engineering; Joint Department of Biomedical Engineering at UNC–Chapel Hill and NC State
- Key Topics: legged humanoid and animaloid robotics / loco-manipulation / whole-body control / robot intelligence / hierarchical RL / tele whole-body control
- Notes: Official lab page lists humanoid loco-manipulation, hybrid dynamical systems, learning-based robotics, safety-critical control, heterogeneous robot teams, and generative AI for motion; recent 2026 news includes an NVIDIA Academic Award supporting humanoid research.

### PSI Lab / USC Physical Superintelligence Lab — Ψ₀ project
- Institution: USC / NVIDIA / WorldEngine collaboration signal from project page
- Homepage: https://psi-lab.ai/Psi0/
- Key Topics: humanoid loco-manipulation / foundation models / VLA / real-world humanoid data / egocentric human video
- Notes: RSS 2026 Ψ₀ project page describes an open foundation model for humanoid loco-manipulation, trained with about 829 hours of egocentric human video and 31 hours of humanoid robot data, with a stated plan to open-source the ecosystem. Good source-network signal; code release was not verified today.

### Figure AI — Helix 02
- Institution: Figure AI
- Homepage: https://www.figure.ai/news/helix-02
- Key Topics: humanoid loco-manipulation / whole-body VLA / visuomotor policy / learned whole-body controller / sim-to-real RL
- Notes: Official announcement says Helix 02 extends Helix from upper-body control to full-body autonomy, including walking, manipulation, and balance in a unified neural system; details remain company-reported and should be treated as an industry signal rather than a reproducible research artifact.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### HIER Lab — NC State University
- Type: PhD / Postdoc
- Location: Raleigh, North Carolina, USA
- Source: official lab page
- Deadline: unknown / 2027 intake signal
- Topics: hierarchical RL-based whole-body control / tele whole-body control of humanoids / loco-manipulation
- Status: watching
- Notes: Official page says the lab expects openings for 2027 PhD students and postdocs and provides an interest form; applicants must also apply through the official graduate admissions system.

### Amazon Personal Robotics Group — Research Scientist II Intern / Co-op 2026
- Type: Internship / Co-op
- Location: multiple Amazon locations; exact team/location finalized at offer stage
- Source: official Amazon Jobs page
- Deadline: unknown
- Topics: robotics / manipulation / autonomous mobile robots / mobile manipulation / locomotion / controls / perception / robot learning / planning / HRI
- Status: active
- Notes: Official posting targets current PhD students for 2026 Robotics Research Scientist II intern/co-op roles across Amazon robotics teams; locomotion is explicitly listed but the role is broad, so relevance depends on team matching.

### Proposed Removal / Stale Item
- Current Status: no removal proposed today
- Reason: Previously surfaced EPFL BioRob, ETH RSL, and Field AI opportunities still looked actionable from recent official checks; no formal `jobs.md` cleanup was performed in this scheduled draft.
- Source Checked: daily search and recent official-source checks

</details>
