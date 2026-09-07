**English** | [中文](../zh/drafts/legged-daily-2026-09-07.md)
# Legged Daily - 2026-09-07

## Summary
- MulDP combines depth history, proprioception, and goal information in a diffusion policy for autonomous Unitree Go1 parkour navigation, supported by the new 31 km / 6,400-trajectory QPND dataset.
- FWBC-VLA gives an arm-equipped wheel-legged quadruped a sensorless 200 Hz contact estimate shared by VLA action generation and whole-body compensation; the project reports a 24.5-point average gain from compensation under sustained loads.
- BRIDGE couples humanoid morphology and control design in an 88 cm, 21-DoF platform reported at roughly USD 1.5K, although its full CAD, BOM, assembly, training, and deployment release is still pending paper acceptance.
- EngineAI released an Apache-2.0 PM01 humanoid navigation stack spanning Isaac Lab training, Gazebo simulation, ROS 2 deployment, LiDAR range-image policies, and verified PM01 + Livox Mid-360 hardware operation.
- The papers expose useful new source networks at Fudan University and across Zhejiang University, Shanghai AI Laboratory, Tsinghua University, Zhongguancun Academy, Deep Robotics, HUST, JoyIn AI, and CMU; no sufficiently fresh active job opening was verified.

<details>
<summary><strong>New Papers</strong></summary>

### MulDP: Multimodal Diffusion Policy for Autonomous Quadruped Parkour Navigation across Complex Terrains
- Link: https://arxiv.org/abs/2609.03984
- Source: arXiv
- Date: 2026-09-03
- Authors: Kangmai Hu, Yueqi Zhang, Peng Zhai, Xiaoyi Wei, Jiabin Hu, Zhixiang Liu, Quancheng Qian, Lihua Zhang
- Topics: quadruped / autonomous parkour / diffusion policy / visual navigation / sim-to-real
- Summary: Uses a multimodal diffusion policy over historical and current depth observations, proprioception, and goal information to generate coherent anticipatory velocity-command horizons for autonomous Unitree Go1 parkour navigation.
- Notes: The accompanying QPND dataset contains 6,400 trajectories, about 250,000 depth images, and 31 km of navigation over gaps, hurdles, stairs, gravel, boxes, flat ground, and impassable obstacles. The paper reports both Isaac Sim and real-robot evaluation, but no public code or dataset link was verified in this run.

### FWBC-VLA: Force-Aware Whole-Body Compensation for Contact-Rich Loco-Manipulation
- Link: https://arxiv.org/abs/2609.03889
- Source: arXiv
- Date: 2026-09-03
- Authors: Yutian Zhang, Siyuan Ma, Liwen Yang, Yang Li, Ce Hao, Haozhen Chi, Dong Wei, Qiaojun Yu, Dibo Hou
- Topics: wheel-legged quadruped / loco-manipulation / VLA / whole-body control / sensorless force estimation
- Summary: Introduces a sensorless force-aware interface that estimates contact from proprioception, injects force-history tokens into VLA action decoding, and supplies corrective actions to the downstream whole-body controller during contact-rich manipulation.
- Notes: HSR-Force runs at 200 Hz and the WL&Arm dataset contains more than 5,000 teleoperation episodes. Real-world door-opening and whiteboard-wiping results report a 24.5-percentage-point average contribution from body compensation, including +52 points for pushing a door with a closer and +44 points for board cleaning; no code release was verified.

### BRIDGE: An Open-Source Humanoid Platform via Morphology-Control Co-Design for Physical AI
- Link: https://arxiv.org/abs/2609.03497
- Source: arXiv
- Date: 2026-09-03
- Authors: Jianren Wang, Letian Qian, Zikai Wang, Weiwei Wu, Junjie Zong, Abhinav Gupta, Deepak Pathak
- Topics: humanoid / morphology-control co-design / motion retargeting / whole-body control / open hardware
- Summary: Optimizes humanoid morphology using anatomical constraints, human-motion retargeting error, actuator feasibility, and closed-loop dynamic tracking, then realizes the result as an 88 cm, 21-active-DoF platform for locomotion, balance, and dynamic whole-body motion.
- Notes: The project page reports 12.5 kg mass, approximately USD 1.5K platform cost, and open code/design intent. However, it also states that the full CAD, BOM, assembly tutorial, electrical specifications, and training/deployment code will be released only after paper acceptance, so the current release is incomplete.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### engineai_navigation
- Link: https://github.com/engineai-robotics/engineai_navigation
- Category: RL
- Robot Type: humanoid
- Simulator: Isaac Lab / Gazebo
- Deploy: both
- Summary: An end-to-end PPO navigation stack for the EngineAI PM01 that converts ordered LiDAR range images into velocity commands executed by a low-level walking policy, with training, ONNX export, ROS 2 simulation, and hardware deployment paths.
- Notes: The repository was created on 2026-09-03 and is Apache-2.0 for EngineAI-authored code, with third-party licenses documented separately. It includes a PM01 URDF, an SRU-modified rsl_rl stack, maze terrains, Super-LIO integration, and deployment verified on PM01 with Livox Mid-360; simulation and hardware packages intentionally use separate ROS 2 install trees.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Fudan University autonomous quadruped parkour team
- Institution: Fudan University
- arXiv: https://arxiv.org/abs/2609.03984
- Lab / Department: College of Intelligent Robotics and Advanced Manufacturing
- Key Topics: quadruped / autonomous parkour / diffusion policy / visual navigation / robot learning
- Notes: MulDP identifies a concentrated Fudan source network led by corresponding author Lihua Zhang around multimodal navigation policies, Isaac Sim data generation, and real-world Unitree Go1 parkour.

### Zhejiang University-led force-aware loco-manipulation collaboration
- Institution: Zhejiang University / Shanghai Artificial Intelligence Laboratory / Tsinghua University / Zhongguancun Academy / Deep Robotics / Zhejiang University of Science and Technology
- Homepage: https://ytydt-reuz.github.io/FWBC-VLA/
- arXiv: https://arxiv.org/abs/2609.03889
- Lab / Department: cross-institution paper collaboration
- Key Topics: wheel-legged quadruped / VLA / sensorless force estimation / whole-body control / loco-manipulation
- Notes: FWBC-VLA links academic and industry groups around arm-equipped wheel-legged robots, using proprioceptive contact estimation as a shared interface between semantic action generation and physical stabilization.

### HUST / JoyIn AI / CMU humanoid co-design collaboration
- Institution: Huazhong University of Science and Technology / JoyIn AI / Carnegie Mellon University
- Homepage: https://sites.google.com/view/bridgerobot
- arXiv: https://arxiv.org/abs/2609.03497
- Lab / Department: cross-institution paper collaboration
- Key Topics: humanoid / open hardware / morphology-control co-design / motion imitation / whole-body control
- Notes: BRIDGE connects hardware and control work at HUST and JoyIn AI with Abhinav Gupta and Deepak Pathak at CMU, making this a useful source network for compact low-cost humanoids designed explicitly around human-motion data.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No sufficiently fresh, active, and high-confidence legged-robotics opportunity was verified from an official source in this run. The EPFL BioRob openings page describes general PhD/Postdoc application routes and mentions humanoid-neuromechanics opportunities in indexed text, but the available status signals were conflicting and did not support promoting a specific opening as active.

</details>
