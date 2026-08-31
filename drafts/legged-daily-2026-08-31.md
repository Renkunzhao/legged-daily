**English** | [中文](../zh/drafts/legged-daily-2026-08-31.md)
# Legged Daily - 2026-08-31

## Summary
- Contact-Guided Exploration uses a decaying exploration critic to overcome sparse-contact exploration in quadrupedal non-prehensile locomanipulation; the RA-L work reports more than 90% simulated success and real ALMA chair-transport experiments.
- Stay Seated demonstrates zero-shot sim-to-real omnidirectional seated locomotion on a passive caster chair with Unitree G1, using proprioception and velocity commands without chair-state or contact observations in the actor.
- Three fresh Unitree G1 repositories expose complementary stacks for robust proprioceptive PPO locomotion, Isaac Sim navigation, and a safety-oriented carried-robot mode; their maturity and hardware evidence vary substantially.
- The paper set highlights active University of Pisa–ETH Zürich–NVIDIA collaboration on quadrupedal locomanipulation and a new humanoid locomotion direction from Takato Horii's Social Robotics Group at the University of Osaka.
- The Inria Auctus / LAAS-CNRS quadruped mechatronic whole-body co-design PhD reaches its official application deadline today, 2026-08-31.

<details>
<summary><strong>New Papers</strong></summary>

### Contact-Guided Exploration for Non-Prehensile Locomanipulation with Multi-Critic RL
- Link: https://arxiv.org/abs/2608.28140
- Source: RA-L / arXiv
- Date: 2026-08-28
- Authors: Simone Tolomei, Mayank Mittal, Franco Angelini, Manolo Garabini, Paolo Salaris, Marco Hutter
- Topics: quadruped, locomanipulation, non-prehensile manipulation, reinforcement learning, multi-critic learning, sim-to-real
- Summary: Introduces a dedicated contact-seeking exploration critic whose influence decays during training, allowing a quadrupedal mobile manipulator to first discover useful contacts and then optimize task performance; evaluations cover box pushing, chair transport, and dishwasher opening, with real ALMA chair-transport experiments.
- Notes: Accepted in IEEE Robotics and Automation Letters. The official project page reports over 90% success on both simulated benchmark tasks and zero-shot transfer to unseen IKEA furniture; hardware evidence is available on the project page: https://tolomeis.github.io/contact-guided-exp/

### Stay Seated: Learning Omnidirectional Humanoid Locomotion on a Passive Mobile Chair with Casters
- Link: https://arxiv.org/abs/2608.28090
- Source: arXiv
- Date: 2026-08-28
- Authors: Kango Yanagida, Kazuki Miyazawa, Takato Horii
- Topics: humanoid, seated locomotion, reinforcement learning, sim-to-real, Unitree G1, energy efficiency
- Summary: Extends velocity-tracking RL to unfixed humanoid–chair contact and intermittent foot propulsion, producing omnidirectional seated motion on a passive caster chair with an actor that observes only proprioception and commands; the authors report zero-shot transfer to a real Unitree G1.
- Notes: The paper analyzes symmetry, foot-slip regularization, and command curriculum across four seeds. The reported real-robot result is especially relevant as an early step toward seated loco-manipulation rather than conventional standing locomotion.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Humanoid_LocomotioN
- Link: https://github.com/shubhamt2897/Humanoid_LocomotioN
- Category: RL
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: A Unitree G1 PPO training stack with an asymmetric actor-critic, proprioceptive deployment observations, payload/friction/push randomization, contact and stability rewards, checkpoint playback, and ONNX export.
- Notes: The repository includes substantial Python implementation and G1 assets, but the current backend loops over CPU MuJoCo environments, procedural terrain is disabled by default, and no real-hardware deployment result is provided. No license was detected as of 2026-08-31.

### g1_isaac_nav
- Link: https://github.com/hyeonjin1998/g1_isaac_nav
- Category: toolkit
- Robot Type: humanoid
- Simulator: Isaac
- Deploy: sim
- Summary: Integrates a 29-DoF Unitree G1 in Isaac Sim with ROS 2 Humble, RTAB-Map localization, Nav2 navigation, simulated LiDAR/camera sensing, an ONNX walking policy, launch files, checks, and reproducible setup scripts.
- Notes: The maintainer reports mapping, navigation, and 0.118 m localization error in simulation and targets later sim-to-real transfer; no hardware deployment is claimed. The stack is documented in detail but requires Isaac Sim 5.1 and separate Unitree model assets. No license was detected as of 2026-08-31.

### Cargo-Mode
- Link: https://github.com/sissississi-013/Cargo-Mode
- Category: control
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: A hackathon prototype for detecting when a Unitree G1 is picked up, folding into a compact pose, applying selective impedance while carried, and safely handing control back after set-down through a guarded finite-state machine.
- Notes: Includes detector, simulation, dashboard, onboard control, and safety-layer code under the MIT License. The team's status file says all workstreams were verified in simulation, while real-robot access was blocked; treat its hardware runbook and deployment path as unvalidated.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### E. Piaggio Research Center / ETH Robotic Systems Lab collaboration
- Institution: University of Pisa / ETH Zürich / NVIDIA
- Homepage: https://tolomeis.github.io/contact-guided-exp/
- arXiv: https://arxiv.org/abs/2608.28140
- Lab / Department: Centro di Ricerca E. Piaggio, Department of Information Engineering / Robotic Systems Lab
- Key Topics: quadruped, locomotion, reinforcement learning, manipulation
- Notes: The new RA-L paper links Simone Tolomei, Franco Angelini, Manolo Garabini, and Paolo Salaris at Pisa with Mayank Mittal and Marco Hutter at ETH Zürich, plus NVIDIA affiliation. The collaboration is producing real-hardware ALMA results on contact-rich non-prehensile locomanipulation.

### Takato Horii / Social Robotics Group
- Institution: The University of Osaka
- Homepage: https://soro.sys.es.osaka-u.ac.jp/en/members/
- arXiv: https://arxiv.org/abs/2608.28090
- Lab / Department: Social Robotics Group, Department of Systems Innovation, Graduate School of Engineering Science
- Key Topics: humanoid, locomotion, robot learning, cognitive developmental robotics
- Notes: Horii is listed by the university as an associate professor. Stay Seated adds real Unitree G1 seated locomotion to a group otherwise known for social and cognitive-developmental robotics, making it a useful new humanoid robot-learning source to watch.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- Type: PhD
- Location: Talence / Bordeaux, France, with planned visits to Toulouse
- Source: official website — https://jobs.inria.fr/public/classic/en/offres/2026-10319
- Deadline: 2026-08-31
- Topics: quadruped, locomotion, reinforcement learning, robotics systems, manipulation
- Status: active
- Notes: Final application day. The project targets mechatronic whole-body co-design of a quadruped with localized compliance for locomanipulation, combining simulation-informed mechanism design, RL-based co-design, experimental calibration, and a full prototype. Planned start is 2026-10-01; listed remuneration is EUR 2,300 per month before tax.

</details>
