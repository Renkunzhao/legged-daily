**English** | [中文](../zh/drafts/legged-daily-2026-09-20.md)
# Legged Daily - 2026-09-20

## Summary
- RoM-Nav transfers navigation knowledge learned with reduced-order dynamics into a full Unitree G1 policy and adds a Poisson safety filter, demonstrating mapless multi-floor runs longer than 100 m with over 10 m of vertical displacement.
- ViLoMan turns partial human-object demonstrations into executable whole-body trajectories and distills a single onboard depth-and-proprioception policy for autonomous G1 door closing.
- A scene-grounded construction framework aligns retargeted roofer motions with metric roof geometry and reports physical G1 execution of uphill walking, nailgun, hammering, and bending motions.
- LP-NavOA released a substantial MuJoCo/mjlab research fork for planner-free G1 local navigation under short-range sensing; WholeBodyWAM's new repository is a project/demo site rather than model-training code.
- No new high-confidence legged-robotics opening was verified today; the expired LAAS-CNRS safe-RL PhD remains proposed for removal pending confirmation.

<details>
<summary><strong>New Papers</strong></summary>

### Learning Safe Humanoid Navigation from Reduced Order Models
- Link: https://arxiv.org/abs/2609.19272
- Source: arXiv; under review for ICRA 2027
- Date: 2026-09-16
- Authors: William D. Compton, Zachary Olkin, Ryan Bena, Aaron D. Ames
- Topics: humanoid navigation / reduced-order models / reinforcement learning / safety filtering / multi-floor autonomy
- Summary: RoM-Nav first learns LiDAR-based navigation on reduced-order dynamics, transfers that knowledge to a full-order Unitree G1 policy with a frozen locomotion controller, and applies a Poisson safety filter to handle out-of-distribution obstacles.
- Notes: The authors demonstrate mapless multi-floor trials exceeding 100 m in path length and 10 m in vertical displacement. The project page provides hardware videos, but no official training-code repository was identified during this review; results were not independently reproduced.

### ViLoMan: Learning Visual-Proprioceptive Whole-Body Loco-Manipulation Skills for Humanoid Robots
- Link: https://arxiv.org/abs/2609.19340
- Source: arXiv
- Date: 2026-09-16
- Authors: Zejie Tian, Ruibing Hou, Bingpeng Ma, Börje F. Karlsson, Shiguang Shan
- Topics: humanoid loco-manipulation / egocentric depth / teacher-student distillation / motion retargeting / sim-to-real
- Summary: ViLoMan converts partial kinematic human-object demonstrations into physically executable robot trajectories, then distills them into one joint-level policy using only onboard depth and proprioception at deployment.
- Notes: The paper evaluates autonomous door closing on Unitree G1 across door configurations and initial states in simulation and hardware. The supplementary project page exposes detailed training and reward information plus videos, but no public policy-training repository was found today.

### Learning Slope-Adaptive Whole-Body Locomotion for Humanoid Robots in Roofing Construction
- Link: https://arxiv.org/abs/2609.20558
- Source: arXiv
- Date: 2026-09-17
- Authors: Songyang Liu, Shuai Li
- Topics: humanoid construction / slope-adaptive locomotion / scene-grounded motion retargeting / reinforcement learning / whole-body control
- Summary: Grounds retargeted roofer demonstrations against a metric roof model using trajectory optimization, then trains an execution-aware policy to preserve support contacts, work relations, clearance, and nonpenetration under tracking errors.
- Notes: The authors report 3/3 successful evaluations for nailgun, hammering, and lateral-pushing tasks, with 0.256–0.531 cm work-clearance errors, plus physical G1 execution whose mean base-frame motion errors remain below 80 mm. No official code repository was identified during this review.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### shenqiqishi/LP-NavOA-code
- Link: https://github.com/shenqiqishi/LP-NavOA-code
- Category: reinforcement learning / navigation / obstacle avoidance / toolkit
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo / mjlab
- Deploy: simulation training and benchmarking / ONNX policy export / related hardware demos
- Summary: Research fork of mjlab implementing a perception-action PPO locomotion backbone and recurrent local planner that changes only the heading command, enabling planner-free G1 local navigation from proprioception, short-range range sensing, and a body-frame goal direction.
- Notes: The Apache-2.0 repository documents seven tasks, a three-stage locomotion curriculum, open-wall and indoor planner distillation, evaluation scripts, ablations, tests, and ONNX export. It was created on 2026-09-19; the linked project page provides real-robot obstacle-bypass videos, while the public README does not provide a complete hardware deployment procedure.

### zbzyjya/WholeBodyWAM
- Link: https://github.com/zbzyjya/WholeBodyWAM
- Category: viewer / project page
- Robot Type: humanoid / TianGong 3.0
- Simulator: none
- Deploy: browser / hardware demos
- Summary: Apache-2.0 project-site repository presenting a motion-pretrained Video-Motion-Action model and real-world TianGong 3.0 whole-body manipulation and loco-manipulation demonstrations.
- Notes: The site describes UniMotion-4K, a heterogeneous corpus with more than 4,100 hours of motion, and reports a 72.2% average normalized score across six real-world tasks. This repository hosts the project page and media, not model-training code, checkpoints, or the motion corpus; it was updated on 2026-09-17.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Aaron D. Ames / AMBER Lab — RoM-Nav collaboration
- Institution: California Institute of Technology
- Homepage: https://www.ames.caltech.edu/
- arXiv: https://arxiv.org/abs/2609.19272
- GitHub: https://github.com/wdc3iii
- Lab / Department: AMBER Lab / Mechanical and Civil Engineering and Control and Dynamical Systems
- Key Topics: humanoid locomotion / autonomous navigation / safety-critical control / reinforcement learning / reduced-order models
- Notes: William D. Compton, Zachary Olkin, Ryan Bena, and Aaron D. Ames extend the group's locomotion and safety-control work toward long-horizon, mapless, multi-floor G1 navigation. The reduced-order-to-full-order transfer and output safety filter make this a high-value source network for scalable safe humanoid autonomy.
- Students and Representative Works:
  - [William D. Compton](https://github.com/wdc3iii) — [RoM-Nav](https://wdc3iii.github.io/rom-nav/)

### Beijing Innovation Center of Humanoid Robotics — WholeBodyWAM collaboration
- Institution: Beijing Innovation Center of Humanoid Robotics / Nankai University / Beijing Institute of Technology / Tsinghua University
- Homepage: https://zbzyjya.github.io/WholeBodyWAM/
- arXiv: https://arxiv.org/abs/2609.18197
- GitHub: https://github.com/zbzyjya/WholeBodyWAM
- Key Topics: humanoid world-action models / motion pretraining / loco-manipulation / whole-body control / TianGong
- Notes: Bowei Zhang, Qiyao Zhang, Shuanghao Bai, Xinhua Wang, Meng Li, and collaborators connect heterogeneous human/humanoid motion pretraining with real-world TianGong 3.0 control. This is distinct from the controller-grounded WholeBodyWAM paper tracked on 2026-09-16; the duplicate project name should be handled carefully in future retrieval.
- Students and Representative Works:
  - [Bowei Zhang](https://arxiv.org/abs/2609.18197) — [Learning Whole-Body World Action Models with Scalable Motion Priors](https://zbzyjya.github.io/WholeBodyWAM/)

### Correll Lab — Unitree G1 and Dex3-1 platform signal
- Institution: University of Notre Dame
- Homepage: https://correlllab.github.io/
- GitHub: https://github.com/correlllab/leprechaun_g1
- Lab / Department: Correll Lab
- Key Topics: humanoid hardware / dexterous manipulation / Unitree G1 / robot learning
- Notes: The lab created a public MIT-licensed hardware-reference repository for its Unitree G1 and Dex3-1 dexterous hands on 2026-09-18. The repository is currently only a minimal platform marker rather than a software release, but it is a useful early signal for future Notre Dame humanoid work.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No newly verified opening
- Type: PhD / RA / Internship / Research Engineer / Postdoc
- Source: official-source review
- Deadline: unknown
- Topics: humanoid / quadruped / locomotion / robot learning
- Status: watching
- Notes: No new legged-robotics opportunity with sufficiently complete and verifiable official details was identified in this run. Existing active/watch entries remain unchanged pending their normal recheck cycle.

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team, PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / no longer actionable
- Reason: The application deadline was 2026-07-31, and the official CNRS portal states that the offer is no longer available. This proposed removal remains pending confirmation.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
