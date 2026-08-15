**English** | [中文](../zh/drafts/legged-daily-2026-08-15.md)
# Legged Daily - 2026-08-15

## Summary
- No new high-signal legged-robotics paper was selected from the post-2026-08-14 search window; the arXiv `cs.RO` date query returned no new records for August 14-15 at run time.
- Three compact repositories stood out: a CPU-only SONIC whole-body tracking bundle for AgiBot X2 Ultra, a two-track Unitree Go2 MuJoCo / Isaac Lab locomotion stack, and an adversarial height-scan benchmark for a frozen Go2 locomotion policy.
- The strongest reproducibility signal is `go2-mujoco-control`, which includes model-based control, Isaac Lab RL, a downloadable checkpoint, tests, experiment artifacts, and explicit upstream/licensing notes.
- No new high-confidence lab/professor addition was found. ETH Zurich RSL's official page was re-verified and continues to list rolling legged-robotics-related research and engineering openings.

<details>
<summary><strong>New Papers</strong></summary>

No new paper was selected today. The focused arXiv `cs.RO` query for records submitted on 2026-08-14 through 2026-08-15 returned zero results at run time, and broader searches did not surface a sufficiently recent, legged-specific paper that cleared the verification bar.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### sonic-x2
- Link: https://github.com/meetsitaram/sonic-x2
- Category: control / motion tracking / viewer
- Robot Type: humanoid — AgiBot X2 Ultra, 31 DoF
- Simulator: MuJoCo
- Deploy: sim / deployment-parity configuration
- Summary: A CPU-only quick-play bundle for running a SONIC whole-body tracking policy in MuJoCo, including the ONNX policy, X2 Ultra model, walk/idle/dance reference motions, tracking metrics, and real-deployment tuning presets.
- Notes: Created 2026-08-14. The repository reports a 50 Hz policy with 1670-D observations and 31-D actions; it is a community bundle rather than an identified official AgiBot release, and no repository-level license was declared at check time.

### go2-mujoco-control
- Link: https://github.com/kairoi-k/go2-mujoco-control
- Category: control / MPC / RL / simulator
- Robot Type: quadruped — Unitree Go2
- Simulator: MuJoCo / Isaac Lab
- Deploy: sim
- Summary: A research fork of Unitree MuJoCo combining a 500 Hz model-based stand-walk-lie controller and diagonal trot with a separate Isaac Lab velocity-RL track.
- Notes: Includes Raibert footstep planning, contact-force allocation, an incremental 18-DoF ID-WBC + SRBD-MPC path, tests, experiment artifacts, an RL checkpoint release, reproducibility documentation, and BSD-3-Clause upstream licensing notes. Hardware deployment is not claimed.

### Go2_heightscan_adversary_retrain
- Link: https://github.com/JasonSDC/Go2_heightscan_adversary_retrain
- Category: RL / robustness benchmark / adversarial observations
- Robot Type: quadruped — Unitree Go2
- Simulator: Isaac Sim / Isaac Lab
- Deploy: sim
- Summary: A reproducible snapshot for attacking a frozen Go2 locomotion policy through its 187-cell terrain height scan, with MLP and LSTM victims, an adversary checkpoint, evaluation scripts, and reported fall-rate comparisons.
- Notes: Created 2026-08-15. The current tree contains attack and evaluation assets, but adversarial victim retraining is explicitly described as the next step rather than completed functionality; no repository-level license was declared at check time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new high-confidence lab or professor signal was selected today. The new repository authors did not expose enough verified institutional context to justify a source-network addition.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official website — https://rsl.ethz.ch/the-lab/open-positions.html
- Deadline: rolling / unknown
- Topics: legged robots / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: Re-verified on 2026-08-15. The official page continues to list rolling research and engineering openings tied to legged robots, mobile manipulators, field deployment, control, learning, planning, perception, and robot hardware. This is an update to an existing tracked entry, not a proposed new master-list addition.

No new high-confidence recruiting addition or stale-item removal was identified today.

</details>
