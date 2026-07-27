**English** | [中文](../zh/drafts/legged-daily-2026-07-27.md)
# Legged Daily - 2026-07-27

## Summary
- One previously untracked paper met the inclusion bar today: an NCKU team uses prompt-generated human videos, 3D pose reconstruction, motion retargeting, motion stitching, and RL tracking to teach diverse whole-body tasks to a simulated Unitree G1.
- The paper is a useful synthetic-data pipeline signal, but all reported validation is in four simulation scenarios; it does not demonstrate sim-to-real transfer or physical-robot deployment.
- One newly discovered official code repository met the repo bar: `mturan33/isaac-g1-ulc` publishes Isaac Lab training/evaluation code and checkpoints for Unitree G1 loco-manipulation, with unusually explicit reproducibility notes and experimental caveats.
- The repository is attached to a paper already tracked in June rather than a new paper today. Its README documents important confounds in the published dual-vs-unified critic comparison, so the headline causal claim should be interpreted cautiously.
- Amazon Robotics Compass has a new high-relevance Senior Applied Scientist opening for safe locomotion, covering RL, formal safety constraints, whole-body control, sim-to-real, and physical quadruped/humanoid deployment.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Diverse Humanoid Tasks via Synthetic Video Scenarios without Real World Data
- Link: https://arxiv.org/abs/2607.21648
- Source: arXiv; accepted to IEEE/ASME AIM 2026
- Date: 2026-07-22
- Authors: Yun-Hao Tsai, Cong-Thanh Vu, Yen-Chen Liu
- Topics: humanoid robot learning / synthetic video / motion retargeting / imitation learning / reinforcement learning / Unitree G1
- Summary: The framework generates diverse human-motion videos from text prompts, reconstructs 3D body motion, retargets it to a humanoid, stitches independently generated clips, and trains an RL motion-tracking policy to reproduce task-level whole-body behaviors.
- Notes: The paper evaluates four scenarios with a simulated Unitree G1. It reports successful task completion and adaptation to motion variations, but provides no physical-robot or sim-to-real experiment. No paper-specific public code repository was linked during verification.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### mturan33/isaac-g1-ulc
- Link: https://github.com/mturan33/isaac-g1-ulc
- Category: reinforcement learning / locomotion / loco-manipulation / benchmark
- Robot Type: humanoid; Unitree G1
- Simulator: NVIDIA Isaac Lab / Isaac Sim
- Deploy: simulation; pretrained checkpoints are public, and the repository includes an external Unitree hardware bridge, but the tracked paper reports simulation experiments
- Summary: Official code for the previously tracked RL4IL @ ICRA 2026 paper comparing dual and unified critic architectures for G1 whole-body loco-manipulation, including staged PPO training, a standardized evaluation harness, pretrained weights, and an additional 29-DoF G1 + DEX3 pipeline.
- Notes: MIT-licensed, 16 GitHub stars at verification, and actively updated on 2026-07-27. The README is unusually candid: the headline comparison uses single runs whose curricula, reward weighting, and action dimensionality were not fully controlled, so the measured checkpoint gap is useful but cannot cleanly establish critic architecture as the sole cause. Proposed addition to `repos.md` after confirmation.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Yen-Chen Liu / NCKU Mechanical Engineering humanoid-learning team
- Institution: National Cheng Kung University, Taiwan
- Homepage: https://arxiv.org/abs/2607.21648
- arXiv: https://arxiv.org/abs/2607.21648
- Lab / Department: Department of Mechanical Engineering
- Key Topics: humanoid learning / synthetic demonstrations / motion retargeting / reinforcement learning / passive-dynamics-inspired locomotion
- Notes: Yun-Hao Tsai, Cong-Thanh Vu, and Yen-Chen Liu report a prompt-to-video-to-policy pipeline for simulated Unitree G1 whole-body tasks, accepted to IEEE/ASME AIM 2026. This is a publication signal rather than a verified recruiting announcement; no separate official lab page was confirmed in this run.
- Students and Representative Works:
  - Yun-Hao Tsai and Cong-Thanh Vu — [Learning Diverse Humanoid Tasks via Synthetic Video Scenarios without Real World Data](https://arxiv.org/abs/2607.21648)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active; official posting verified 2026-07-27
- Notes: The role owns learning-based locomotion algorithms for walking, running, stairs, and fall recovery on physical quadruped and humanoid platforms. It explicitly combines RL policies with formal safety mechanisms and model-based whole-body control, and asks for hardware evaluation and failure-mode analysis. Proposed addition/update in `jobs.md` after confirmation.

</details>
