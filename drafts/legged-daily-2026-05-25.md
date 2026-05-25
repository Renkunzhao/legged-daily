**English** | [中文](../zh/drafts/legged-daily-2026-05-25.md)
# Legged Daily - 2026-05-25

## Summary
- Today's strongest paper signal is Any2Any, which targets low-cost cross-embodiment transfer for humanoid whole-body tracking from Unitree G1 to LimX platforms.
- Direct Dynamic Retargeting is a high-signal humanoid imitation paper because it bypasses intermediate geometric retargeting and optimizes dynamically feasible references directly from monocular videos.
- Four Simple Proprioceptive Estimators for Legged Robots is useful infrastructure work: it compares contact-aided EKF / factor-graph / fixed-lag smoothing variants and reports GTSAM plus ROS 2 availability.
- Unitree released or surfaced `unitree_rl_mjlab`, a MuJoCo-based RL stack for Go2, A2, AS2, G1, R1, H1_2, and H2 with Train → Play → Sim2Real workflow.
- `AMP_Running_baseline` is a focused Unitree G1 running/imitation baseline around Isaac Lab, AMP, motion data, actuator modeling, and hardware-ready deployment.
- CUHK Legged Robot Lab has both a 2026 RSS paper signal and active Fall 2027 PhD plus RA/engineer openings.

<details>
<summary><strong>New Papers</strong></summary>

### Any2Any: Efficient Cross-Embodiment Transfer for Humanoid Whole-Body Tracking
- Link: https://arxiv.org/abs/2605.23733
- Source: arXiv
- Date: 2026-05-22
- Authors: Ming Yang, Tao Yu, Feng Li, Hua Chen
- Topics: humanoid / whole-body tracking / cross-embodiment transfer / parameter-efficient fine-tuning / imitation learning
- Summary: Framework for transferring pretrained humanoid whole-body tracking specialists across robot embodiments using kinematic alignment plus lightweight dynamics adaptation; the paper reports transfer from Unitree G1 pretrained Sonic models to LimX Oli and LimX Luna using about 1% of the full-training data and compute.
- Notes: Strong long-term signal for reusable humanoid WBT policies and fast robot-platform adaptation; code is stated as not yet available in the arXiv abstract/source search.

### Direct Dynamic Retargeting for Humanoid Imitation Learning from Videos
- Link: https://arxiv.org/abs/2605.23762
- Source: arXiv
- Date: 2026-05-22
- Authors: Constant Roux, Ludovic De Matteïs, Armand Jordana, Valentin Guillet, Nicolas Mansard, Olivier Stasse, Philippe Souères
- Topics: humanoid / imitation learning / video demonstrations / motion retargeting / model predictive control / physics simulation
- Summary: Single-stage dynamic retargeting method that generates physically feasible humanoid reference trajectories directly from monocular expert videos by optimizing in task space with a sampling-based MPC solver in simulation.
- Notes: Relevant to humanoid skill acquisition pipelines because it challenges geometric or indirect retargeting as a bottleneck before RL policy training; source code is promised but not yet verified as public.

### Four Simple Proprioceptive Estimators for Legged Robots
- Link: https://arxiv.org/abs/2605.23100
- Source: arXiv
- Date: 2026-05-21
- Authors: Frank Dellaert, Chiyun Noh, Varun Agrawal, Ayoung Kim
- Topics: legged robots / state estimation / proprioceptive odometry / contact-aided estimation / GTSAM / ROS 2
- Summary: Compares four contact-aided legged state estimators ranging from invariant EKF to small factor graphs and fixed-lag smoothing with contact-episode footholds, targeting reproducible proprioceptive odometry with IMU and intermittent foot contacts.
- Notes: Good infrastructure paper to track for practical legged state-estimation baselines; the abstract states that all four variants are available in GTSAM and that a ROS 2-compatible implementation is provided.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### unitree_rl_mjlab
- Link: https://github.com/unitreerobotics/unitree_rl_mjlab
- Category: RL / simulator / toolkit
- Robot Type: humanoid / quadruped / general Unitree platforms
- Simulator: MuJoCo
- Deploy: both
- Summary: Official Unitree MuJoCo-based reinforcement-learning project built on mjlab, supporting Unitree Go2, A2, AS2, G1, R1, H1_2, and H2 with velocity tracking, G1 motion imitation, ONNX export, and sim-to-real deployment paths.
- Notes: README describes Train → Play → Sim2Real workflow, multi-GPU training, Unitree SDK2 / CycloneDDS deployment, and use with `unitree_mujoco` before physical deployment.

### AMP_Running_baseline
- Link: https://github.com/Jiarui-Xie/AMP_Running_baseline
- Category: RL / imitation learning / deployment baseline
- Robot Type: humanoid
- Simulator: Isaac Lab
- Deploy: both
- Summary: Unitree G1 locomotion training codebase for the 2026 Beijing Yizhuang Half Marathon Robot Race, extending legged_lab with Adversarial Motion Priors, BASE walk/run motion clips, actuator modeling, action-delay randomization, tuned rewards, and checkpoints.
- Notes: Useful practical baseline for G1 running and motion-imitation experiments; README distinguishes a hardware-tested BASE checkpoint from later simulation-only checkpoints.

### sfg-ros
- Link: https://github.com/iis-esslingen/sfg-ros
- Category: toolkit / perception middleware
- Robot Type: general / legged fleets
- Simulator: none
- Deploy: hardware / field software
- Summary: ROS 2 resource-aware framework for dense multi-agent perception that uses schema-driven Fast DDS routing, centralized on-demand decoding, and hardware-agnostic containers; evaluated on fleets including wheeled and legged robots with LiDAR and stereo depth.
- Notes: Adjacent but relevant for legged field robotics and multi-robot perception infrastructure; project page reports reduced per-subscriber CPU scaling penalty versus standard ROS 2.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### CUHK Legged Robot Lab / Yun-Hui Liu
- Institution: The Chinese University of Hong Kong
- Homepage: https://cuhkleggedrobotlab.github.io/
- Lab / Department: Department of Mechanical and Automation Engineering, CUHK
- Key Topics: quadruped / locomotion / loco-manipulation / perception and navigation / actuator and mechanical system design
- Notes: Official lab page states a 2026 RSS acceptance for Zhang Linwei's "VRA: Grounding Discrete-Time Joint Acceleration in Voltage-Constrained Actuation" and says the lab is actively seeking Fall 2027 PhD applicants plus multiple RAs and engineers.

### LAAS-CNRS / Gepetto humanoid control network
- Institution: LAAS-CNRS / associated French humanoid robotics network; verify individual affiliations before adding to master list
- arXiv: https://arxiv.org/abs/2605.23762
- Key Topics: humanoid / dynamic retargeting / MPC / imitation learning / physics simulation
- Notes: The DDR author network around Nicolas Mansard, Olivier Stasse, and Philippe Souères is a useful source for dynamic humanoid motion generation and retargeting work.

### Frank Dellaert / Georgia Tech Borg Lab and GTSAM network
- Institution: Georgia Institute of Technology / GTSAM ecosystem; verify coauthor affiliations before adding students
- arXiv: https://arxiv.org/abs/2605.23100
- GitHub: https://github.com/borglab/gtsam
- Key Topics: legged state estimation / factor graphs / smoothing / proprioceptive odometry / ROS 2
- Notes: The new legged estimator paper makes the GTSAM network a practical source to track for reusable state-estimation tooling, even though the lab is not exclusively legged-robotics focused.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### CUHK Legged Robot Lab
- Type: PhD / Research Assistant / Engineer
- Location: Hong Kong
- Source: official lab page
- Deadline: Fall 2027 PhD cycle / RA and engineer timing unknown
- Topics: robust and precise locomotion / whole-body loco-manipulation / traversability-aware perception and navigation / safe actuator and mechanical system design
- Status: active
- Notes: Official homepage says the lab is actively seeking self-motivated PhD applicants for Fall 2027 and has multiple RA and engineer openings; contact is listed on the lab page.

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: Official page continues to list multiple continuous openings and explicit legged-robotics requirements; no stale signal today.

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: aggregator results pointing to prior official/lab-linked announcement; official page should be rechecked before formal insertion beyond existing master-list entry
- Deadline: Fall 2026 opening; EPFL doctoral program deadlines typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: watching
- Notes: Still relevant as an already tracked opportunity, but today's direct fetch of the old `www.biorob.epfl.ch/openings/` URL failed DNS resolution, so confirm from EPFL/Biorob official channels before surfacing as newly verified.

</details>
