**English** | [中文](../zh/drafts/legged-daily-2026-06-11.md)
# Legged Daily - 2026-06-11

## Summary
- Today's strongest theme is humanoid whole-body and loco-manipulation learning: OMG targets omni-modal generalist Unitree G1 control, while OASIS targets simulation-data-driven real-world humanoid loco-manipulation.
- A compact new ICRA 2026 workshop paper highlights critic architecture as a concrete design variable for multi-objective humanoid RL, reporting stronger reaching efficiency from dual critics than a unified critic on Unitree G1 in Isaac Lab.
- Repository signals are implementation-heavy: OASIS released data-collection code/assets, LeggedGym-Ex remains an actively updated multi-simulator legged-RL framework, and NeuroGait is a new Isaac Lab quadruped locomotion benchmark/template but appears early-stage.
- Lab/source signals worth tracking include Tsinghua MARS Lab for humanoid motion-generation foundation models and the TeleHuman/OASIS project line for simulation-first humanoid loco-manipulation data collection.
- Job checks found Field AI's official Lever board listing new humanoid manipulation research roles in Boston, while EPFL BioRob and ETH RSL official openings remain active.

<details>
<summary><strong>New Papers</strong></summary>

### OMG: Omni-Modal Motion Generation for Generalist Humanoid Control
- Link: https://arxiv.org/abs/2606.10340
- Source: arXiv
- Date: 2026-06-09
- Authors: Siqiao Huang, Kun-Ying Lee, Dongming Qiao, Guanqi He, Zhenyu Wang, Yitang Li, Shaoting Zhu, Hang Zhao
- Topics: humanoid / whole-body control / motion generation / diffusion model / foundation model / Unitree G1
- Summary: Proposes OMG, a generator-tracker hierarchy for generalist humanoid control where a diffusion-based motion generator conditions on language, audio, human reference motion, and motion history, then a pretrained tracker executes the resulting whole-body trajectories on Unitree G1.
- Notes: Project page: https://tsinghua-mars-lab.github.io/OMG/ . The page reports a 1174.66-hour omni-modal humanoid motion corpus retargeted/aligned to Unitree G1 and emphasizes extensible control modalities; code release was not clearly verified from the project page.

### OASIS: From Simulation Data Collection to Real-World Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.08548
- Source: arXiv
- Date: 2026-06-07
- Authors: Zehao Yu, Jiakun Zheng, Weiji Xie, Jiyuan Shi, Chenyun Zhang, Chenjia Bai, Xuelong Li
- Topics: humanoid / loco-manipulation / simulation data / teleoperation / domain randomization / visuomotor policy
- Summary: Introduces OASIS, a simulation-data-driven framework that reconstructs realistic object assets from images, collects humanoid loco-manipulation trajectories by teleoperation in simulation, applies domain randomization, and trains a hierarchical visuomotor policy that transfers to real humanoid deployment.
- Notes: Project page: https://oasis-humanoid.github.io/ . Official repository: https://github.com/TeleHuman/OASIS . Relevant as a simulation-data counterpart to recent real-teleoperation and synthetic-data humanoid manipulation pipelines.

### Critic Architecture Matters: Dual vs. Unified Critics for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.11891
- Source: arXiv / ICRA 2026 Workshop on Reinforcement Learning for Imitation Learning
- Date: 2026-06-10
- Authors: Mehmet Turan Yardımcı
- Topics: humanoid / loco-manipulation / reinforcement learning / critic architecture / Isaac Lab / Unitree G1
- Summary: Compares unified versus dual critic architectures for Unitree G1 loco-manipulation RL in Isaac Lab, reporting that dual critics reach targets 3.5x faster, double validated reaching throughput, and outperform extra anti-gaming reward mechanisms.
- Notes: Short workshop paper, but useful because it isolates critic architecture as a practical training-design variable for multi-objective humanoid RL and RL fine-tuning of imitation-learned policies.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### OASIS
- Link: https://github.com/TeleHuman/OASIS
- Category: dataset / toolkit / simulator / teleoperation
- Robot Type: humanoid
- Simulator: Isaac Lab / Isaac Sim
- Deploy: both
- Summary: Official OASIS repository for simulation-based humanoid loco-manipulation data collection, including Isaac Lab setup, scene/object assets, PICO-based teleoperation workflow, trajectory replay, and domain-randomized rendering.
- Notes: Created 2026-06-07 and README says OASIS was released in 2026-06 with data-collection code, assets, and paper; depends on GMR, PICO SDK, unitree_sim_isaaclab, TWIST2, and Teleopit.

### LeggedGym-Ex
- Link: https://github.com/lupinjia/LeggedGym-Ex
- Category: RL / simulator / toolkit
- Robot Type: humanoid / quadruped / general
- Simulator: IsaacGym / Genesis / IsaacSim
- Deploy: both
- Summary: legged_gym-based framework for training legged robots across IsaacGym, Genesis, and IsaacSim, with examples for Unitree Go2, Unitree G1, Booster K1, and TRON1 variants plus implementations of multiple published RL methods.
- Notes: Actively updated in June 2026; README lists support for warp-based depth rendering/height query, DeepMimic, AMP, teacher-student, system ID, and several sim-to-real robot demos. This is not a brand-new repo but is a high-signal active toolkit.

### NeuroGait
- Link: https://github.com/Tanishq-C-Saha/NeuroGait
- Category: RL / simulator / benchmark
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: New Isaac Lab extension described as benchmarking and terrain-adaptive reinforcement learning for Unitree Go2 quadruped locomotion.
- Notes: Created 2026-06-06. The GitHub description is relevant, but the README still mostly follows the Isaac Lab extension template, so treat this as an early-stage watch item rather than a mature benchmark.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Tsinghua MARS Lab / OMG project
- Institution: Tsinghua University
- Homepage: https://tsinghua-mars-lab.github.io/OMG/
- Lab / Department: MARS Lab, Tsinghua University
- Key Topics: humanoid / whole-body control / motion generation / multi-modal conditioning / Unitree G1 / robot foundation models
- Notes: OMG is a clear signal that this group is working on scalable humanoid motion generation: the project page presents a generator-tracker hierarchy, OMG-DiT diffusion backbone, and 1174.66-hour Unitree G1-aligned omni-modal motion corpus. Track for code/data release and follow-up generalist humanoid control work.

### TeleHuman / OASIS project line
- Homepage: https://oasis-humanoid.github.io/
- GitHub: https://github.com/TeleHuman/OASIS
- Key Topics: humanoid / loco-manipulation / simulation data collection / teleoperation / domain randomization / real-world transfer
- Notes: OASIS released a public repository in June 2026 for simulation-data-driven humanoid loco-manipulation. The source is useful to track alongside GRAIL, SIMPLE, EgoHumanoid, and other humanoid manipulation-data pipelines; institutional affiliation was not verified from the project page in this pass.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Field AI
- Type: Research Engineer / Internship
- Location: Boston, MA, USA
- Source: official Lever careers page
- Deadline: unknown
- Topics: humanoid manipulation / loco-manipulation / embodied intelligence / robot learning / real hardware
- Status: active
- Notes: Official postings include “Senior Research Engineer – Humanoid Manipulation” and “Robotics Research Internship, Humanoid Manipulation (Summer 2026) | PhD Internship.” The roles emphasize humanoid manipulation capabilities, loco-manipulation, real robotic systems, foundation-model-adjacent robot learning, and applied deployment. Sources: https://jobs.lever.co/field-ai/1ae59c17-eabd-4e36-a2c2-e9ac96ba0f85 and https://jobs.lever.co/field-ai/2a2c8f00-3a28-481b-882c-33cb0ec4a3a0

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: Official openings page still lists one Postdoc and one PhD position for investigating and leveraging human locomotion neuromechanics using humanoid robots, numerical neuromechanical simulation, bio-inspired controllers, and reinforcement learning. Source: https://www.epfl.ch/labs/biorob/openings/

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: Official RSL page continues to list rolling PhD, postdoc, research staff/software engineer, robot design, and embedded-systems roles connected to legged robots, mobile manipulation, control, learning, planning, and deployment. Source: https://rsl.ethz.ch/the-lab/open-positions.html

</details>
