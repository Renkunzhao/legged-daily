**English** | [中文](../zh/drafts/legged-daily-2026-08-03.md)
# Legged Daily - 2026-08-03

## Summary
- Three high-signal papers entered the review queue: a Science Robotics field outlook on legged robots, CLIFT for closed-loop adaptation of a managed humanoid foundation model, and a dynamics-based treatment of humanoid balance while lifting objects.
- Three newly released repositories met the implementation bar: TheDoorGym for hierarchical door-opening with a legged mobile manipulator, a Berkeley quadrupedal-juggling stack spanning Isaac Lab and MuJoCo, and an Isaac Lab H1 football-dribbling task with a checkpoint and deterministic evaluation.
- The strongest theme today is reproducibility around contact-rich legged skills: the selected repositories expose task code, retained weights, tests or evaluation tools, and explicit limitations rather than only demonstration media.
- No new primary-source lab or professor signal was verified today; author affiliations and repository provenance were reviewed but were not treated as sufficient evidence of a new institutional update.
- ETH Zurich RSL's rolling openings remain active. The official CNRS page now explicitly says the LAAS-CNRS safe-RL humanoid PhD offer is no longer available, strengthening the pending stale-removal recommendation.

<details>
<summary><strong>New Papers</strong></summary>

### Advances, challenges, and opportunities for legged robots
- Link: https://arxiv.org/abs/2607.28952
- Source: Science Robotics / arXiv author manuscript
- Date: 2026-07-29
- Authors: Jonas Frey, Matías Mattamala, Hae-Won Park, Mayank Mittal, Georg Martius, Maike Osborne, Robert Sparrow, Marco Hutter
- Topics: humanoids / quadrupeds / hardware / locomotion / autonomy / data / applications / policy and societal impact
- Summary: A broad field-level assessment of current humanoid and quadruped capabilities, open technical bottlenecks, application prospects, and the ethical, economic, and policy questions that accompany wider deployment.
- Notes: The definitive article appears in Science Robotics, Vol. 11, Issue 116, DOI `10.1126/scirobotics.aee0787`; the arXiv record is the author manuscript and is useful as an accessible retrieval link.

### CLIFT: Turning Gemini Robotics On-Device into Humanoid Specialists via Non-Invasive Closed-Loop Iterative Fine-Tuning
- Link: https://arxiv.org/abs/2607.29172
- Source: arXiv
- Date: 2026-07-31
- Authors: Yuxin Chen, Hari Srikanth, Nathan Jew, Menglin Wu, Pengcheng Wang, Junli Ren, Masayoshi Tomizuka, Peng Xu, Jinyu Xie, Thomas Tian
- Topics: humanoid manipulation / robot foundation models / VLA / closed-loop adaptation / supervised fine-tuning / real-robot learning
- Summary: CLIFT converts deployment-time reward feedback into API-compatible supervised data, enabling iterative closed-loop improvement of the closed-weight Gemini Robotics On-Device policy on agile, contact-rich humanoid tasks without access to weights, gradients, or losses.
- Notes: The paper reports one of the first real-humanoid studies of managed fine-tuning APIs and says two data-flywheel cycles bring selected tasks to near-perfect success; the result is specifically about adapting a proprietary model through its supported interface, not opening or reproducing the base model.

### Balancing of Humanoid with Object Mass: Trade-off Analyses and Lifting Control
- Link: https://arxiv.org/abs/2607.29625
- Source: arXiv
- Date: 2026-07-31
- Authors: Hyunjong Song, William Z. Peng, Joo H. Kim
- Topics: humanoid balance / loco-manipulation / whole-body dynamics / trajectory optimization / lifting / contact constraints
- Summary: The work incorporates object mass into whole-body dynamics and balanced-state basin constraints, characterizes critical and transition masses, and uses the resulting thresholds in trajectory optimization for stable humanoid lift-and-hold and lift-and-release tasks.
- Notes: The paper combines analytical trade-off studies with simulation and experimental demonstrations, making it a useful model-based complement to predominantly heuristic or learning-driven humanoid lifting controllers.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### DeerYoyo/TheDoorGym
- Link: https://github.com/DeerYoyo/TheDoorGym
- Category: reinforcement learning / hierarchical control / legged manipulation / benchmark
- Robot Type: quadruped mobile manipulator; B1Z1 and B2Z1 assets, with B1Z1 used by the released final task
- Simulator: NVIDIA Isaac Gym Preview 4
- Deploy: simulation only; no physical-robot deployment is claimed
- Summary: A BSD-3-Clause reproducible release for approaching a lever handle, grasping and pressing it, pushing the door open, releasing, and traversing the doorway with a hierarchical legged-manipulation pipeline.
- Notes: The repository includes high- and low-level training code, retained checkpoints, assets, pinned environment files, checksums, and an experiment history. The final Exp68 behavior is explicitly hybrid: a learned high-level policy handles approach and contact behavior, while deterministic physical stages maintain the grasp, push, release, and traversal.

### frankwsq242/hierarchical-quadrupedal-juggling
- Link: https://github.com/frankwsq242/hierarchical-quadrupedal-juggling
- Category: reinforcement learning / hierarchical control / legged manipulation / sim-to-sim validation
- Robot Type: quadruped; Unitree Go1 with a back-mounted paddle
- Simulator: NVIDIA Isaac Lab 2.3.2 and MuJoCo
- Deploy: simulation and sim-to-sim; no hardware rollout is claimed
- Summary: A UC Berkeley MEng capstone that combines an interpretable mirror-law or learned high-level planner with a PPO torso-tracking policy to bounce a ping-pong ball while the Go1 moves.
- Notes: The MIT-licensed release includes Isaac Lab training and playback, a committed Pi2 checkpoint and ONNX export, MuJoCo smoke tests and demos, and detailed simulator-transfer diagnostics. The authors clearly state that the learned high-level Pi1 policy has not converged and that perception prototypes are not connected to a deployed policy.

### kingjameschan/isaaclab-h1-dribble-slalom
- Link: https://github.com/kingjameschan/isaaclab-h1-dribble-slalom
- Category: reinforcement learning / humanoid locomotion and manipulation / evaluation toolkit
- Robot Type: humanoid; Unitree H1 with 19 active joints
- Simulator: NVIDIA Isaac Lab 5.1.0 with RSL-RL PPO
- Deploy: simulation only; no real-robot deployment is demonstrated
- Summary: A GPU-parallel H1 task for keeping a football close, weaving around four collidable poles in alternating directions, and finishing with a shot on goal.
- Notes: The MIT-licensed single-release repository contains the environment, PPO configuration, geometry tests, evaluation and recording scripts, a final checkpoint, and evaluation JSON. It reports a 97.97% goal rate over 4,096 deterministic simulator episodes and documents a reward loophole discovered through video inspection; these figures apply only to the stated simulator distribution.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new primary-source lab or professor signal was verified today.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich Robotic Systems Lab — Rolling Research and Engineering Openings
- Type: PhD / PostDoc / research staff or software engineer / robot design engineer / embedded systems engineer / electronics engineer
- Location: Zurich, Switzerland
- Source: official website — https://rsl.ethz.ch/the-lab/open-positions.html
- Deadline: rolling / not specified on the official page
- Topics: legged robots / mobile manipulation / motion planning / model predictive control / reinforcement learning / perception / navigation / actuation / teleoperation / embedded systems
- Status: active at 2026-08-03 verification; previously tracked opportunity, not a new master-list addition
- Notes: The official page still exposes application links and lists continuous PhD and PostDoc recruitment plus research, software, robot-design, embedded, and electronics roles connected to legged robots and field deployment.

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / official offer no longer available
- Reason: The listed 2026-07-31 23:59 deadline has passed, and the official CNRS page now explicitly states, “The requested offer is no longer available.” Remove or mark the active master-list entry as expired after confirmation.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
