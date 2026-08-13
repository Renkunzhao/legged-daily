**English** | [中文](../zh/drafts/legged-daily-2026-08-13.md)
# Legged Daily - 2026-08-13

Status: Draft only; awaiting confirmation before publication and master-list merge.

## Summary
- SMPC demonstrations can bootstrap sparse-reward offline-to-online RL for complex loco-manipulation, with reported real-hardware transfer to an arm-equipped Spot and Unitree G1.
- ContactIPM combines contact-aware interior relaxation with stagewise optimal-control structure; its official implementation includes reproducible comparisons and closed-loop contact validation.
- AWS released a same-day sample stack for collecting, annotating, fine-tuning, evaluating, and deploying VLA policies on a Unitree Go2 quadruped with a 6-DoF arm.
- RAI Institute, ETH Zurich, and TUM form a notable collaboration around planner-generated data and robot learning across morphologies.
- Flexion Robotics posted two Zürich openings focused on generative humanoid whole-body motion; the previously tracked Amazon Safe Locomotion page is now unavailable.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Loco-Manipulation From SMPC Demonstrations With Sparse Offline-to-Online RL
- Link: [arXiv](https://arxiv.org/abs/2608.12063) · [Project page](https://pages.rai-inst.com/smpc2rl/)
- Source: arXiv
- Date: 2026-08-12
- Authors: Martin Schuck, Maks Sorokin, Simone Manni, Duy Ta, Angela P. Schoellig, Marco Hutter, Simon Le Cleac'h, Jan Brüdigam
- Topics: loco-manipulation / sparse-reward RL / offline-to-online RL / sampling-based MPC / sim-to-real
- Summary: Uses a rapidly tunable sampling-based MPC expert in simulation to generate offline demonstrations, then bootstraps an off-policy agent that learns with sparse task rewards before phasing into online RL; the project reports deployment of pushing, rolling, lifting, and navigation-related skills on an arm-equipped Spot quadruped and a Unitree G1 humanoid.
- Notes: The project reports near-perfect simulated success with expert data, failure without it, and locally faster completion than the SMPC teacher; the paper is marked under submission, and no dedicated official code repository for this paper was found during this run.

### ContactIPM: A Structure-Exploiting Interior-Point Solver for Contact-Implicit Trajectory Optimization
- Link: [arXiv](https://arxiv.org/abs/2608.11731) · [Official code](https://github.com/chenyucheng2016/ContactIPM)
- Source: arXiv
- Date: 2026-08-12
- Authors: Yucheng Chen
- Topics: contact-implicit trajectory optimization / MPCC / optimal control / NMPC / contact planning
- Summary: Introduces a primal-dual solver that embeds complementarity pairs in a barrier-coupled elastic interior relaxation, eliminates slack and dual variables stagewise, and solves the reduced Newton system with Riccati recursion, targeting robust and efficient contact-rich trajectory optimization.
- Notes: Reported matched benchmarks show mixed task-dependent speedups against IMPACT and consistent speedups against CRISP on four fixed cases; the released validation is primarily manipulation and quasi-static contact rather than a demonstrated legged-hardware controller, so its relevance is methodological.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### aws-samples/sample-vla-mobile-manipulation-on-aws
- Link: https://github.com/aws-samples/sample-vla-mobile-manipulation-on-aws
- Category: robot learning / VLA / mobile manipulation / toolkit
- Robot Type: quadruped
- Simulator: custom stack / none specified as a single canonical simulator
- Deploy: both
- Summary: An AWS sample for bring-your-own VLA development on a Unitree Go2 with a D1 6-DoF arm, covering task specification, teleoperation data collection, Bedrock-assisted annotation, openpi or OpenVLA-OFT fine-tuning on EC2, rolling-window evaluation, and phase-routed deployment for navigation, grasping, transport, and placement.
- Notes: Created 2026-08-13; Python, MIT-0, 1 star at check time. It is an integration sample rather than an independently benchmarked locomotion or manipulation algorithm, and requires substantial cloud and robot-specific setup.

### chenyucheng2016/ContactIPM
- Link: https://github.com/chenyucheng2016/ContactIPM
- Category: optimal control / MPC / solver
- Robot Type: general
- Simulator: custom benchmark models / CasADi interfaces
- Deploy: sim
- Summary: Apache-2.0 C++ implementation of ContactIPM for direct-transcription NMPC and optimal-control problems with dynamics, bounds, nonlinear inequalities, and complementarity constraints, including pinned competitor revisions, audited benchmark artifacts, reproduction instructions, and closed-loop contact tests.
- Notes: Created 2026-06-09 and updated 2026-08-11; 0 stars at check time. The current public examples emphasize cart, box, and T-pushing problems rather than a legged model, so it should be tracked as enabling contact-optimization infrastructure.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### RAI Institute / ETH Zurich / Technical University of Munich collaboration
- Institution: RAI Institute; ETH Zurich; Technical University of Munich
- Homepage: https://pages.rai-inst.com/smpc2rl/
- arXiv: https://arxiv.org/abs/2608.12063
- GitHub: https://github.com/rai-opensource/judo
- Lab / Department: RAI Institute; ETH Robotic Systems Lab network; TUM learning systems collaboration
- Key Topics: quadruped / humanoid / loco-manipulation / RL / MPC / sim-to-real
- Notes: The new SMPC-to-RL work connects Martin Schuck, Angela P. Schoellig, Marco Hutter, and RAI researchers around planner-generated offline data, sparse-reward learning, and cross-morphology hardware deployment. The project also points to RAI's established Judo sampling-based MPC toolbox as enabling infrastructure.

### Flexion Robotics motion-generation and humanoid autonomy team
- Institution: Flexion Robotics
- Homepage: https://flexion.ai/about
- LinkedIn: https://www.linkedin.com/company/flexion-robotics
- X: https://x.com/FlexionAI
- YouTube: https://www.youtube.com/@Flexion-AI
- Lab / Department: Motion Generation / Control / AI Engineering
- Key Topics: humanoid / whole-body motion / generative models / RL / locomotion / manipulation
- Notes: Flexion describes an autonomy stack spanning command, control, manipulation, and locomotion across humanoid hardware. Its team page links ETH Zurich and former NVIDIA robotics researchers—including Nikita Rudin and advisor/co-founder Marco Hutter—to dedicated motion-generation, control, perception, and VLA groups; the two same-day openings make this a concrete team-growth signal.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Flexion Robotics — Research Engineer, Generative Humanoid Motion Generation
- Type: Research Engineer
- Location: Zürich, Switzerland
- Source: [official careers page](https://flexion.ai/careers/525e50)
- Deadline: unknown
- Topics: humanoid / whole-body motion / diffusion / flow matching / multimodal generative models / robot trajectory generation
- Status: active
- Notes: Full-time AI Engineering role posted 2026-08-13, seeking experience in generative or vision-conditioned motion models and deployment of learning-based robot trajectories; Omniverse or Genesis and foundation-model fine-tuning are listed as relevant experience.

### Flexion Robotics — Internship, Humanoid Motion Generation (Diffusion or Flow Matching)
- Type: Internship
- Location: Zürich, Switzerland
- Source: [official careers page](https://flexion.ai/careers/526f62)
- Deadline: unknown
- Topics: humanoid / diffusion / flow matching / autoregressive models / 3D perception / imitation learning
- Status: active
- Notes: AI Engineering internship posted 2026-08-13 for a current master's or PhD student, combining generative whole-body trajectory generation with 3D environment perception.

### Proposed Removal / Stale Item
- Current Status: no longer actionable
- Reason: The previously tracked Amazon Robotics Compass “Senior Applied Scientist, Safe Locomotion” official page now returns a not-available message, so it should no longer be surfaced as active.
- Source Checked: https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass

</details>
