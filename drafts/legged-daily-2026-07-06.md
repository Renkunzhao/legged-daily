**English** | [中文](../zh/drafts/legged-daily-2026-07-06.md)
# Legged Daily - 2026-07-06

## Summary
- Fresh arXiv legged-robotics submissions this run are concentrated around humanoid teleoperation, actuator-level sim-to-real transfer, and interpretable gait-aware quadruped RL.
- HEFT is a high-signal humanoid teleoperation paper because it targets a full-size 175 cm / 65 kg platform and real payload handling up to 24 kg.
- Actuator Reality Shaping is worth tracking as a reusable sim-to-real interface idea: instead of only improving simulator fidelity, it shapes hardware actuator response toward the idealized dynamics used in policy training.
- Gait-aware quadruped locomotion with temporal logic specifications connects formal methods to PPO reward shaping and may be useful for more controllable gait design.
- Repo updates worth previewing include ProtoMotions3 for humanoid motion imitation / retargeting, FoCoDyn for differentiable floating-base contact dynamics, and MGDP for generalized depth-perception-based quadruped locomotion.
- Opportunity signal remains strongest at EPFL BioRob: the official page still lists Fall 2026 Postdoc and PhD openings on neuromechanics-informed humanoid locomotion.

<details>
<summary><strong>New Papers</strong></summary>

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid / teleoperation / motion tracking / payload handling / sim-to-real
- Summary: Introduces HEFT, a full-size humanoid teleoperation framework using Privileged Motion Guidance and a Windowed Payload Curriculum to make noisy VR references usable for robust payload-aware humanoid motion tracking.
- Notes: Deployed on L7, a 175 cm, 65 kg humanoid, with forward/backward locomotion, turns, squats, and payloads up to 24 kg; project page listed at https://heft.axell.top/.

### Actuator Reality Shaping for Zero-Shot Sim-to-Real Robot Learning
- Link: https://arxiv.org/abs/2607.02205
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Satoshi Yamamori, Koji Ishihara, Kentaro Minamikawa, Kiyoharu Ohomori, Taiyo Yazaki, Norikazu Sugimoto, Jun Morimoto
- Topics: sim-to-real / actuator dynamics / robot learning / humanoid / wheeled-legged robot
- Summary: Proposes shaping the real actuator closed-loop response to match the idealized second-order reference dynamics assumed during simulation, enabling zero-shot deployment without task-level fine-tuning or learned actuator models.
- Notes: Validated on a servo, a 7-DOF arm reaching task, a wheeled-legged robot on a slope, and humanoid walking; useful as an actuator-interface idea for legged RL deployment.

### Learning Gait-Aware Quadruped Locomotion with Temporal Logic Specifications
- Link: https://arxiv.org/abs/2607.00442
- Source: arXiv cs.RO / cs.AI
- Date: 2026-07-01
- Authors: Merve Atasever, Cagan Bakirci, Alfredo Reina Corona, Keyan Azbijari, Jyotirmoy V. Deshmukh
- Topics: quadruped / reinforcement learning / gait specification / signal temporal logic / MuJoCo XLA
- Summary: Uses Signal Temporal Logic templates to specify gait, safety, synchronization, tracking, and actuation constraints, then converts robustness into dense PPO-compatible rewards for quadruped locomotion.
- Notes: Instantiated on Google's Barkour quadruped in MuJoCo XLA / MJX with walking-trot, trot, and bound regimes; project page listed at https://stl-locomotion.github.io/.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### NVlabs/ProtoMotions
- Link: https://github.com/NVlabs/ProtoMotions
- Category: simulator / RL / retargeting / toolkit
- Robot Type: humanoid / digital human
- Simulator: Isaac Gym / Newton / MuJoCo
- Deploy: sim / hardware
- Summary: GPU-accelerated simulation and learning framework for physically simulated digital humans and humanoid robots, including AMASS-scale motion imitation, PyRoki-based robot retargeting, and policy testing across multiple physics engines.
- Notes: README describes ProtoMotions3, Apache-2.0 licensing, AMASS / BONES workflows, H1_2 and G1 examples, and real-hardware deployment direction.

### mstoelzle/focodyn
- Link: https://github.com/mstoelzle/focodyn
- Category: control / toolkit
- Robot Type: legged / humanoid
- Simulator: none
- Deploy: data / toolkit
- Summary: Differentiable floating-base dynamics and contact-pose Jacobian package for legged robots, aimed at CBF/CLF, trajectory optimization, and learning workflows that need gradients through rigid-body dynamics and contact kinematics.
- Notes: Python >=3.11 package wrapping Adam's PyTorch backend; currently includes Unitree G1 URDF/MJCF assets, control-affine f(x) and g(x), differentiable foot contact poses, and a Viser viewer.

### arclab-hku/MGDP
- Link: https://github.com/arclab-hku/MGDP
- Category: RL / perception / simulator
- Robot Type: quadruped
- Simulator: Isaac Gym / NVIDIA Warp sensors
- Deploy: sim
- Summary: Implementation for MGDP, a generalized depth-perception-based quadruped locomotion framework using low-dimensional terrain features, explicit depth denoising, and terrain-adaptive rewards.
- Notes: Repository is tied to an Advanced Science 2026 paper claim in its README; supports multi-robot quadruped training / fine-tuning workflows and visualization scripts.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### HEFT / Jianyu Chen group signal
- Institution: not verified from arXiv page alone
- Homepage: https://heft.axell.top/
- Key Topics: humanoid / teleoperation / motion tracking / payload handling / robot learning
- Notes: HEFT is a new arXiv signal centered on full-size humanoid teleoperation under real payloads. Follow-up check should verify the project page, code / video availability, and the authors' lab affiliation before adding a formal lab entry.

### STL Locomotion / Jyotirmoy V. Deshmukh coauthor signal
- Institution: not verified from arXiv page alone
- Homepage: https://stl-locomotion.github.io/
- Key Topics: quadruped / formal methods / signal temporal logic / reinforcement learning / gait control
- Notes: The gait-aware quadruped paper is a useful source-network signal linking temporal-logic specifications with legged RL. Follow-up check should verify the project page and author affiliations before promoting to `labs.md`.

### NVIDIA / ProtoMotions signal
- Institution: NVIDIA Research / NVLabs
- GitHub: https://github.com/NVlabs/ProtoMotions
- Key Topics: humanoid / digital human simulation / motion imitation / retargeting / robot learning
- Notes: ProtoMotions3 remains a strong source to watch for humanoid robot learning infrastructure because it connects AMASS-scale motion imitation, robot retargeting, and multi-simulator policy evaluation.

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
- Notes: Official openings page still lists one Postdoc and one PhD student position for investigating and leveraging human locomotion neuromechanics using humanoid robots, numerical neuromechanical simulations, bio-inspired controllers, and reinforcement learning.

### Proposed Removal / Stale Item
- Current Status: none identified in this run
- Reason: No tracked job item was verified as expired during today's checks.
- Source Checked: EPFL BioRob official openings page and existing repository `jobs.md` context.

</details>
