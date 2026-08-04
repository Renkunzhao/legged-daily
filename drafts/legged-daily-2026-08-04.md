**English** | [中文](../zh/drafts/legged-daily-2026-08-04.md)
# Legged Daily - 2026-08-04

## Summary
- Three new papers met the inclusion bar: StableMimic unifies humanoid motion tracking and structured post-fall recovery on a real Unitree G1; Open-DiffLoco trains hardware-deployable blind quadruped locomotion with differentiable MuJoCo MJX; and a residual-based adaptive InEKF improves Unitree Go2 state estimation without foot-force sensing.
- Two repositories met the implementation bar. Open-DiffLoco publishes the differentiable-training and C++ deployment stack behind the paper, while the previously unavailable official RoboNaldo code now exposes the Isaac Lab training curriculum, reference motion, deployment path, and real-G1 demonstrations.
- The strongest theme today is deployability rather than simulation-only scores: both selected learning systems report physical Unitree deployments, and the state-estimation paper evaluates indoor and outdoor Go2 datasets.
- No new primary-source lab or professor update was verified today; author affiliations and repository ownership were not treated as standalone institutional announcements.
- ETH Zurich RSL's rolling openings remain active. The LAAS-CNRS safe-RL humanoid PhD is now explicitly marked unavailable by the official portal and remains a proposed stale removal pending confirmation.

<details>
<summary><strong>New Papers</strong></summary>

### StableMimic: Smooth Human-Like Recovery for Humanoid Motion Tracking - Learning Beyond the Tracking Distribution for Structured Post-Fall Behavior
- Link: https://arxiv.org/abs/2608.02385
- Source: arXiv
- Date: 2026-08-03
- Authors: Weihao Wu, Ming Huang, Ruofei Liu, Jinglei Nie, Shuxiang Guo, Chunying Li
- Topics: humanoid motion tracking / fall recovery / imitation learning / mixture of experts / safety / real-robot deployment
- Summary: StableMimic trains dedicated tracking and recovery experts with a proprioceptive blending gate, enabling a Unitree G1 to recover autonomously from contact-rich falls and resume commanded motion without an external policy switch.
- Notes: The preprint reports the lowest errors on all four tracking metrics across five methods on the retargeted LAFAN1 dance subset, 100/100 recoveries in matched push-to-fall trials, and qualitative real-G1 dance and standing-reference deployments. These results are preprint claims under the authors' stated protocol and have not been formally peer-reviewed.

### Open-DiffLoco: Open-Source Differentiable Learning for Deployable Blind Quadruped Locomotion
- Link: https://arxiv.org/abs/2608.02069
- Source: arXiv
- Date: 2026-08-03
- Authors: Martin Opat
- Topics: quadruped locomotion / differentiable simulation / MJX / SHAC / sim-to-real / blind control
- Summary: Open-DiffLoco implements SHAC and a Jacobian-augmented critic objective in MuJoCo MJX to train a proprioceptive blind locomotion policy that transfers to a physical Unitree Go2 without base linear velocity, reference trajectories, or complex auxiliary rewards.
- Notes: The paper reports 20–60 minute training under 6 GB VRAM on an RTX 5080, omnidirectional tracking error below 0.2 m/s, speeds above 1 m/s, and robustness to uneven terrain and lateral pushes. The associated source repository and deployment documentation are public; the numerical claims remain author-reported preprint results.

### Residual-Based Adaptive Kalman Filtering for Legged Robot State Estimation
- Link: https://arxiv.org/abs/2608.02316
- Source: arXiv
- Date: 2026-08-03
- Authors: Mihaela Popescu, Dennis Mronga, Shivesh Kumar, Frank Kirchner
- Topics: legged state estimation / invariant EKF / adaptive covariance / sensor fusion / quadruped / proprioception
- Summary: The method adapts InEKF process and measurement covariances online from filter residuals and innovations, reducing dependence on fixed expert tuning across changing gaits and environments.
- Notes: On indoor and outdoor Unitree Go2 datasets, the authors report that adapting measurement covariance alone improves trotting accuracy by 25% over a fixed-tuned InEKF and reaches performance comparable to a foot-force-based approach without requiring foot-force measurements or extra parameter tuning.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### MartinOpat/open-diffloco
- Link: https://github.com/MartinOpat/open-diffloco
- Category: differentiable reinforcement learning / quadruped locomotion / sim-to-real / deployment stack
- Robot Type: quadruped; Unitree Go2
- Simulator: MuJoCo MJX for differentiable training
- Deploy: physical Unitree Go2 through a C++ deployment path using the Unitree SDK, with optional ROS 2 support
- Summary: The official Open-DiffLoco implementation provides SHAC and JAVE training configurations, actor variants with and without privileged observations or kinematic references, checkpoint export, and C++ policy deployment tools.
- Notes: The repository includes reproducible CLI configurations and detailed deployment documentation, but GitHub does not expose a recognized SPDX license for the current snapshot. Hardware metrics should be interpreted according to the associated preprint and its reported setup.

### OpenDriveLab/RoboNaldo
- Link: https://github.com/OpenDriveLab/RoboNaldo
- Category: reinforcement learning / humanoid whole-body control / motion-guided curriculum / soccer / sim-to-real
- Robot Type: humanoid; Unitree G1
- Simulator: NVIDIA Isaac Lab 2.3.2 / Isaac Sim 5.1.0 with RSL-RL PPO
- Deploy: simulation plus physical Unitree G1; companion deployment repository exports and runs ONNX policies on hardware
- Summary: The now-public official codebase trains a humanoid soccer-shooting policy through motion tracking, stationary-ball adaptation, and moving-ball task generalization, then deploys the learned policy to a real G1 with onboard perception.
- Notes: The MIT-licensed repository contains the Isaac Lab task extension, staged curriculum presets, a default retargeted right-kick motion, training/evaluation scripts, and links to pinned deployment code and real-robot demos. The project was covered as a paper on 2026-06-10 when its code link returned 404; this entry tracks the subsequently published implementation rather than repeating the paper.

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
- Status: active at 2026-08-04 verification; previously tracked opportunity, not a new master-list addition
- Notes: The official page continues to expose application links for rolling PhD and PostDoc recruitment plus research, software, robot-design, embedded-systems, and electronics roles directly connected to legged robots and field deployment.

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / official offer unavailable
- Reason: The listed 2026-07-31 23:59 deadline has passed, and the official CNRS portal now explicitly states, “The requested offer is no longer available.” Remove or mark the active master-list entry as expired after confirmation.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
