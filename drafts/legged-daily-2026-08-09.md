**English** | [中文](../zh/drafts/legged-daily-2026-08-09.md)
# Legged Daily - 2026-08-09

## Summary
- No new paper met the inclusion bar today. The official arXiv `cs.RO` new-submission page still ends with the Friday, 2026-08-07 batch, whose selected legged and humanoid papers were already covered.
- DUET is today's strongest release: a newly public Apache-2.0 Unitree G1 stack decouples a lower-body locomotion policy from externally supplied arm targets, and includes MuJoCo-Warp training, ablations, an exported checkpoint, a C++ hardware controller, and bridges for GR00T N1.7 and π0.5.
- `Livox_MID360_IsaacSim` is a useful new humanoid-perception asset release for Isaac Sim 5.1, providing MIT-licensed MID-360 Petal and Rotary scan profiles plus ROS 2-enabled Unitree G1 4010/5010 USD assets and reproducible validation scenes.
- Both repositories are very new and had little or no community validation at verification time. No new institution-backed lab/professor signal was selected; Amazon Robotics Compass's official Safe Locomotion role remains active and pending confirmation for master-list addition.

<details>
<summary><strong>New Papers</strong></summary>

No new paper met the inclusion bar today. The official arXiv `cs.RO` new-submission page still shows Friday, 2026-08-07 as its latest batch, and the selected legged/humanoid papers from that batch were already included in the 2026-08-07 draft.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### bae-air-lab/DUET
- Link: https://github.com/bae-air-lab/DUET
- Category: RL / control / loco-manipulation / deployment
- Robot Type: humanoid
- Simulator: MuJoCo Warp / mjlab
- Deploy: both
- Summary: Apache-2.0 Unitree G1 framework that trains a 13-action lower-body policy for velocity, turning, and pelvis-height tracking while accepting arm targets from an independent process, allowing separately trained VLA policies to manipulate without retraining or coordinating with the locomotion policy.
- Notes: Initial public release on 2026-08-09. The repository includes the DUET task, whole-body baseline, ablations, training and evaluation scripts, a deployed checkpoint and ONNX export with an explicit deployment contract, a C++ hardware controller, and bridges for GR00T N1.7 and π0.5. The README shows a hardware demonstration, but no matching paper/preprint or institutional affiliation was independently verified today; the repository had zero stars at verification time.

### 123tthh/Livox_MID360_IsaacSim
- Link: https://github.com/123tthh/Livox_MID360_IsaacSim
- Category: simulator / sensor assets / toolkit
- Robot Type: humanoid
- Simulator: Isaac Sim 5.1
- Deploy: sim
- Summary: MIT-licensed Livox MID-360 simulation and ROS 2 asset package with separate non-repetitive Petal and deterministic Rotary scan profiles, each supplied as standalone LiDAR and sensor-equipped Unitree G1 4010, G1 5010 Mode13, and G1 5010 Mode15 USD assets.
- Notes: Created on 2026-08-08 and substantively validated on 2026-08-09. It uses the official four-second Livox direction trajectory for the Petal profile, publishes 200,000 points/s through ROS 2, documents mounts and extrinsics, and includes reproducible object-field, RViz2, and stair-scene validation. It explicitly provides no locomotion policy, mapping stack, or hardware deployment and had one star at verification time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new high-confidence lab or professor signal was selected today. DUET is a strong technical release, but its GitHub owner exposes no independently verifiable institution or lab affiliation, so it is not promoted into the source-network section yet.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-09 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role develops and deploys RL controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms, integrating formal safety mechanisms, sim-to-real pipelines, and model-based whole-body control. No newly posted, higher-confidence opportunity surpassed this verified active signal today.

</details>
