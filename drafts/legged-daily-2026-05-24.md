**English** | [中文](../zh/drafts/legged-daily-2026-05-24.md)
# Legged Daily - 2026-05-24

## Summary
- PRIME is today's strongest paper signal: an RSS 2026 method for physically consistent inertial and motion estimation on legged and humanoid robots.
- MUJICA contributes a unified proprioceptive multi-skill controller for wheeled-legged robots, with real Unitree Go2-W experiments.
- X2-N is a hardware-and-control signal for transformable wheel-legged humanoids, connecting dual-mode locomotion, transformation, and manipulation.
- DreamWaQ++ remains a strong quadruped locomotion source-network signal around multimodal RL, stairs, slopes, obstacle robustness, payloads, and multi-platform transfer.
- Practical repository signals today are `g1_locomotion` for Unitree G1 MPC/WBID simulation and `awesome-unitree-humanoid-papers` as a Unitree humanoid literature watchlist.
- Official job signals remain active or watchlisted at ETH RSL and NC State HIER Lab.

<details>
<summary><strong>New Papers</strong></summary>

### PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots
- Link: https://arxiv.org/abs/2605.17681
- Source: arXiv / RSS 2026
- Date: 2026-05-22
- Authors: Jiarong Kang, Kunzhao Ren, Linxuan Wang, Jingbo Wang, Tao Pang, Xiaobin Xiong
- Topics: legged robots / humanoid robots / state estimation / motion estimation / contact dynamics / inertial parameters
- Summary: MAP-based motion-estimation method that refines kinematics and actuator commands into dynamically consistent trajectories while estimating contact forces and inertial parameters for legged and humanoid robots.
- Notes: Evaluated on quadrupeds and Unitree G1; useful to track for physically consistent robot-data reconstruction and force/contact annotation.

### MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots
- Link: https://arxiv.org/abs/2605.13058
- Source: arXiv
- Date: 2026-05-17
- Authors: Wanming Yu, Xinshuo Yang, Wenxuan Wei, ZhuoJia Huang, Junzheng Wang
- Topics: wheeled-legged robots / reinforcement learning / proprioceptive control / sim-to-real / fall recovery
- Summary: Unified controller that trains one fully proprioceptive policy with skill indicators for omnidirectional movement, high-platform climbing, and fall recovery, plus a high-level skill selector.
- Notes: Real-world Unitree Go2-W experiments make it relevant for robust wheeled-legged deployment.

### X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation
- Link: https://arxiv.org/abs/2604.21541
- Source: arXiv
- Date: 2026-04-28
- Authors: Shengjie Wang, Hui Zhang, Zixuan Wu, Wenhao Yu, Guifeng Yuan, Guohui Tian, Wenhao Zhang, Junyao Gao, Weijia Liu, Zhennan Tang, Jing Peng, Weixia Liu, Wensheng Zhang, Qiang Huang
- Topics: humanoid / wheeled-legged robot / transformable robot / whole-body control / reinforcement learning / manipulation
- Summary: Transformable high-DoF robot that switches between humanoid and wheel-legged modes, with an RL-based whole-body controller for hybrid locomotion, transformation, stair climbing, skating-like motion, package delivery, and manipulation.
- Notes: Useful hardware-system signal for dual-mode humanoid mobility and manipulation.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### g1_locomotion
- Link: https://github.com/ioloizou/g1_locomotion
- Category: control / MPC
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: Unitree G1 locomotion stack combining Single Rigid Body Dynamics and Whole-Body Inverse Dynamics in a cascaded linear control pipeline.
- Notes: README reports MuJoCo straight-line walking support and states that physical-robot testing has not yet been performed.

### awesome-unitree-humanoid-papers
- Link: https://github.com/eai2-repos/awesome-unitree-humanoid-papers
- Category: toolkit
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Curated list of Unitree humanoid papers and projects covering G1, H1, and H1-2 work from 2025-2026.
- Notes: Best treated as a source-discovery watchlist rather than a research implementation repository.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Jiarong Kang, Kunzhao Ren, Tao Pang, Xiaobin Xiong / PRIME author network
- Institution: mixed author network; verify individual affiliations before adding to master list
- arXiv: https://arxiv.org/abs/2605.17681
- Key Topics: legged robots / humanoid robots / motion estimation / contact dynamics / inertial parameter estimation
- Notes: PRIME is a high-signal contact-dynamics and motion-estimation work for legged and humanoid robots; track for future code, data, and physically consistent reconstruction releases.

### DreamWaQ++ team
- Institution: KAIST / KRAFTON / URobotics / MIT
- Homepage: https://kaist-dmlab.github.io/DreamWaQ-Plus-Plus-Site/
- Key Topics: quadruped / locomotion / reinforcement learning / multimodal perception / terrain adaptation / sim-to-real
- Notes: DreamWaQ++ reports resilient multimodal RL for quadruped locomotion, including challenging stairs, slope climbing, obstacle traversal, payload robustness, multi-platform results, and 50 Hz real-time control.

### HIER Lab / NC State University
- Institution: North Carolina State University
- Homepage: https://hierlab.github.io/
- Lab / Department: HIER Lab
- Key Topics: humanoid / animaloid legged robots / loco-manipulation / whole-body control / teleoperation / safety-critical control / generative AI for motion
- Notes: Active source for humanoid and animaloid robot intelligence; the lab page reports 2026 student paper submissions and NVIDIA Academic Award support for humanoid research.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / field robots / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: RSL lists rolling openings connected to legged and field robotics, including research and engineering roles.

### HIER Lab / NC State University
- Type: PhD / Postdoc
- Location: Raleigh, NC, USA
- Source: official lab page
- Deadline: 2027 cycle / official admissions required
- Topics: humanoid / whole-body control / hierarchical reinforcement learning / teleoperation / loco-manipulation
- Status: watching
- Notes: Lab page expects 2027 PhD and postdoc openings in hierarchical RL-based whole-body control and humanoid tele whole-body control; official graduate admissions are still required.

</details>
