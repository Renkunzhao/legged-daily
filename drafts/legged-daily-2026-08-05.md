**English** | [中文](../zh/drafts/legged-daily-2026-08-05.md)
# Legged Daily - 2026-08-05

## Summary
- Three new papers met the inclusion bar, all centered on humanoid motion learning and contact-rich control: dynamically feasible contact-implicit retargeting, context-aware motion priors, and a reusable flow-matching prior trained from unordered poses.
- Shooting for Contact is the strongest systems result: its direct simulation-based multiple-shooting formulation resolves contact internally and supports zero-shot Unitree G1 crawling and a 180-degree jump-turn, while also demonstrating morphology transfer to a quadruped.
- CMP and PFM-HR address complementary weaknesses in motion-prior learning: CMP selects task-relevant motion supervision without manual labels, while PFM-HR extracts reusable transition guidance from unordered pose collections.
- No repository met the implementation bar today. CMP states that code will be released, while no official public implementation was verified for the other selected papers; low-signal or unrelated newly created repositories were excluded.
- Caltech AMBER Lab produced another high-signal real-G1 control update through Shooting for Contact. Amazon Robotics Compass's previously tracked Safe Locomotion role remains active on the official careers page and is still pending confirmation for master-list addition.

<details>
<summary><strong>New Papers</strong></summary>

### Shooting for Contact: Contact-Implicit Multiple Shooting for Dynamic Motion Retargeting
- Link: https://arxiv.org/abs/2608.03116
- Source: arXiv
- Date: 2026-08-04
- Authors: Sergio A. Esteban, Jason H. K. Siu, Derrick Mach, Junheng Li, Vince Kurtz, Joel W. Burdick, Aaron D. Ames
- Topics: humanoid control / motion retargeting / contact-implicit optimization / differentiable simulation / motion-imitation RL / sim-to-real
- Summary: The method embeds a differentiable simulator inside direct simulation-based multiple shooting to convert kinematic references into dynamically feasible whole-body trajectories without prescribing contact modes, then uses the optimized motions to accelerate imitation-policy training and enable zero-shot Unitree G1 deployment.
- Notes: The project page demonstrates command-conditioned crawling with hands, elbows, knees, and feet in contact, an on-hardware 180-degree jump-turn, and morphology transfer to a quadruped jump-turn. Contact, friction, impacts, self-collision, joint limits, and actuation constraints are handled inside the simulator; performance claims remain author-reported preprint results.

### Learning Context-Aware Motion Priors for Humanoid Control
- Link: https://arxiv.org/abs/2608.03234
- Source: arXiv
- Date: 2026-08-04
- Authors: Yunyang Mo, Yi Gu, Yangchen Zhou, Hanyang Cao, Renjing Xu
- Topics: humanoid control / motion priors / reinforcement learning / imitation learning / context adaptation / sample efficiency
- Summary: Context-Aware Motion Priors learn task-to-motion relevance from high-advantage policy rollouts and use it to adapt a general prior to the current task without manual skill labels, dataset partitioning, or a separate skill-discovery stage.
- Notes: The authors instantiate the method with adversarial and score-matching motion priors and report consistent task-performance and sample-efficiency gains across five humanoid control tasks, including robustness to imbalanced motion datasets. The paper says code will be released publicly, but no official repository was verified today.

### Pose Flow Matching for Humanoid Robots
- Link: https://arxiv.org/abs/2608.03227
- Source: arXiv
- Date: 2026-08-04
- Authors: Yukang Gao, Yi Gu, Yangchen Zhou, Xingyu Chen, Zhaorui Wang, Fanghai Zhang, Hanyang Cao, Zhengyang Shen, Ji Ma, Runhan Zhang, Lei Han, Renjing Xu
- Topics: humanoid motion tracking / flow matching / motion priors / reinforcement learning / pose geometry / dynamic motions
- Summary: PFM-HR trains a frozen reusable flow-matching prior directly on large-scale unordered pose data, then uses a Pose Geometry Score to reward rollout transitions that align with the learned local geometry of human poses.
- Notes: Unlike temporal priors, the method does not require ordered motion clips; unlike conventional pose priors, it explicitly guides policy-induced pose transitions. The authors report improvements in single-motion and general-motion tracking, especially for highly dynamic motions; no official public code repository was verified today.

</details>

<details>
<summary><strong>New Repos</strong></summary>

No new repository met the implementation and relevance bar today.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Caltech AMBER Lab / Aaron D. Ames and collaborators
- Institution: California Institute of Technology; collaboration with DePaul University
- Homepage: http://www.bipedalrobotics.com/
- arXiv: https://arxiv.org/abs/2608.03116
- Key Topics: humanoid control / contact-implicit optimization / motion retargeting / reinforcement learning / sim-to-real / legged locomotion
- Notes: Shooting for Contact is a new update from the already tracked AMBER source network. Its official project page (https://shooting-for-contact.github.io/) shows zero-shot Unitree G1 crawling and jump-turn deployment plus a quadruped transfer example, strengthening the lab's recurring signal around dynamics-aware humanoid control and physical validation. Treat this as an update to the existing lab entry rather than a new lab addition.
- Students and Representative Works:
  - [Sergio A. Esteban](https://arxiv.org/search/cs?searchtype=author&query=Esteban%2C+S+A) — [Shooting for Contact](https://arxiv.org/abs/2608.03116)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-05 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role owns learning-based controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms. It explicitly combines RL and sim-to-real with formal safety mechanisms and model-based whole-body control, and requires rigorous simulation, hardware, and failure-mode evaluation.

</details>
