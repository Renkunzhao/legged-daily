**English** | [中文](../zh/drafts/legged-daily-2026-10-22.md)
# Legged Daily - 2026-10-22

## Summary
- SuperMimic trains a humanoid motion tracker through one differentiable world model; it reports surpassing a 7-day, 128-GPU baseline in 3 GPU-hours and transfers to a Unitree G1.
- "Watch Your Step" predicts upcoming footholds and samples the elevation map only around them, reaching a given terrain difficulty in about a third of the training iterations and transferring zero-shot to a Unitree G1.
- An ETH RSL team trains a single end-to-end quadruped jumping policy for lunar gravity, with a hardware vertical jump under gravity offloading.
- No new repository, lab/professor signal, or job opening was verified today (GitHub search was unavailable in this session and no project/code links were found for the papers above).

<details>
<summary><strong>New Papers</strong></summary>

### SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model
- Link: https://arxiv.org/abs/2610.28480
- Source: arXiv
- Date: 2026-10-20
- Authors: Qiayuan Liao, Yiyang Shao, Junfeng Long, Kevin Zakka, Roberto Horowitz, Pieter Abbeel, Koushil Sreenath
- Topics: humanoid whole-body control / motion tracking / differentiable world model / scaling / sim-to-real
- Summary: Fits one differentiable world model of shared dynamics from logged rigid-body-simulator transitions and trains it jointly with the tracking policy, using backpropagation through short imagined rollouts to give analytic policy gradients.
- Notes: The abstract reports exceeding a state-of-the-art tracker trained for 7 days on 128 GPUs within 3 hours on one GPU, more than 1000× fewer GPU-hours, and 25 failures out of 129,514 benchmark motions versus 179 for the baseline (zero after 9.8 hours on two GPUs). Transfers to a physical Unitree G1 on diverse and acrobatic motions. No code link was found; results not independently reproduced.

### Watch Your Step: Anticipated Perception for Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.29612
- Source: arXiv
- Date: 2026-10-21
- Authors: Matthias Heyrman, Chenhao Li, Ioannis Dadiotis, Marco Hutter
- Topics: perceptive locomotion / foothold prediction / elevation map / humanoid / zero-shot transfer
- Summary: A lightweight foothold prediction model, trained alongside the policy from proprioception and the velocity command, selects small elevation-map patches around predicted footholds so the policy sees only step-relevant terrain.
- Notes: The abstract reports reaching a given terrain difficulty in roughly a third of the training iterations versus the full map, better results where footholds are sparse and on unseen terrain, and parity with an attention-based encoder trained at several times the cost. Zero-shot transfer to a Unitree G1 on obstacles, stairs, gaps, and step-downs indoors and outdoors. No code link was found.

### End-to-End Reinforcement Learning for Quadrupedal Jumping in Lunar Gravity
- Link: https://arxiv.org/abs/2610.29586
- Source: arXiv
- Date: 2026-10-21
- Authors: Levin Müller, Oliver Fischer, Marco Trentini, Yusuke Tanaka, Marco Hutter
- Topics: quadruped / jumping / planetary exploration / reinforcement learning / sim-to-real
- Summary: A multistage RL approach yields one end-to-end policy for commanded point-to-point jumping under lunar gravity using only mission-compatible onboard sensing.
- Notes: In simulation, landing errors are smaller than the robot's body size, and the authors analyze torque/power demands and robustness to control-update freezes of up to 1 s in flight. Hardware shows a vertical jump under lunar-gravity offloading with torque and power profiles consistent with simulation; point-to-point jumps are shown in simulation only per the abstract.

</details>

<details>
<summary><strong>New Repos</strong></summary>

No newly verified repository in this run.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No newly verified lab or professor signal in this run.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No newly verified opening
- Type: PhD / RA / Internship / Research Engineer / Postdoc
- Source: official-source review
- Deadline: unknown
- Topics: humanoid / quadruped / locomotion / robot learning
- Status: watching
- Notes: No opening was confirmed on an official page. Existing entries remain unchanged; the previously proposed LAAS-CNRS safe-RL PhD removal (deadline 2026-07-31, expired) remains pending confirmation.

</details>
