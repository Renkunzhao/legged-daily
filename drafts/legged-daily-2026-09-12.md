**English** | [中文](../zh/drafts/legged-daily-2026-09-12.md)
# Legged Daily - 2026-09-12

## Summary
- Georgia Tech's granular-terrain work combines a physics-grounded 3D resistive-force contact model with teacher-student RL, then demonstrates Unitree G1 running on basalt, dry sand, and beach sand.
- SwingBot expands humanoid mobility beyond ground locomotion: keyframe-guided exploration and a recurrent privileged-state estimator enable continuous real-robot brachiation with passive wrist hooks.
- ViBe post-trains existing humanoid motion trackers for vision-conditioned whole-body control using pretrained visual encoders and low-rank adapters, with zero-shot sim-to-real demonstrations across locomotion and loco-manipulation tasks.
- Fresh repository signals include a hardware-facing VITA humanoid Python SDK, a full simulated ROBOTIS OP3 companion stack with an RL walking policy, and a new curated index for perceptive humanoid locomotion.
- No sufficiently specific, verifiably active new legged-robotics job opening was selected from the official sources checked today.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Terrain-Adaptive Humanoid Locomotion on Granular Terrain
- Link: https://arxiv.org/abs/2609.10286
- Source: arXiv
- Date: 2026-09-09
- Authors: Junnosuke Kamohara, Feiyang Wu, Andy Ningan Zong, Daniel I. Goldman, Yashwanth Nakka, Seth Hutchinson, Ye Zhao
- Topics: humanoid locomotion / granular terrain / contact modeling / reinforcement learning / sim-to-real
- Summary: Integrates a physics-grounded three-dimensional resistive-force-theory contact model into RL training and distills a terrain-conditioned teacher into a proprioceptive student that estimates terrain properties online for locomotion across deformable ground.
- Notes: [Project page](https://humanoid-gm-locomotion.github.io/HUMANOID-GM/). The authors report Unitree G1 hardware trials on basalt, dry sand, and beach sand, plus terrain transitions; code is marked coming soon, and the performance claims were not independently reproduced in this run.

### SwingBot: Learning Whole-Body Brachiation for Humanoid Robots
- Link: https://arxiv.org/abs/2609.10283
- Source: arXiv / CoRL 2026
- Date: 2026-09-09
- Authors: Yujie Xiong, Peng Zhai, Taixian Hou, Quancheng Qian, Cunwang Liu, Kangmai Hu, Long Yang, Zhiyan Dong, Lihua Zhang
- Topics: humanoid locomotion / brachiation / whole-body control / reinforcement learning / contact transitions
- Summary: Uses biomimetic keyframes to scaffold sparse release-swing-capture exploration and a recurrent privileged-information model to estimate position and hook-contact latents for continuous humanoid brachiation.
- Notes: [Project page](https://ttbray.github.io/SwingBot/). Hardware experiments report continuous overhead traversal and robustness to payload, disturbances, and changing bar spacing using passive wrist hooks; this complements walking when ground routes are blocked.

### ViBe: Visual Behavior Adaptation for Perceptive Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2609.09918
- Source: arXiv
- Date: 2026-09-09
- Authors: Lokesh Krishna, Sarvesh Venkatesan, An Zhang, Quan Nguyen
- Topics: perceptive humanoid control / motion tracking / visual adaptation / parameter-efficient fine-tuning / loco-manipulation
- Summary: Adapts existing humanoid motion trackers to perceptive tasks by extracting task-relevant feedback from pretrained visual encoders and grafting it into the policy through low-rank adapters for direct post-training with policy optimization.
- Notes: [Project page](https://lok-i.github.io/vibe-control/). The authors report zero-shot sim-to-real results for curb walking, parkour, cube reorientation, omni-object loco-manipulation, and dodgeball under outdoor, low-light, and visual-distractor conditions; code is not yet linked from the paper or project page.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### VitaDynamics/humanoid-sdk
- Link: https://github.com/VitaDynamics/humanoid-sdk
- Category: hardware SDK / control interface / examples
- Robot Type: humanoid / VITA
- Simulator: none documented
- Deploy: hardware-facing Linux client; hardware acceptance not independently verified
- Summary: Provides a Python SDK and examples for connecting an external Linux computer to VITA humanoid robots through the Aorta messaging stack, including read-only state subscription and an explicitly gated whole-body control example.
- Notes: Created 2026-09-10 and updated 2026-09-12. The README documents Linux x86_64/aarch64 compatibility, offline bundle checks, peer-profile requirements, and motion-safety gates, but the repository had one star, no GitHub-detected license, and no latest GitHub release at check time; deployment depends on vendor-provided matching bundles and credentials.

### YauhenBichel/humanoid-companion
- Link: https://github.com/YauhenBichel/humanoid-companion
- Category: RL locomotion / humanoid interaction / simulation stack
- Robot Type: humanoid / ROBOTIS OP3
- Simulator: MuJoCo / MuJoCo Playground (MJX)
- Deploy: simulation; real-hardware adapter remains roadmap work
- Summary: Combines a bundled PPO walking policy, 50 Hz safety-checked control loop, gestures, browser-rendered face, speech, and a locally hosted LLM interface into an end-to-end simulated small-humanoid companion system.
- Notes: Created 2026-09-11 and updated 2026-09-12 under Apache-2.0. The repository includes training, evaluation, export, policy parity tests, and domain randomization, but current demonstrations use a simulated OP3; `DynamixelRobotIO` and real-robot walking are explicitly future work.

### yhx1203/awesome-perceptive-humanoid-locomotion
- Link: https://github.com/yhx1203/awesome-perceptive-humanoid-locomotion
- Category: paper and code index
- Robot Type: humanoid
- Simulator: not applicable
- Deploy: literature/resource index
- Summary: Curates papers, project pages, and available code for perceptive humanoid locomotion, spanning visual parkour, terrain reconstruction, active gaze, tactile sensing, world-model-based control, and perception-degraded locomotion.
- Notes: Created 2026-09-11 with two stars at check time. It is a small, manually curated reading list rather than runnable software, currently organized as a single perceptive-locomotion table and without a detected repository license.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Georgia Tech granular-terrain locomotion collaboration
- Institution: Georgia Institute of Technology / Northeastern University
- Homepage: https://humanoid-gm-locomotion.github.io/HUMANOID-GM/
- Lab / Department: Institute for Robotics and Intelligent Machines / Georgia Tech School of Physics
- Key Topics: humanoid locomotion / granular media / terradynamics / reinforcement learning / sim-to-real
- Notes: Junnosuke Kamohara, Feiyang Wu, Andy Ningan Zong, Daniel I. Goldman, Yashwanth Nakka, Seth Hutchinson, and Ye Zhao connect legged control with granular-contact physics in a Unitree G1 hardware study. This is a useful cross-lab signal for outdoor locomotion where rigid-ground simulators are insufficient.

### Fudan University SwingBot team
- Institution: Fudan University
- Homepage: https://ttbray.github.io/SwingBot/
- Lab / Department: College of Intelligent Robotics and Advanced Manufacturing
- Key Topics: humanoid whole-body control / brachiation / reinforcement learning / contact-rich locomotion
- Notes: The SwingBot team demonstrates a high-DoF humanoid using passive wrist hooks for continuous overhead locomotion. The work is a notable signal that the group's locomotion scope includes aerial contact transitions and whole-body momentum control, not only foot-ground walking.

### USC perceptive whole-body control team
- Institution: University of Southern California
- Homepage: https://lok-i.github.io/vibe-control/
- Key Topics: perceptive humanoid control / motion tracking / visual representation learning / loco-manipulation
- Notes: Lokesh Krishna, Sarvesh Venkatesan, An Zhang, and Quan Nguyen released ViBe as a modular visual post-training route for existing humanoid trackers. The project joins perceptive locomotion and object-centric whole-body tasks through a common parameter-efficient adaptation mechanism.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently specific, currently actionable new legged-robotics opening was selected today from the official careers sources checked. A current NVIDIA “Research Scientist, Robotics Research — PhD New College Grad 2026” page was visible, but the accessible official page exposed only the title and not enough role detail to verify a direct legged-robotics fit, location, or application status, so it was omitted rather than inferred. No stale-item removal is proposed today.

</details>
