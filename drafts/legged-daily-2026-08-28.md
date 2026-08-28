**English** | [中文](../zh/drafts/legged-daily-2026-08-28.md)
# Legged Daily - 2026-08-28

## Summary
- `SOLO` targets accumulated perception-control errors in long-horizon humanoid locomotion and reports a zero-shot 1.5 km outdoor deployment using one chest depth camera and proprioception.
- `LAC` learns commanded linear and angular whole-body compliance for upper-body wrenches, including real-robot teleoperated loco-manipulation demonstrations.
- `RAEM` combines local tomographic/3D traversability maps with an elevation-aware global topological graph, demonstrating continuous quadruped exploration of a five-floor stairwell.
- Three new code releases are worth inspection: a measured classical/RL Unitree H1-2 balance stack, guarded multi-policy switching for G1 in MuJoCo, and a safety-disabled-by-default ROS 2 navigation workspace for Go2W.
- A verified Inria Bordeaux / LAAS-CNRS PhD on compliant whole-body quadruped co-design closes on 2026-08-31; the official page lists a 2026-10-01 start and EUR 2,300 monthly gross pay.

<details>
<summary><strong>New Papers</strong></summary>

### SOLO: Stable Omni-terrain Long-Horizon Perceptive Humanoid Locomotion
- Link: [arXiv](https://arxiv.org/abs/2608.26583) · [Project](https://sunpihai-up.github.io/solo/)
- Source: arXiv
- Date: 2026-08-27
- Authors: Pihai Sun, Gang Han, Jingkai Sun, Jiahao Ma, Zeran Su, Zelin Tao, Peiran Liu, Shuai Shi, Wei Cui, Zifan Wang, Jialin Yu, Wen Zhao, Kangning Yin, Jiaxu Wang, Jiahang Cao, Lingfeng Zhang, Hao Cheng, Jian Tang, Yijie Guo, Qiang Zhang
- Topics: humanoid / perceptive locomotion / long-horizon deployment / terrain reconstruction / teacher-student reinforcement learning
- Summary: Combines query-based reconstruction of action-critical terrain geometry with trajectory-aware distillation that propagates future teacher-student disagreement into the PPO objective.
- Notes: The paper reports 97.5% mean success on stress-test terrains and 96% stepping-stone success. The policy was deployed zero-shot at 50 Hz using one chest depth camera and proprioception, completing a continuous 1.5 km outdoor route without external mapping or state systems. No public code release was verified today.

### LAC: Linear and Angular Compliance for Humanoid Whole-body Control
- Link: [arXiv](https://arxiv.org/abs/2608.25405) · [Project](https://lac-humanoid.github.io/)
- Source: arXiv
- Date: 2026-08-26
- Authors: Yang Liu, Zhongkai Gu, Wei Zhu, Mitsuhiro Hayashibe
- Topics: humanoid / whole-body control / linear compliance / angular compliance / reinforcement learning / loco-manipulation
- Summary: Trains one teacher-student policy to realize commanded linear and angular whole-body compliance under upper-body external wrenches rather than treating all interaction forces as disturbances.
- Notes: The method synthesizes compliant whole-body responses from contact frames in human-interaction data, then trains at scale in Isaac Lab. The paper reports monotonic stiffness modulation, real-world wrench-response experiments, and teleoperated loco-manipulation demonstrations. No public code release was verified today.

### RAEM: Robust Autonomous Exploration for Multi-Floor Environments with a Quadruped Robot
- Link: https://arxiv.org/abs/2608.25366
- Source: arXiv
- Date: 2026-08-26
- Authors: Zikang Yuan, Yuan Ren, Yian Wang, Yixue Wang, Enze Fang, Xuewei Zhang, Junda Cheng, Chi Chen, Chin-Pang Ho, Lijun Zhu, Shaohang Xu, Kwang-Ting Cheng, Xin Yang
- Topics: quadruped / autonomous exploration / multi-floor navigation / traversability mapping / topological planning / stair climbing
- Summary: Uses local tomographic and categorized 3D traversability maps for terrain analysis while incrementally building an elevation-aware global topological graph for efficient cross-floor exploration.
- Notes: A staircase center-alignment strategy reduces abrupt yaw changes, while dual path search recovers guidance when local topology becomes disconnected. Simulation and real-world results include continuous autonomous exploration of a five-floor stairwell. No official project page or code release was verified today.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### FERBIN12/humanoid-balance-locomotion
- Link: https://github.com/FERBIN12/humanoid-balance-locomotion
- Category: control / reinforcement learning / toolkit
- Robot Type: humanoid — Unitree H1-2
- Simulator: MuJoCo / Gazebo with ROS 2
- Deploy: simulation / sim-to-sim
- Summary: Builds a measured torque-control stack from CoM/CoP estimation through ankle, upper-body momentum, stepping, LIPM walking, whole-body QP, and an RL-policy comparison for a 51-actuator H1-2 model.
- Notes: Created 2026-08-26 under MIT. The repository contains 90 Python modules, recorded traces, disturbance tests, terrain failure cases, and a 400 Hz ROS 2 effort-control port. Its README reports 12.9 m in 30 s for the bundled pretrained RL-policy comparison; all demonstrated results remain simulation-only.

### Nikerane/g1-switchstep
- Link: https://github.com/Nikerane/g1-switchstep
- Category: control / policy integration / toolkit
- Robot Type: humanoid — Unitree G1 29-DoF
- Simulator: MuJoCo
- Deploy: simulation
- Summary: Implements guarded switching between pretrained G1 locomotion and spin-kick ONNX policies using one exclusive command owner, measured-state transitions, terminal stability checks, blending, and passive damping on faults.
- Notes: Created 2026-08-28. The repository includes tensor/timing/hash contracts, deterministic tests, execution metrics, and a public demo, but excludes policy binaries and requires users to obtain pinned upstream artifacts. The maintainer explicitly states that this is cross-simulator evidence, not hardware-safety validation; no repository-level license was detected by GitHub today.

### zhuaoyuRobo/Go2W-navigate-project
- Link: https://github.com/zhuaoyuRobo/Go2W-navigate-project
- Category: navigation / perception / systems integration
- Robot Type: quadruped / wheel-legged — Unitree Go2W-class platform
- Simulator: ROS 2 integrations with external simulator or sensor source
- Deploy: both, with public hardware output disabled by default
- Summary: Publishes a ROS 2 Humble workspace integrating FAST-LIO, point-cloud localization, Nav2, robot description, command limiting, and an optional learned locomotion-controller interface.
- Notes: Created 2026-08-27 and Apache-2.0 for the integration package, with vendored components retaining separate licenses. Maps, calibrated parameters, policy weights, vendor SDKs, and real-robot launch files are intentionally excluded; public action scale defaults to zero and the Go2W bridge stays disabled until locally enabled and calibrated.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### X-Humanoid / Beijing Humanoid Robot Innovation Center
- Institution: Beijing Humanoid Robot Innovation Center
- Homepage: https://sunpihai-up.github.io/solo/
- arXiv: https://arxiv.org/abs/2608.26583
- Lab / Department: X-Humanoid
- Key Topics: humanoid / perceptive locomotion / long-horizon deployment / rough terrain / teacher-student reinforcement learning
- Notes: X-Humanoid is the recurring primary affiliation across the new SOLO author team. The project reports zero-shot 1.5 km perceptive locomotion and says related technology powered Tiangong Omni competition and public terrain demonstrations, making the group a high-priority source for long-horizon humanoid mobility.

### Mitsuhiro Hayashibe / Neuro-Robotics Laboratory
- Institution: Tohoku University
- Homepage: https://lac-humanoid.github.io/
- arXiv: https://arxiv.org/abs/2608.25405
- Lab / Department: Neuro-Robotics Laboratory
- Key Topics: humanoid / whole-body compliance / physical interaction / reinforcement learning / teleoperated loco-manipulation
- Notes: The LAC paper identifies all authors with Tohoku University's Neuro-Robotics Laboratory and adds real-robot evidence for commandable linear and angular compliance across upper-body contacts. This is a useful source signal for contact-rich humanoid interaction beyond disturbance rejection.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- Type: PhD
- Location: Talence / Bordeaux, France, with planned visits to Toulouse
- Source: [official Inria posting](https://jobs.inria.fr/public/classic/en/offres/2026-10319)
- Deadline: 2026-08-31; planned start 2026-10-01
- Topics: quadruped / mechatronic co-design / local compliance / loco-manipulation / reinforcement learning / real-to-sim calibration / prototyping
- Status: active — closing soon
- Notes: The project jointly studies mechanical architecture, actuation, compliance distribution, and control policy for a new whole-body quadruped, with experimental targets including outdoor high-speed galloping and flying-object catching. The official posting requests mechanical design, prototyping, robot modeling/control, and C++ or Python; listed remuneration is EUR 2,300 per month before tax.

</details>
