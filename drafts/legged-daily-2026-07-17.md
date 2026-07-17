**English** | [中文](../zh/drafts/legged-daily-2026-07-17.md)
# Legged Daily - 2026-07-17

## Summary
- ScaleBFM presents a scaling recipe for humanoid Behavior Foundation Models that coordinates global-frame motion tracking, on-policy rollout scale, reference-motion diversity, and a Humanoid Transformer, with simulation and real-hardware validation.
- VOP-Nav combines Velocity Obstacle geometry with end-to-end reinforcement learning for agile quadruped navigation through dense dynamic crowds using only local multi-frame LiDAR observations.
- Acc-CBF-QP adds an open-source acceleration-level CBF-QP runtime safety filter to existing RL policies; on Unitree H1 hardware it reduced reported constraint violations by 92% without retraining the policy.
- One repository met today's selection bar: the new Acc-CBF-QP superbuild provides a documented Ubuntu 24.04 installation path and a ready-to-run Unitree H1 MuJoCo example. ScaleBFM's official repository is tracked as a release preview rather than selected because most code is still scheduled for release by July 26.
- Georgia Tech's LIDAR lab announced IEEE RA-L acceptance of REFINE-DP, which jointly fine-tunes a diffusion planner and low-level RL controller for humanoid loco-manipulation; the LAAS-CNRS humanoid safe-RL PhD remains active through July 31.

<details>
<summary><strong>New Papers</strong></summary>

### Scaling Behavior Foundation Model for Humanoid Robots
- Link: https://arxiv.org/abs/2607.15163
- Source: arXiv
- Date: 2026-07-16
- Authors: Weishuai Zeng, Kangning Yin, Xiaojie Niu, Shunlin Lu, Weixiang Zhong, Jiahe Chen, Feiyu Jia, Xiao Chen, Zirui Wang, Furui Xu, Ming Zhou, Kailin Li, Weinan Zhang, He Wang, Li Yi, Dahua Lin, Jiangmiao Pang, Jingbo Wang
- Topics: humanoid / behavior foundation model / motion tracking / reinforcement learning / Transformer / scaling
- Summary: ScaleBFM coordinates global-frame whole-body motion tracking, balanced scaling of on-policy rollout width and depth, heterogeneous reference-motion diversity, and a scalable Humanoid Transformer to improve reusable humanoid behavior learning and generalization in simulation and on hardware.
- Notes: The project aggregates more than 102 million human-motion frames at 50 FPS and reports test-set MPKPE reductions of over 10% in local mode and 82% in global mode relative to existing humanoid controllers. Project page: https://scalebfm.github.io/. The official repository currently contains a staged-release notice and expects most retargeting, training, and deployment code by 2026-07-26, so it is not counted as a mature repository today: https://github.com/zengweishuai/ScaleBFM.

### Learning Agile Navigation in Crowded Environments for Quadruped Robots
- Link: https://arxiv.org/abs/2607.15036
- Source: arXiv
- Date: 2026-07-16
- Authors: Shuyu Wu, Zeyu Liu, Tianbao Zhang, Fanxing Li, Fangyu Sun, Mingkang Xiong, Wei Xi, Wenxian Yu, Danping Zou
- Topics: quadruped / crowded navigation / reinforcement learning / Velocity Obstacles / LiDAR / sim-to-real
- Summary: VOP-Nav uses multi-frame local LiDAR to predict a Velocity-Obstacle-derived safe velocity region, feeding that prediction to an end-to-end navigation policy at inference time and using it as a training reward, without explicit human detection, tracking, or global mapping.
- Notes: Evaluated in Isaac Gym and deployed on a Unitree Go2 in indoor and outdoor dynamic crowds. No official code repository was found during today's verification.

### Safe Execution of RL Policies Via Acceleration-Based CBF-QP Constraint Enforcement for Real-World Robotic Deployments
- Link: https://arxiv.org/abs/2607.14488
- Source: IROS 2026 / arXiv
- Date: 2026-07-16
- Authors: Bastien Muraccioli, Alice Cariou, Pierre-Alexandre Leziart, Mathieu Celerier, Arnaud Demont, Gentiane Venture, Mehdi Benallegue
- Topics: humanoid / safe reinforcement learning / control barrier function / quadratic programming / runtime safety / whole-body control
- Summary: Acc-CBF-QP filters an existing RL policy at acceleration level without modifying training, enforcing joint-position, velocity, torque, and collision constraints while regulating deviation from the original policy through torque- or forward-dynamics-based QP tasks.
- Notes: Accepted to IROS 2026 and validated in simulation and hardware on a 19-DoF Unitree H1 and 7-DoF Kinova Gen3. The project reports reducing H1 hardware violations from 10.04 to 0.80 per second, a 92% reduction. Project page: https://safe-rl-qp.github.io/.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### safe-rl-qp-mc-rtc-superbuild
- Link: https://github.com/safe-rl-qp/safe-rl-qp-mc-rtc-superbuild
- Category: control / RL / toolkit
- Robot Type: humanoid / general
- Simulator: MuJoCo / mc_rtc
- Deploy: both
- Summary: A CMake superbuild that installs the Acc-CBF-QP framework and dependencies and provides a ready-to-run Unitree H1 walking-policy example for MuJoCo, with a path toward hardware execution and custom RL-QP controllers.
- Notes: Created on 2026-06-28 and updated on 2026-07-17; documented for Ubuntu 24.04. It links the archived paper implementation and experiment logs at https://github.com/safe-rl-qp/mc-safe-rl-qp, plus a controller template and community examples. This is the recommended starting point for reproducing the open-source IROS 2026 system.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Mehdi Benallegue / CNRS-AIST Joint Robotics Laboratory
- Institution: CNRS / AIST, Japan
- Homepage: https://jrl-umi3218.github.io/
- GitHub: https://github.com/safe-rl-qp
- Lab / Department: CNRS-AIST JRL, IRL3218
- Key Topics: humanoid / safe reinforcement learning / whole-body control / CBF-QP / task and motion planning
- Notes: The IROS 2026 Acc-CBF-QP release adds a complete open-source safety-filter ecosystem around mc_rtc, with hardware validation on Unitree H1 and Kinova Gen3. The same line directly grounds a newly advertised LAAS/JRL PhD on coupling high-level RL decisions with online MPC.
- Students and Representative Works:
  - [Alice Cariou](https://safe-rl-qp.github.io/) — [Safe Execution of RL Policies Via Acceleration-Based CBF-QP Constraint Enforcement](https://safe-rl-qp.github.io/)

### Ye Zhao / Laboratory for Intelligent Decision and Autonomous Robots
- Institution: Georgia Institute of Technology
- Homepage: https://lab-idar.gatech.edu/
- Lab / Department: Institute for Robotics and Intelligent Machines / George W. Woodruff School of Mechanical Engineering
- Key Topics: humanoid / loco-manipulation / reinforcement learning / diffusion policy / whole-body control
- Notes: The lab's July 2026 news announces IEEE RA-L acceptance of REFINE-DP. The method jointly fine-tunes a diffusion high-level planner and an RL low-level controller; its project page reports over 90% simulation success, real-world Booster T1 demonstrations, and 95-97% success from 50 demonstrations versus roughly 1,000 trajectories when training from scratch.
- Students and Representative Works:
  - [Zhaoyuan Gu](https://scholar.google.com/citations?user=IC9VJpsAAAAJ&hl=en) — [REFINE-DP](https://refine-dp.github.io/REFINE-DP/)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto Team — PhD in Humanoid Robotics: Safe Reinforcement Learning
- Type: PhD
- Location: Toulouse, France, with part of the project at CNRS-AIST JRL in Tsukuba, Japan
- Source: official website — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59
- Topics: humanoid / legged locomotion / reinforcement learning / MPC / whole-body control / safe control
- Status: active
- Notes: Rechecked on 2026-07-17. This is a 36-month, full-time PhD starting 2026-10-01 with listed remuneration of EUR 2,300 gross per month. The project combines learned discrete contact, footstep, gait, or behavior decisions with online MPC and plans hardware validation on PAL Robotics Kangaroo and/or Unitree H1/R1 platforms under Olivier Stasse and Mehdi Benallegue.

</details>
