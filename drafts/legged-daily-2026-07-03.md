**English** | [中文](../zh/drafts/legged-daily-2026-07-03.md)
# Legged Daily - 2026-07-03

## Summary
- arXiv cs.RO new listings for 2026-07-03 surfaced three strong legged/humanoid items: wall-supported bipedal locomotion on a quadruped, actuator reality shaping for zero-shot sim-to-real, and full-size humanoid heavy-payload teleoperation.
- Two Isaac Lab repositories are useful for tracking: a structured legged-RL tutorial from Go2 to H1, and IIT DLSLab's quadruped locomotion stack with sim-to-sim and ROS2 sim-to-real paths.
- CUHK Legged Robot Lab is actively advertising Fall 2027 PhD, RA, and engineer openings, and reports 2026 activity around Hong Kong Embodied AI Lab and RSS 2026 work on voltage-constrained actuation.
- EPFL BioRob has an official humanoid locomotion neuromechanics opening: the postdoc role is marked closed, while the PhD track is considered on a rolling basis after EPFL doctoral-school acceptance.
- ETH RSL continues to list rolling PhD, postdoc, research staff, robot design, embedded, and electronics openings across legged robots, mobile manipulation, actuation, control, learning, planning, and perception.

<details>
<summary><strong>New Papers</strong></summary>

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid, teleoperation, motion tracking, loco-manipulation, payload curriculum
- Summary: Introduces a teleoperation framework for full-size humanoids that learns from noisy VR references using privileged motion guidance and a windowed payload curriculum, then demonstrates turns, forward/backward locomotion, squats, and payloads up to 24 kg on a 175 cm, 65 kg L7 humanoid.
- Notes: Project page listed at https://heft.axell.top/ ; no GitHub repository was found from quick search today.

### Actuator Reality Shaping for Zero-Shot Sim-to-Real Robot Learning
- Link: https://arxiv.org/abs/2607.02205
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Satoshi Yamamori, Koji Ishihara, Kentaro Minamikawa, Kiyoharu Ohomori, Taiyo Yazaki, Norikazu Sugimoto, Jun Morimoto
- Topics: sim-to-real, actuator control, robot learning, humanoid, wheeled-legged robot
- Summary: Proposes shaping the physical actuator closed-loop response to match the simulator's ideal second-order reference dynamics, providing a reusable actuator interface for zero-shot deployment of policies trained only with the reference model.
- Notes: Validated on a single-joint servo, a 7-DOF arm reaching task, a wheeled-legged robot driving over a slope, and humanoid walking; no public code surfaced in today's search.

### Multi-Rate Nonlinear Model Predictive Control for Wall-Supported Bipedal Locomotion of Quadrupedal Robots
- Link: https://arxiv.org/abs/2607.01574
- Source: arXiv cs.RO / math.OC
- Date: 2026-07-02
- Authors: Taizoon Chunawala, Jeeseop Kim, Kaveh Akbari Hamed
- Topics: quadruped, bipedal locomotion, wall-assisted locomotion, NMPC, whole-body control
- Summary: Presents a layered MR-NMPC plus nonlinear whole-body control framework that lets a Unitree A1 perform wall-supported hybrid bipedal locomotion in constrained, rough environments, with reported 2.9× higher success rate than heuristic-foot-placement MPC in simulation.
- Notes: Accepted to IEEE/RSJ IROS 2026.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Lab-of-AI-and-Robotics/IsaacLab-Tutorial
- Link: https://github.com/Lab-of-AI-and-Robotics/IsaacLab-Tutorial
- Category: RL / simulator / toolkit / tutorial
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab
- Deploy: sim
- Summary: A 10-chapter Apache-2.0 tutorial for developing reinforcement-learning environments for legged robots in NVIDIA Isaac Lab, moving from Unitree Go2 baseline work to a Unitree H1 humanoid locomotion challenge.
- Notes: Created by Jihoon Moon at SKKU Lab of AI and Robotics; chapters are split into dedicated GitHub branches and a linked Notion tutorial.

### iit-DLSLab/basic-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- Category: RL / control / sim-to-real / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Isaac Lab DirectEnv stack for quadruped locomotion across Aliengo, Go2, B2, and HyQReal2, including flat/rough and blind/vision environments plus sim-to-sim and ROS2 sim-to-real paths.
- Notes: Tracks concurrent state estimation, rapid motor adaptation, morphological symmetries, adversarial motion priors, parameter identification via pace, and Unitree deployment integration.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### CUHK Legged Robot Lab / Prof. Liu Yun-Hui
- Institution: The Chinese University of Hong Kong
- Homepage: https://cuhkleggedrobotlab.github.io/
- Lab / Department: Department of Mechanical and Automation Engineering
- Key Topics: quadruped, locomotion, whole-body loco-manipulation, perception, navigation, safe actuation, mechanical design
- Notes: The lab states active interest in real-world legged robot deployment; recent 2026 signals include the launch of the Hong Kong Embodied AI Lab and an RSS 2026 paper on voltage-constrained actuation.

### ETH Zurich Robotic Systems Lab
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/the-lab/open-positions.html
- Lab / Department: Robotic Systems Lab
- Key Topics: legged robots, mobile manipulation, motion planning, MPC, reinforcement learning, perception, actuation, teleoperation
- Notes: Official openings page remains a high-value recurring source because it lists rolling PhD, postdoc, research staff, robot design, embedded, and electronics roles tied to legged robotics and field deployment.

### EPFL BioRob / Prof. Auke Ijspeert
- Institution: EPFL
- Homepage: https://www.epfl.ch/labs/biorob/openings/
- Lab / Department: Biorobotics Laboratory
- Key Topics: humanoid, human locomotion neuromechanics, bio-inspired control, reinforcement learning, neuromechanical simulation
- Notes: Official page describes a Fall 2026 project on leveraging human locomotion neuromechanics for humanoid controllers; the postdoc track is marked closed, but the PhD process is still described as rolling after EPFL doctoral-school acceptance.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRob
- Type: PhD
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling / until filled; EPFL doctoral program deadlines typically April 15 and December 15
- Topics: humanoid, locomotion, neuromechanics, reinforcement learning, bio-inspired control
- Status: active
- Notes: Official page says applications are considered continuously until filled, with a good start date around September 2026; postdoc position for the same project is explicitly marked closed.

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Research Engineer / Robot Design / Embedded Systems / Electronics
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots, mobile manipulation, actuation, control, learning, planning, perception, teleoperation
- Status: active
- Notes: Official page lists multiple rolling roles and directs applicants to separate external application forms rather than email.

### CUHK Legged Robot Lab
- Type: PhD / RA / Research Engineer
- Location: Hong Kong
- Source: lab page
- Deadline: Fall 2027 PhD cycle / unknown for RA and engineers
- Topics: legged robots, locomotion, whole-body loco-manipulation, perception, navigation, actuation, mechanical design
- Status: active
- Notes: Lab page says it is actively seeking self-motivated Fall 2027 PhD applicants plus multiple RAs and engineers.

### Proposed Removal / Stale Item
- Current Status: stale
- Reason: EPFL BioRob's postdoc position for the humanoid neuromechanics project is now explicitly marked closed on the official openings page.
- Source Checked: https://www.epfl.ch/labs/biorob/openings/

</details>
