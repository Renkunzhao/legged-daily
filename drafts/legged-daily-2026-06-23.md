**English** | [中文](../zh/drafts/legged-daily-2026-06-23.md)
# Legged Daily - 2026-06-23

## Summary
- Today has a strong arXiv batch for humanoid whole-body locomotion and loco-manipulation, with multiple June 19-22 submissions worth tracking.
- OpenHLM is the top humanoid VLA signal: it frames whole-body loco-manipulation as a reproducible recipe with teleoperation, VLA design, and heterogeneous co-training ablations.
- CoorDex is the top dexterous loco-manipulation signal: it releases an Isaac Lab codebase and checkpoints for Unitree G1 + Wuji hand continuous manipulation while walking.
- Go2-W long-distance navigation is a practical deployment signal: a DRL controller and autonomy stack reportedly completed about 2.8 km at Tsukuba Challenge 2025 without overheating stops.
- Repository watch adds CoorDex and keeps `g1_locomotion` as a useful classical-control G1 reference, with the important caveat that it is not hardware-tested.
- Opportunity watch: Chalmers RAIL is a lab to track for legged humanoid robotics openings; the official lab page states it welcomes PhD, postdoc, and master's thesis candidates, while a third-party Chalmers postdoc listing should be verified on the official vacancies page before adding as confirmed.

<details>
<summary><strong>New Papers</strong></summary>

### OpenHLM: An Empirical Recipe for Whole-Body Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.22174
- Source: arXiv
- Date: 2026-06-20
- Authors: Yingdong Hu, Haodong Zhu, Boyuan Zheng, Yihang Hu, Tong Zhang, Zunhao Chen, Junming Zhao, Ruiqian Nai, Yang Gao
- Topics: humanoid / loco-manipulation / VLA / whole-body teleoperation / co-training / language-conditioned control
- Summary: Presents OpenHLM as an open-source recipe for whole-body humanoid loco-manipulation, studying full-joint teleoperation, VLA adaptation to humanoid action spaces, and heterogeneous co-training; the project page reports 87.5% task progress on a long-horizon pick-and-place task using less than half the demonstration time of two humanoid VLA baselines.
- Notes: Strong candidate for tracking humanoid VLA systems that move beyond decoupled upper/lower-body control.

### CoorDex: Coordinating Body and Hand Priors for Continuous Dexterous Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.23680
- Source: arXiv
- Date: 2026-06-22
- Authors: Sikai Li, Shuning Li, Zhenyu Wei, Yunchao Yao, Chenran Li, Mingyu Ding
- Topics: humanoid / dexterous hands / loco-manipulation / reinforcement learning / latent priors / Unitree G1
- Summary: Introduces a coordinated latent-residual policy that composes frozen body and hand priors so a Unitree G1 with high-DoF hands can grasp, carry, open a fridge, and pick-turn objects while moving, avoiding the common stop-and-go loco-manipulation pattern.
- Notes: High signal because it includes a project page and released code/checkpoints for reproducible Isaac Lab rollouts.

### Long-Distance Real-World Navigation of the Legged-Wheeled Robot Go2-W Using Deep Reinforcement Learning
- Link: https://arxiv.org/abs/2606.21387
- Source: arXiv
- Date: 2026-06-19
- Authors: Takaaki Matsuzawa, Kiyoshi Irie, Tomoaki Yoshida, Taro Suzuki, Yoshitaka Hara, Masahiro Tomono
- Topics: legged-wheeled robot / Go2-W / DRL / real-world navigation / thermal robustness / autonomous deployment
- Summary: Extends a proprioception-only quadruped policy to the 16-DoF Unitree Go2-W and integrates it with an autonomy stack, reporting about 2.8 km autonomous traversal at Tsukuba Challenge 2025 across sidewalks, park terrain, and stairs without overheating-related stops.
- Notes: Useful practical signal for sustained legged-wheeled autonomy, including the observation that wheeled gait load distribution matters for hip-joint heating.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### Skevinci/coordex
- Link: https://github.com/Skevinci/coordex/tree/main
- Category: RL / loco-manipulation / simulator / checkpoints
- Robot Type: humanoid / Unitree G1 with Wuji hand
- Simulator: Isaac Sim 5.0 / Isaac Lab 2.2.0
- Deploy: sim / hardware demos referenced on project page
- Summary: Official CoorDex codebase with G1 Wuji loco-manipulation rollouts for WalkGrab, OpenFridge, and WalkPickTurn, including frozen body/hand priors, trained coordinated-residual policy checkpoints, Isaac Lab task configs, and rollout scripts.
- Notes: Strong repo candidate for the master list because it ships runnable tasks and checkpoints, not only paper media.

### ioloizou/g1_locomotion
- Link: https://github.com/ioloizou/g1_locomotion
- Category: MPC / whole-body inverse dynamics / simulator
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo
- Deploy: sim
- Summary: Master's-thesis locomotion stack for Unitree G1 combining single-rigid-body dynamics MPC with whole-body inverse dynamics in a linear cascaded control pipeline, with Docker/ROS launch instructions for a straight-line walking simulation.
- Notes: Useful as a classical-control reference beside learning-based G1 stacks; README explicitly states the implementation has not yet been tested on the physical robot.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### OpenHLM Project / Yang Gao group
- Institution: Tsinghua University ecosystem, based on project authorship; exact lab mapping should be verified before master-list insertion
- Homepage: https://openhlm-project.github.io/
- arXiv: https://arxiv.org/abs/2606.22174
- Key Topics: humanoid / VLA / whole-body teleoperation / loco-manipulation / heterogeneous co-training
- Notes: Project reports language-conditioned whole-body humanoid tasks, comparison against GR00T N1.6 and Psi_0, and public code/data/checkpoints availability via the project site.

### CoorDex Team / UNC Chapel Hill and UC Berkeley
- Institution: University of North Carolina at Chapel Hill; University of California, Berkeley
- Homepage: https://skevinci.github.io/coordex/
- GitHub: https://github.com/Skevinci/coordex/tree/main
- arXiv: https://arxiv.org/abs/2606.23680
- Key Topics: humanoid / dexterous hand / loco-manipulation / Isaac Lab / reinforcement learning / latent priors
- Notes: Strong follow-up source for dexterous humanoid loco-manipulation because the project includes both simulation rollout tasks and real-world G1 demos.

### Robot Athletic Intelligence Lab / Shivesh Kumar
- Institution: Chalmers University of Technology
- Homepage: https://chalmers-rail.github.io/
- Key Topics: underactuated robotics / legged machines / humanoids / optimal control / reinforcement learning / hardware-algorithm co-design
- Notes: Official lab page states RAIL develops physical and athletic intelligence for underactuated robots, legged machines, and humanoids, and lists open-position interest for PhD students, postdoctoral researchers, and master's thesis students.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Chalmers Robot Athletic Intelligence Lab (RAIL)
- Type: PhD / Postdoc / Master's thesis, plus possible specific postdoc opening to verify
- Location: Gothenburg, Sweden
- Source: official lab page; third-party job aggregator for the specific postdoc signal
- Deadline: unknown
- Topics: legged humanoid robotics / dynamic locomotion / optimal control / reinforcement learning / underactuated systems
- Status: watching / verify before confirmed addition
- Notes: The official RAIL page says the lab welcomes motivated PhD students, postdoctoral researchers, and master's thesis students. A third-party listing mentions a Chalmers postdoctoral researcher role in legged humanoid robotics, but the direct official Chalmers vacancy link was not verified during this run, so keep this as a watch item rather than a confirmed job entry.

### EPFL BioRobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: unknown
- Topics: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- Status: active
- Notes: Official openings page continues to list Fall 2026 PhD/Postdoc positions on investigating and leveraging human locomotion neuromechanics using humanoid robots.

</details>
