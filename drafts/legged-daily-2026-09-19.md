**English** | [中文](../zh/drafts/legged-daily-2026-09-19.md)
# Legged Daily - 2026-09-19

## Summary
- SGPS combines sampling-based MPC, behavior-cloning initialization, and first-order gradients through MJX to train state and depth-based policies for Go2, H1, and G1; the authors report zero-shot onboard-depth deployment on a real Go2.
- OmniMimic expands directionally narrow animal demonstrations into one omnidirectional four-gait policy through dynamics-completed augmentation and progressive command expansion, with direct Unitree Go2 sim-to-real demonstrations.
- DR-MPC relaxes dynamics and affine input relations into penalties, retains nonempty box constraints, and uses a tailored interior-point solver; the authors report 4.4 ms median onboard MPC time on Unitree Go1.
- Two research releases need different labels: SGPS is a substantive MuJoCo MJX training implementation, while OmniMimic's repository is explicitly a project/demo website rather than policy-training code.
- A newly created experimental C++ library from Adorno Lab wraps Unitree SDK2 across locomotion, G1 arm/waist, low-level joints, and state/IMU access, but is a reusable component rather than a complete robot driver.
- NVIDIA's official careers site exposes a new “Machine Learning Engineer - Humanoid Robotics” title page; the fetched page did not expose location or detailed requirements, so it remains a watching signal pending fuller verification.

<details>
<summary><strong>New Papers</strong></summary>

### Accelerating Visual Policy Learning with Sampling-Based Model Predictive Control
- Link: https://arxiv.org/abs/2609.20575
- Source: arXiv
- Date: 2026-09-17
- Authors: Yilang Liu, Haoxiang You, Qian Wang, Daniel Rakita, Ian Abraham
- Topics: visual locomotion / sampling-based MPC / differentiable simulation / first-order policy gradients / sim-to-real
- Summary: Sampling-Guided Policy Search repeatedly refines action targets with sampling-based MPC and optimizes policies through MuJoCo MJX dynamics, enabling direct depth-policy training without a privileged state-policy teacher.
- Notes: The paper covers locomotion, obstacle traversal, crate pushing, and bimanual carrying on simulated Unitree Go2 and G1 robots. The authors report single-GPU training and zero-shot transfer of one visual Go2 policy that trots, crawls, clears hurdles, and switches behaviors using onboard depth; results were not independently reproduced in this review.

### OmniMimic: Dynamics-completed Motion Augmentation for Multi-style Omnidirectional Quadruped Locomotion
- Link: https://arxiv.org/abs/2609.20566
- Source: arXiv
- Date: 2026-09-17
- Authors: Sheng Wu, Guoqiang Zhao, Zhe Yang, Fei Teng, Zhikun Zhou, Zheng Fang, Hong Zheng, Yaonan Wang, Kailun Yang
- Topics: quadruped locomotion / motion imitation / multi-gait control / reinforcement learning / sim-to-real
- Summary: OmniMimic converts directionally limited animal demonstrations into robot-specific reversed and reflected supervision, then progressively expands commands while using gait-specialized residual experts inside one omnidirectional policy.
- Notes: Evaluated on trot, pace, canter, and pronk, the authors report 12.9% lower foot-position RMSE and 63.1% lower command-grid velocity-tracking RMSE than a matched APEX baseline, plus direct deployment on Unitree Go2 without fine-tuning. The public project repository contains demos, not training code.

### DR-MPC: Fast and Feasible Dynamics-Relaxed Model-Predictive Control for Legged Locomotion
- Link: https://arxiv.org/abs/2609.20035
- Source: arXiv
- Date: 2026-09-17
- Authors: Run Wang, Alapati Tuerxun, Shuo Liu, Wei Xiao, Ján Drgoňa, Yilin Mo, Liang Wu
- Topics: quadruped locomotion / model predictive control / quadratic programming / real-time optimization / hardware control
- Summary: DR-MPC moves approximate dynamics and affine input relations into quadratic penalties, preserves only nonempty box constraints, and exploits the resulting block-arrow structure with a tailored interior-point solver.
- Notes: Using the same DR-MPC formulation, the authors report median end-to-end speedups of 16.0× over HPIPM and 4.4× over OSQP, a 4.4 ms median onboard MPC update, and Unitree Go1 hardware validation. The paper says code will be released after publication; no official implementation was found today.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### YilangLiu/Sampling-Guided-Policy-Search
- Link: https://github.com/YilangLiu/Sampling-Guided-Policy-Search
- Category: RL / MPC / control / toolkit
- Robot Type: quadruped / humanoid
- Simulator: MuJoCo MJX
- Deploy: sim / hardware
- Summary: Official SGPS implementation coupling DIAL-MPC reference generation and recurring refinement with behavior-cloning warm starts and first-order policy optimization through MJX for Go2, H1, and G1 tasks.
- Notes: The repository documents state and egocentric-depth pipelines, locomotion and obstacle tasks, G1 crate pushing, task YAMLs, reference verification, and training entry points. Robot models are vendored, but generated references and checkpoints are not; GitHub metadata exposed no declared license when checked.

### Adorno-Lab/unitree_drivers
- Link: https://github.com/Adorno-Lab/unitree_drivers
- Category: toolkit / control / hardware interface
- Robot Type: humanoid / quadruped / general Unitree lineup
- Simulator: none
- Deploy: hardware
- Summary: Experimental C++17, pImpl-based wrappers around Unitree SDK2 for high-level locomotion, G1 arm/waist control, low-level joint commands, and state/IMU telemetry.
- Notes: The library builds three reusable CMake targets and depends on Unitree SDK2, Eigen3, and DQ Robotics. Its documentation explicitly says it is a building block for higher-level facades or robot drivers, not a complete driver; the repository is LGPL-2.1 and was created on 2026-09-18.

### OmniMimic/OmniMimic.github.io
- Link: https://github.com/OmniMimic/OmniMimic.github.io
- Category: viewer / project page
- Robot Type: quadruped
- Simulator: none
- Deploy: browser / hardware demos
- Summary: Official OmniMimic project-site repository hosting simulation results and Unitree Go2 videos for trot, pace, canter, and pronk under omnidirectional commands.
- Notes: This is a dependency-free GitHub Pages and media-preparation repository. Its README explicitly states that it hosts the website only and is not a release of the policy-training implementation; no declared license was exposed in GitHub metadata when checked.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Yale University / University of Sydney — SGPS collaboration
- Institution: Yale University / University of Sydney
- arXiv: https://arxiv.org/abs/2609.20575
- GitHub: https://github.com/YilangLiu/Sampling-Guided-Policy-Search
- Lab / Department: Yale Mechanical Engineering and Computer Science; University of Sydney Electrical and Computer Engineering
- Key Topics: sampling-based MPC / differentiable simulation / visual locomotion / loco-manipulation / sim-to-real
- Notes: Yilang Liu, Haoxiang You, Qian Wang, Daniel Rakita, and Ian Abraham connect sampling-based planning, differentiable policy learning, and direct visual-policy deployment across Go2 and G1. The unusually complete repository makes this a useful source network for compute-efficient contact-rich policy learning.
- Students and Representative Works:
  - [Yilang Liu](https://github.com/YilangLiu) — [Sampling-Guided Policy Search](https://github.com/YilangLiu/Sampling-Guided-Policy-Search)

### Kailun Yang / Hunan University — OmniMimic collaboration
- Institution: Hunan University / China Mobile Group Hunan Company
- Homepage: https://omnimimic.github.io/
- arXiv: https://arxiv.org/abs/2609.20566
- GitHub: https://github.com/OmniMimic/OmniMimic.github.io
- Lab / Department: School of Artificial Intelligence and Robotics; National Engineering Research Center of Robot Visual Perception and Control Technology
- Key Topics: quadruped locomotion / motion imitation / expressive multi-gait control / reinforcement learning / sim-to-real
- Notes: Sheng Wu, Kailun Yang, and collaborators are a new source signal around learning expressive quadruped motion from animal demonstrations while preserving broad command following and hardware transfer. Follow-up value depends on whether the promised research line later releases training code or motion data.
- Students and Representative Works:
  - [Sheng Wu](https://arxiv.org/abs/2609.20566) — [OmniMimic](https://omnimimic.github.io/)

### Tsinghua University / Johns Hopkins University — DR-MPC collaboration
- Institution: Tsinghua University / Johns Hopkins University / Boston University / Nanyang Technological University
- arXiv: https://arxiv.org/abs/2609.20035
- Lab / Department: Tsinghua Department of Automation and cross-institution control/optimization collaboration
- Key Topics: legged MPC / real-time optimization / QP solvers / contact-aware control / hardware deployment
- Notes: Run Wang, Liang Wu, Yilin Mo, Ján Drgoňa, and collaborators provide a high-relevance model-based-control signal centered on co-designing an MPC formulation, contact-aware parameterization, and solver for onboard timing and feasibility. The planned post-publication code release is worth monitoring.
- Students and Representative Works:
  - [Run Wang](https://arxiv.org/abs/2609.20035) — [DR-MPC](https://arxiv.org/abs/2609.20035)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### NVIDIA — Humanoid Robotics
- Type: Machine Learning Engineer
- Source: official careers page — https://jobs.nvidia.com/careers/job/893394875865?domain=nvidia.com
- Deadline: unknown
- Topics: humanoid / machine learning / robot learning
- Status: watching
- Notes: NVIDIA's official careers endpoint currently exposes the title “Machine Learning Engineer - Humanoid Robotics.” The fetched page did not expose location, responsibilities, or application deadline, so this is recorded as a high-relevance watching signal rather than a fully verified active opening; recheck the detailed posting before adding it to the formal jobs list.

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team, PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / no longer actionable
- Reason: The application deadline was 2026-07-31, and the official CNRS portal now states that the offer is no longer available. This removal was proposed in the 2026-09-17 draft and remains pending confirmation.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
