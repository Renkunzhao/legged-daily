**English** | [中文](../zh/drafts/legged-daily-2026-05-24.md)
# Legged Daily - 2026-05-24

## Summary
- The strongest paper signal today is PRIME, an RSS 2026 work on physically consistent inertial and motion estimation for legged and humanoid robots, evaluated on quadrupeds and Unitree G1.
- MUJICA adds a unified proprioceptive multi-skill controller for wheeled-legged robots, combining omnidirectional motion, high-platform climbing, and fall recovery on Unitree Go2-W.
- X2-N is a hardware-and-control signal for transformable wheel-legged humanoids, combining humanoid mode, wheel-legged mode, transformation, and manipulation under one RL-based whole-body control framework.
- DreamWaQ++ is a T-RO 2026 quadruped locomotion project with multimodal RL, reporting robust stair, slope, obstacle, payload, and multi-platform results.
- Repository signals are practical but lower-confidence than the paper signals: `g1_locomotion` provides a Unitree G1 MPC/WBID simulation stack, while `awesome-unitree-humanoid-papers` is a useful curated watchlist rather than a research codebase.
- Job signals remain active from official pages: ETH RSL lists rolling PhD/PostDoc/research-engineering roles, and NC State HIER Lab expects 2027 PhD/PostDoc openings in humanoid whole-body control.

## New Papers
- [PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots](https://arxiv.org/abs/2605.17681)
  Source: arXiv / RSS 2026
  Importance: high
  Summary: PRIME formulates motion estimation as a MAP optimization that refines kinematics and actuator commands into dynamically consistent trajectories while estimating contact forces and inertial parameters; it is evaluated on quadrupeds and Unitree G1 and is notable because force/contact-annotated reconstructions could improve feedback control and downstream robot-learning datasets.

- [MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots](https://arxiv.org/abs/2605.13058)
  Source: arXiv
  Importance: medium
  Summary: MUJICA trains a single fully proprioceptive policy with skill indicators for omnidirectional moving, high-platform climbing, and fall recovery, plus a high-level skill selector; real-world Unitree Go2-W experiments make it relevant for robust wheeled-legged sim-to-real control.

- [X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation](https://arxiv.org/abs/2604.21541)
  Source: arXiv
  Importance: medium
  Summary: X2-N presents a high-DoF robot that can switch between humanoid and wheel-legged forms, with an RL-based whole-body controller for hybrid locomotion, transformation, stair climbing, skating-like motion, package delivery, and manipulation.

## New Repos
- [g1_locomotion](https://github.com/ioloizou/g1_locomotion)
  Topic: humanoid / Unitree G1 / MPC / whole-body inverse dynamics / MuJoCo / ROS
  Importance: medium
  Summary: A Unitree G1 locomotion stack combining Single Rigid Body Dynamics and Whole-Body Inverse Dynamics in a cascaded linear control pipeline; the README reports MuJoCo straight-line walking support but explicitly notes that it has not yet been tested on the physical robot.

- [awesome-unitree-humanoid-papers](https://github.com/eai2-repos/awesome-unitree-humanoid-papers)
  Topic: curated list / Unitree humanoids / G1 / H1 / locomotion / manipulation / foundation models
  Importance: low
  Summary: A curated list of Unitree humanoid papers and projects covering G1/H1/H1-2 work from 2025-2026; useful as a source-discovery watchlist, but it is not itself a research implementation repository.

## Lab / Professor Signals
- Name / Lab: Jiarong Kang, Kunzhao Ren, Tao Pang, Xiaobin Xiong / PRIME author network
  Source: arXiv / RSS 2026
  Update: PRIME is a high-signal contact-dynamics and motion-estimation work for legged and humanoid robots; track the authors for future releases related to physically consistent data reconstruction and robot foundation-model datasets.

- Name / Lab: DreamWaQ++ team / KAIST + KRAFTON + URobotics + MIT
  Source: project page / IEEE Transactions on Robotics 2026
  Update: DreamWaQ++ reports resilient multimodal RL for quadruped locomotion, including 97.8% success on challenging stairs, 35° slope climbing, 4 robot platforms, and 50 Hz real-time control.

- Name / Lab: HIER Lab / NC State University
  Source: official lab homepage
  Update: The lab lists humanoid and animaloid robotics, autonomous loco-manipulation, whole-body control, teleoperation, safety-critical control, and generative AI for motion as active directions; the page also reports 2026 student paper submissions and NVIDIA Academic Award support for humanoid research.

## Job Signals
- Institution / Company / Lab / Team: ETH Zurich Robotic Systems Lab
  Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
  Source: official RSL open positions page
  Deadline: rolling / unknown
  Summary: RSL lists rolling openings connected to legged robots, mobile manipulators, large-scale field robots, motion planning, MPC, reinforcement learning, perception, navigation, actuation, teleoperation, and ROS/C++ systems work.

- Institution / Company / Lab / Team: HIER Lab / NC State University
  Type: PhD / Postdoc
  Source: official lab homepage
  Deadline: 2027 cycle / official admissions required
  Summary: HIER Lab expects openings for 2027 PhD students and postdocs in hierarchical RL-based whole-body control and tele whole-body control of humanoids, with an interest form plus official graduate admissions requirement.
