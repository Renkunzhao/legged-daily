**English** | [中文](../zh/drafts/legged-daily-2026-08-08.md)
# Legged Daily - 2026-08-08

## Summary
- No new paper met the inclusion bar today. Saturday's arXiv robotics listing still ends with the 2026-08-07 batch, whose strongest legged and humanoid items were already covered in yesterday's draft.
- One newly created repository is worth cautious tracking: `ROS2-Quadruped-Locomotion-Control` publishes a substantial, MIT-licensed ROS 2 Jazzy and Gazebo Harmonic model-based control stack for Unitree Go2.
- The repository is unusually explicit about validation boundaries: stable standing and four-contact wrench allocation are validated, but repeated static transfer is still in progress, forward locomotion is blocked, and hardware deployment is future work.
- No new high-confidence lab or professor update was selected. Amazon Robotics Compass's official Safe Locomotion role remains active and is still the strongest verified opportunity signal pending confirmation for master-list addition.

<details>
<summary><strong>New Papers</strong></summary>

No new paper met the inclusion bar today. The latest arXiv `cs.RO` batch remains dated 2026-08-07, and its selected legged/humanoid papers were already included in the 2026-08-07 draft.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### AREIVAN/ROS2-Quadruped-Locomotion-Control
- Link: https://github.com/AREIVAN/ROS2-Quadruped-Locomotion-Control
- Category: control / toolkit
- Robot Type: quadruped
- Simulator: Gazebo Harmonic
- Deploy: sim
- Summary: MIT-licensed model-based quadruped locomotion framework for ROS 2 Jazzy, using Unitree Go2 as the reference platform and connecting command velocity to gait/contact scheduling, support geometry, body-wrench control, contact-force distribution, stance/swing planning, inverse kinematics, and `ros2_control` joint commands.
- Notes: Created on 2026-08-07. The repository includes robot description, simulation packages, control documentation, and tests, but explicitly states that it is unfinished: stable standing and four-contact wrench allocation are validated, single-leg liftoff is partial, repeated static transfer remains in progress, forward locomotion is blocked on that milestone, and hardware deployment is future work. It had zero stars and no independent validation at verification time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new high-confidence lab or professor signal was selected today. Previously identified source networks are not repeated without a material new publication, release, personnel update, or official announcement.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-08 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role develops and deploys RL controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms, integrating formal safety mechanisms, sim-to-real pipelines, and model-based whole-body control. No newly posted, higher-confidence opportunity surpassed this verified active signal today.

</details>
