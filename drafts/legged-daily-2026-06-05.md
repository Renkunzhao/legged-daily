**English** | [中文](../zh/drafts/legged-daily-2026-06-05.md)
# Legged Daily - 2026-06-05

## Summary
- Today's strongest new paper signal is MPC-RL from Caltech / Johns Hopkins: it uses training-time centroidal MPC guidance and a batched GPU MPC solver to scale humanoid locomotion and manipulation RL.
- MotionDisco adds a complementary direction for humanoid loco-manipulation: LLM-guided evolutionary search plus kinodynamic optimization discovers long-horizon contact-rich skills without teleoperation or human-motion retargeting.
- M3imic / MultiModalWBC is both a paper and an implementation signal: it unifies joint trajectories, human-pose trajectories, and end-effector references for Unitree G1 whole-body control in Isaac Lab.
- Repository signals are useful but uneven: MultiModalWBC appears implementation-ready, while mpc-rl is an official paper repository whose README says code is still under preparation.
- Job checks found EPFL BioRob, ETH RSL, and Stanford/Karen Liu-linked wearable locomotion postdoc openings active; no verified stale removal is proposed today.

<details>
<summary><strong>New Papers</strong></summary>

### Accelerating and Scaling MPC-Guided Reinforcement Learning for Humanoid Locomotion and Manipulation
- Link: https://arxiv.org/abs/2606.05687
- Source: arXiv
- Date: 2026-06-04
- Authors: Junheng Li, Liang Wu, Sergio A. Esteban, Lizhi Yang, Ján Drgoňa, Aaron D. Ames
- Topics: humanoid / locomotion / loco-manipulation / MPC / reinforcement learning / batched GPU optimization
- Summary: Studies training-time MPC guidance for humanoid locomotion and manipulation RL, introducing a centroidal-dynamics MPC reward and $\pi^n$MPC, a construction-free batched GPU MPC solver designed to scale MPC guidance in massively parallel RL; the abstract reports comparative studies and hardware validations showing improved locomotion and manipulation performance.
- Notes: Official code link: https://github.com/junhengl/mpc-rl. Affiliations from the arXiv HTML are California Institute of Technology and Johns Hopkins University; repository README currently says code is under preparation.

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Source: arXiv
- Date: 2026-06-04
- Authors: Ilyass Taouil, Michal Ciebielski, Shafeef Omar, Haizhou Zhao, Angela Dai, Aaron M. Johnson, Majid Khadiv
- Topics: humanoid / loco-manipulation / motion discovery / LLM-guided search / kinodynamic optimization / reinforcement learning
- Summary: Presents MotionDisco, a framework that discovers contact-rich, long-horizon humanoid loco-manipulation motions from scratch by combining LLM-guided evolutionary search over interaction sequences with sequential kinodynamic trajectory optimization and pruning, then trains RL tracking policies to transfer discovered motions to a real humanoid robot.
- Notes: Supplementary video: https://youtu.be/DHiVz34QYlw. Affiliations listed in the arXiv HTML include Technical University of Munich, New York University, and Carnegie Mellon University. I did not verify a public code repository today.

### M3imic: Learning a Versatile Whole-Body Controller for Multimodal Motion Mimicking
- Link: https://arxiv.org/abs/2606.04829
- Source: arXiv / IEEE Robotics and Automation Letters
- Date: 2026-06-03
- Authors: Zuxing Lu, Ziang Zheng, Yao Lyu, Jingyu Liu, Feihong Zhang, Song Lu, Xin Yuan, Changyin Sun, Xingxing Zuo, Shengbo Eben Li
- Topics: humanoid / whole-body control / motion imitation / multimodal references / sim-to-real / Unitree G1
- Summary: Introduces Multi-Modal Mimic (M3imic), a whole-body control framework that maps heterogeneous motion references—robot joint angles, human pose trajectories, and end-effector poses—into a shared latent space so one policy can support locomotion and loco-manipulation references; the abstract reports Unitree G1 sim-to-real experiments and 98.42% peak simulation success on an unseen test set.
- Notes: Official code: https://github.com/Renforce-Dynamics/MultiModalWBC. arXiv HTML says the paper was accepted June 1, 2026; affiliations include Southeast University, Tsinghua University, and MBZUAI.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### MultiModalWBC
- Link: https://github.com/Renforce-Dynamics/MultiModalWBC
- Category: RL / control / imitation learning / whole-body control toolkit
- Robot Type: humanoid / general
- Simulator: Isaac Sim 4.5 / Isaac Lab 2.1.1
- Deploy: sim / hardware
- Summary: Official M3imic repository for multi-modal whole-body control, built on Isaac Lab and RSL-RL, with Unitree G1-focused environments and tasks for motion tracking, multi-motion training, and cross-modal imitation from robot joint trajectories, SMPL-X human body pose, and SE(3) keypoint trajectories.
- Notes: README states RA-L acceptance on 2026-06-03 and provides setup, dataset download, and training entrypoints; useful as a current implementation anchor for multimodal humanoid whole-body control.

### mpc-rl
- Link: https://github.com/junhengl/mpc-rl
- Category: MPC / RL / control
- Robot Type: humanoid
- Simulator: not yet specified in README
- Deploy: not yet specified; paper abstract reports hardware validations
- Summary: Official repository linked from the MPC-guided RL paper for humanoid locomotion and manipulation, targeting training-time MPC guidance and scalable batched MPC inside RL.
- Notes: Current README says “Code is under preparation and will be available very soon,” so this should be tracked as an official-but-not-yet-usable implementation signal rather than a ready toolkit.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Aaron D. Ames / Caltech AMBER Lab and collaborators
- Institution: California Institute of Technology; Johns Hopkins University collaborators
- Homepage: https://arxiv.org/abs/2606.05687
- GitHub: https://github.com/junhengl/mpc-rl
- Key Topics: humanoid / locomotion / manipulation / MPC / reinforcement learning / control
- Notes: MPC-RL is a high-signal bridge between model-predictive control and massively parallel RL for humanoid locomotion/manipulation. The arXiv HTML lists Caltech and Johns Hopkins affiliations and support from Technology Innovation Institute, Dow, Westwood Robotics, Johns Hopkins ROSEI, and DOE SciDAC.

### Majid Khadiv / Angela Dai / Aaron M. Johnson and MotionDisco author network
- Institution: Technical University of Munich; New York University; Carnegie Mellon University
- Homepage: https://arxiv.org/abs/2606.06139
- YouTube: https://youtu.be/DHiVz34QYlw
- Key Topics: humanoid / loco-manipulation / motion planning / LLM-guided search / trajectory optimization / real-robot deployment
- Notes: MotionDisco is worth tracking as a source-network signal around automated discovery of contact-rich humanoid skills without teleoperation or human-motion retargeting.

### Tsinghua / Southeast University / MBZUAI M3imic author network
- Institution: Southeast University; Tsinghua University; Mohamed Bin Zayed University of Artificial Intelligence
- Homepage: https://arxiv.org/abs/2606.04829
- GitHub: https://github.com/Renforce-Dynamics/MultiModalWBC
- Key Topics: humanoid / Unitree G1 / whole-body control / multimodal imitation / Isaac Lab / sim-to-real
- Notes: M3imic / MultiModalWBC gives a concrete source to track around multimodal whole-body control policies and reusable Isaac Lab infrastructure for Unitree G1.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: Official BioRob openings page still lists one Postdoc and one PhD student position for investigating and leveraging human locomotion neuromechanics using humanoid robots, combining neuromechanical simulation, bio-inspired controllers, and reinforcement learning.

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: Official RSL page continues to list rolling PhD, postdoc, research staff/software engineer, and robot-design openings connected to legged robots, control, learning, planning, field deployment, and mobile manipulation.

### Stanford Biomechatronics Laboratory / Karen Liu, Steve Collins, Scott Delp, Leo Guibas
- Type: Postdoc
- Location: Stanford, CA, USA
- Source: official lab page
- Deadline: unknown
- Topics: lower-limb exoskeletons / human locomotion / balance control / human-in-the-loop optimization / optimal control / reinforcement learning
- Status: active
- Notes: Official page lists two postdoctoral positions, including a lower-limb exoskeleton experimentalist and a gait modeling / exoskeleton control role. This is adjacent to legged robotics rather than a humanoid/quadruped opening, but relevant through human locomotion, balance control, exoskeleton hardware, optimal control, and RL.

</details>
