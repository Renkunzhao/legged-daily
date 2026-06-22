**English** | [中文](../zh/drafts/legged-daily-2026-06-22.md)
# Legged Daily - 2026-06-22

## Summary
- Monday arXiv has not yet produced a newer legged-robotics batch than the verified June 17-18 submissions, so today focuses on high-signal items not already highlighted in the latest drafts.
- Active-toe biped hardware is the strongest paper signal: a 14-DoF biped study quantifies toe effects on agility, efficiency, and impact absorption in a high-fidelity actuator-aware simulation environment.
- Proprioceptive state estimation on non-inertial ground is a useful humanoid robustness signal, especially for moving platforms where external ground-motion sensing is unavailable.
- ZiMPedance adds a payload-stability angle for quadrupeds, extending ZMP analysis to passive spring-damper load interfaces and validating with hardware experiments.
- Repository watch: StepIt is a small but active framework for connecting legged robots, input devices, and learning-based controllers; a Unitree G1 MuJoCo MPC/WBC environment is worth previewing as a classical-control reference.
- Opportunity watch remains active: EPFL BioRob has Fall 2026 humanoid neuromechanics PhD/Postdoc openings; ETH RSL continues to list rolling legged-robotics PhD/Postdoc/research staff/engineering roles.

<details>
<summary><strong>New Papers</strong></summary>

### Comparative Study on Agility, Efficiency, and Impact Absorption of Bipedal Robots with Active Toes
- Link: https://arxiv.org/abs/2606.19699
- Source: arXiv
- Date: 2026-06-18
- Authors: Joong-Gil Kim, Wontae Ye, Geunwoo Cho, Seong-Ho Yun, Se-Hyoung Cho, Yong-Jae Kim
- Topics: biped / active toes / hardware design / locomotion / agility / efficiency / impact absorption
- Summary: Proposes a 14-DoF biped robot with lightweight high-torque active toes and evaluates toe benefits through a high-fidelity simulation environment that models real actuators, coupled transmissions, and power consumption for fair comparisons across toe configurations.
- Notes: Good candidate for tracking foot/toe morphology as a locomotion-performance lever rather than treating feet as passive contact geometry.

### Proprioceptive Invariant State Estimation for Humanoid Robots on Non-Inertial Ground
- Link: https://arxiv.org/abs/2606.19512
- Source: arXiv
- Date: 2026-06-17
- Authors: Falak Mandali, Zijian He, Yan Gu
- Topics: humanoid / state estimation / invariant EKF / proprioception / moving ground / non-inertial environments
- Summary: Presents a proprioceptive InEKF for humanoids on moving or non-inertial ground, estimating base position and velocity relative to the moving ground frame using onboard sensing and stance-foot kinematic constraints without direct ground-motion measurements.
- Notes: Relevant to humanoid deployment on ships, elevators, vehicles, and other moving support surfaces where external tracking or fixed-world assumptions break down.

### ZiMPedance: Impedance-Aware ZMP Modeling and Control for Payload Carrying with Quadruped Robots
- Link: https://arxiv.org/abs/2606.18883
- Source: arXiv
- Date: 2026-06-17
- Authors: Giovanni B. Dessy, Lorenzo Amatucci, Victor Barasuol, Claudio Semini
- Topics: quadruped / payload carrying / impedance / ZMP / MPC / passive arms / stability
- Summary: Extends Zero Moment Point modeling for quadruped payload transport by including passive spring-damper payload-interface dynamics, showing how stiffness, damping, and load mass affect stability margins and using the analysis to improve controller design.
- Notes: Useful for applications where quadrupeds carry loads through lightweight passive interfaces rather than fully actuated manipulators.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### chengruiz/stepit
- Link: https://github.com/chengruiz/stepit
- Category: toolkit / control / RL / input interface
- Robot Type: legged / general
- Simulator: none
- Deploy: hardware
- Summary: Active C++ framework for connecting legged robots, input devices, and control algorithms, especially learning-based policies, with plugin-style components for control console, joystick interfaces, robot interfaces, state machines, and replay utilities.
- Notes: README marks the project as under active development with unstable interfaces; related policies/configurations are referenced via `stepit_zoo`.

### matteogoddi/labrob_mujoco_environment
- Link: https://github.com/matteogoddi/labrob_mujoco_environment
- Category: MPC / whole-body control / simulator
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo
- Deploy: sim
- Summary: MuJoCo-based Unitree G1 walking environment built around an offline footstep planner, EKF state estimation, IS-MPC center-of-mass trajectory generation, and whole-body control for reference tracking and contact/kinematic constraints.
- Notes: Small research/teaching-style repository, but useful as a readable classical-control baseline for G1 locomotion experiments.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Yonsei Bio-inspired Robotics Laboratory / Yonsei University
- Institution: Yonsei University
- arXiv: https://arxiv.org/abs/2606.19699
- Key Topics: biped / active toes / bio-inspired mechanisms / locomotion efficiency / impact absorption
- Notes: Active-toe biped work is a useful hardware-design signal around how foot morphology changes locomotion agility, energy use, and landing robustness.

### West Virginia University Interactive Robotics Laboratory
- Institution: West Virginia University
- arXiv: https://arxiv.org/abs/2606.19512
- Key Topics: humanoid / state estimation / invariant filtering / non-inertial locomotion / proprioception
- Notes: The non-inertial-ground humanoid estimator extends prior legged state-estimation tracking toward moving support surfaces and proprioception-only assumptions.

### Dynamic Legged Systems Lab / Istituto Italiano di Tecnologia
- Institution: Istituto Italiano di Tecnologia
- Homepage: https://www.iit.it/research/lines/dynamic-legged-systems
- arXiv: https://arxiv.org/abs/2606.18883
- Key Topics: quadruped / payload transport / impedance / MPC / ZMP / dynamic locomotion
- Notes: ZiMPedance is another signal from the IIT legged systems ecosystem around payload-aware quadruped locomotion and practical controller design.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: unknown
- Topics: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- Status: active
- Notes: Official openings page lists one Postdoc and one PhD position for Fall 2026 on investigating and leveraging human locomotion neuromechanics using humanoid robots; PhD applicants must first be accepted by an EPFL doctoral program.

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / teleoperation / actuation and system design
- Status: active
- Notes: Official RSL openings page continues to list rolling positions spanning legged robots, mobile manipulators, real-world deployments, robot design, embedded systems, and electronics.

</details>
