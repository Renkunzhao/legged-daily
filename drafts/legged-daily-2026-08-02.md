**English** | [中文](../zh/drafts/legged-daily-2026-08-02.md)
# Legged Daily - 2026-08-02

## Summary
- No new legged-robotics paper met the inclusion bar after the 2026-08-01 run. The arXiv `cs.RO` feed refreshed on 2026-08-02 still has the previously covered PAC-MAN submission from 2026-07-30 as its newest entry.
- Two repositories met the implementation bar: Yanshi RL Lab introduces a robot-profile abstraction plus deterministic Isaac Lab-to-MuJoCo acceptance gates across three humanoids, while `quadruped-gait` received substantive MPC, whole-body-control, and learned-policy deployment updates.
- No new primary-source lab or professor signal was verified today. Repository authorship alone was not treated as sufficient evidence for a new institutional source-network entry.
- No new opening met the novelty bar. ETH Zurich RSL's official page still advertises rolling legged-robotics PhD, PostDoc, research staff/software, robot-design, embedded, and electronics roles; the expired LAAS-CNRS safe-RL humanoid PhD remains a proposed stale removal pending confirmation.

<details>
<summary><strong>New Papers</strong></summary>

No new paper met the inclusion bar today.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### jeffliulab/yanshi-rl-lab
- Link: https://github.com/jeffliulab/yanshi-rl-lab
- Category: reinforcement learning / multi-robot benchmarking / sim-to-sim validation / reproducibility
- Robot Type: humanoid; Unitree G1, AgiBot Lingxi X2, Berkeley Humanoid Lite
- Simulator: NVIDIA Isaac Lab 2.3.2 for training; MuJoCo for deterministic replay and acceptance gates
- Deploy: simulation and sim-to-sim only; no physical-robot deployment is demonstrated
- Summary: A newly published MIT-licensed framework that represents each humanoid as a vendor profile, trains locomotion policies in Isaac Lab, exports them to ONNX, and requires them to pass declarative MuJoCo gates before being treated as results.
- Notes: The repository includes CPU-only profile/contract/gate tests, pinned external asset references, rough-terrain task scaffolding, and initial single-seed benchmark results for three materially different humanoids. Its strongest contribution is methodological rather than a new controller: cross-engine replay and YAML-defined thresholds make portability failures and changed evaluation criteria visible. The maintainers explicitly mark multi-seed baselines as future work.

### takarakasai/quadruped-gait
- Link: https://github.com/takarakasai/quadruped-gait
- Category: model-based control / gait generation / MPC / whole-body control / state estimation / Rust robotics
- Robot Type: quadruped; designed as a reusable locomotion stack and consumed by the author's Articara / Go2 tooling
- Simulator: simulator-independent libraries; MuJoCo walk-regression lives in the related `articara` repository
- Deploy: includes a policy-runtime deployment path, but no new physical-robot result was verified in today's update
- Summary: An Apache-2.0 Rust stack combining CHAMP-style gait generation, SRBD/centroidal/full-centroidal MPC, hierarchical whole-body control, and legged state estimation, with several substantive control and deployment commits on 2026-08-02.
- Notes: Today's commits added a deployment path for a learned Bound policy, corrected yaw-footstep moment arms and horizon phase projection in MPC, and added an optional minimum normal force for commanded-stance feet. The repository reports CI and coverage, while behavioral MuJoCo regression is intentionally maintained in a downstream consumer repository.

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
- Status: active at verification; previously tracked opportunity, not a new master-list addition
- Notes: The official page continues to expose application links and lists multiple roles spanning research and robot-system engineering. This is a status check rather than a novel opening.

### Proposed Removal / Stale Item — LAAS-CNRS Gepetto Team PhD in Humanoid Robotics: Safe Reinforcement Learning
- Current Status: expired / past the listed application deadline
- Reason: The official posting's 2026-07-31 23:59 deadline has passed. Keep the proposed removal visible until the corresponding active master-list entry is explicitly confirmed for removal.
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
