**English** | [中文](../zh/drafts/legged-daily-2026-06-29.md)
# Legged Daily - 2026-06-29

## Summary
- This run covers new signals after the 2026-06-23 draft, with the strongest cluster appearing in arXiv submissions from June 24-26.
- The top quadruped signal is Uni-Mo / Quad-Imaginarium: a generative-video-prior pipeline and open dataset for 7,488 language-annotated Unitree Go2 motions, with reported real-hardware validation.
- The top humanoid whole-body signal is SceneBot: a contact-prompted policy interface for free-space locomotion, terrain traversal, and contact-rich whole-body manipulation.
- A practical Go2-W racing/control signal appeared from Berkeley MPC Lab and collaborators, with supplementary code for active roll-control MPC on a wheeled quadruped.
- Additional watch items not promoted into the top-three paper list this time include CWI for LimX Oli humanoid loco-manipulation, Booster Lab for deployable humanoid locomotion data curation, TaskNPoint for few-shot dynamic humanoid skills on Unitree G1, and MPC-Injection for biasing locomotion RL with controller rollouts.
- No high-confidence new job opening was verified in this pass; keep opportunity tracking unchanged unless a direct official posting is found.

<details>
<summary><strong>New Papers</strong></summary>

### Unleashing Infinite Motion: Scaling Expressive Quadrupedal Motion via Generative Video Priors
- Link: https://arxiv.org/abs/2606.28237
- Source: arXiv
- Date: 2026-06-26
- Authors: Youzhi Liu, Li Gao, Yifei Qian, Liu Liu, Yang Cai, Ziqiao Li
- Topics: quadruped / motion dataset / generative video priors / reinforcement learning / Unitree Go2 / sim-to-real
- Summary: Introduces Uni-Mo, a pipeline that uses LLM-generated motion prompts and video diffusion priors to synthesize quadruped behaviors, lift them into 3D trajectories, and train tracking policies for Unitree Go2; the released Quad-Imaginarium dataset contains 7,488 language-annotated motions totaling 18.5 hours, with reported 96.7% deployment success on 392 sampled real-robot motions.
- Notes: High-signal dataset and pipeline candidate for the master list because it attacks quadruped motion-data scarcity without animal motion capture or teleoperation.

### SceneBot: Contact-Prompted General Humanoid Whole Body Tracking with Scene-Interaction
- Link: https://arxiv.org/abs/2606.27581
- Source: arXiv
- Date: 2026-06-25
- Authors: Sirui Chen, Shibo Zhao, Zhen Wu, Jiaman Li, Guanya Shi, C. Karen Liu
- Topics: humanoid / whole-body tracking / contact-rich locomotion / terrain traversal / loco-manipulation / reinforcement learning
- Summary: Proposes a unified humanoid motion-tracking framework that conditions a single policy on reference motions and per-link contact labels, using hindsight scene reconstruction to infer contact-rich interaction graphs from retargeted human motion; demos include free-space motions, terrain traversal, object interaction, and carrying a box upstairs.
- Notes: Strong follow-up source for contact-conditioned humanoid control; the project page states that code and data will be open-sourced.

### Racing a Wheeled Quadruped: Active Load Transfer Mitigation via Model Predictive Control
- Link: https://arxiv.org/abs/2606.26313
- Source: arXiv
- Date: 2026-06-24
- Authors: Marla Eisman, Brian Lam, Samuel Sonnino, Francesco Borrelli
- Topics: wheeled quadruped / Unitree Go2-W / MPC / reinforcement learning / active suspension / high-speed locomotion
- Summary: Presents a hierarchical control stack for autonomous racing with a Unitree Go2-W, combining offline raceline generation, online MPC for lateral load-transfer mitigation, and a low-level whole-body RL policy; physical track experiments report up to 44% lower mean LTR, 8.7% faster lap time, and 21.3% higher peak lateral acceleration.
- Notes: Useful practical complement to learning-heavy locomotion papers because it exposes the vehicle-dynamics/MPC layer and ties directly to a public supplementary repository.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### GaoLii/Quad-Imaginarium
- Link: https://github.com/GaoLii/Quad-Imaginarium
- Category: dataset / retargeting / RL / quadruped motion
- Robot Type: quadruped / Unitree Go2
- Simulator: not specified in repository summary; policy validation reported in simulation and on hardware
- Deploy: data / hardware validation reported
- Summary: Official dataset repository for Quad-Imaginarium, containing 7,488 language-annotated quadruped robot motions generated through video priors and stored in Unitree Go2 configuration space.
- Notes: Repository README reports 18.5 hours of motions at 24 fps, dual language annotations, and real-Go2 validation on 392 sampled motions.

### meisman-ucb/go2w-roll-control-mpc
- Link: https://github.com/meisman-ucb/go2w-roll-control-mpc
- Category: MPC / control / simulation / wheeled quadruped racing
- Robot Type: wheeled quadruped / Unitree Go2-W
- Simulator: dynamic-bicycle closed-loop simulation
- Deploy: sim / hardware experiment video and paper results
- Summary: Supplementary code for Go2-W active roll-control MPC, including raceline generation, a dynamic-bicycle MPC that outputs longitudinal acceleration and yaw/roll moments, simulation scripts, and plotting assets.
- Notes: Good candidate for tracking practical high-speed wheeled-quadruped control; the repository appears to expose the high-level MPC rather than the full low-level robot policy.

### SceneBot Project Page
- Link: https://ericcsr.github.io/scenebot/
- Category: project page / browser demo / humanoid whole-body tracking
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo browser demo
- Deploy: browser / code and data announced as forthcoming
- Summary: Project page for SceneBot with an interactive browser MuJoCo demo and videos covering object interaction, terrain traversal, free-space motion, teleoperation, and reconstructed scenes.
- Notes: Track as a source until the promised code/data repository appears; do not treat it as a released codebase yet.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### SceneBot Team / Amazon FAR, Stanford University, CMU
- Institution: Amazon Frontier AI & Robotics; Stanford University; Carnegie Mellon University
- Homepage: https://ericcsr.github.io/scenebot/
- arXiv: https://arxiv.org/abs/2606.27581
- Key Topics: humanoid / whole-body tracking / contact-rich control / terrain interaction / loco-manipulation
- Notes: The project page lists Amazon FAR, Stanford, and CMU affiliations, and the author set includes Guanya Shi and C. Karen Liu; worth tracking for contact-conditioned humanoid control and scene-interaction datasets.

### Berkeley MPC Lab / Francesco Borrelli collaborators
- Institution: University of California, Berkeley; Politecnico di Milano collaboration on the Go2-W paper
- Homepage: https://www.mpc.berkeley.edu/
- GitHub: https://github.com/meisman-ucb/go2w-roll-control-mpc
- arXiv: https://arxiv.org/abs/2606.26313
- Lab / Department: Model Predictive Control Lab
- Key Topics: MPC / constrained predictive control / robotics / wheeled quadruped racing / active roll control
- Notes: The lab describes work on theoretical and real-time implementation of constrained predictive model-based control; the Go2-W racing paper is a concrete legged-wheeled robotics signal to track.

### Quad-Imaginarium / Uni-Mo Authors
- Homepage: https://github.com/GaoLii/Quad-Imaginarium
- arXiv: https://arxiv.org/abs/2606.28237
- GitHub: https://github.com/GaoLii/Quad-Imaginarium
- Key Topics: quadruped / motion generation / video diffusion priors / language-annotated datasets / Unitree Go2
- Notes: Keep the author network on watch because the paper releases a large quadruped motion dataset and reports real-hardware validation; institutional lab mapping should be verified before inserting into `labs.md`.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No new verified job signal
- Type: watching
- Source: this 2026-06-29 search pass
- Deadline: unknown
- Topics: legged robotics / humanoid / quadruped / locomotion / control
- Status: no confirmed addition
- Notes: No direct official opening with enough confidence was verified during this pass. Keep existing opportunity entries unchanged and continue checking official lab/careers pages in the next run.

</details>
