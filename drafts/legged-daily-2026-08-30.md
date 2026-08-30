**English** | [中文](../zh/drafts/legged-daily-2026-08-30.md)
# Legged Daily - 2026-08-30

## Summary
- No new paper was selected today. The run fell on Sunday, and no paper newer than the 2026-08-28 draft cleared both the recency and source-verification bar.
- `GRIT v0.0.1` is today's strongest release: an MIT-licensed Unitree G1 whole-body motion-tracking stack with a bundled ONNX policy, MuJoCo sim2sim, PICO teleoperation, and a native Unitree SDK2 bridge.
- `Sprite` opens both a 31-actuated-joint humanoid simulation description and companion FreeCAD hardware sources under explicit reciprocal licenses, but does not yet provide a complete controller or claim sim-to-real readiness.
- `go2-pace-sim2real` publishes a broad Isaac Lab workflow spanning PACE-style system identification, teacher-student locomotion training, ONNX validation, read-only shadow mode, and a Go2 control framework; the repository is new, unlicensed, and omits raw identification data and policy weights.
- BeijingDynamics is a new organization-level source worth watching for open humanoid hardware and locomotion artifacts. The previously tracked Inria Auctus / LAAS-CNRS quadruped co-design PhD remains active but closes tomorrow, 2026-08-31.

<details>
<summary><strong>New Papers</strong></summary>

No new paper met the inclusion bar today. This Sunday run did not verify a legged-robotics paper newer than the items already covered in the 2026-08-28 draft.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### mrzuang/GRIT_teleop_deploy
- Link: https://github.com/mrzuang/GRIT_teleop_deploy
- Category: control / retargeting / teleoperation / toolkit
- Robot Type: humanoid — Unitree G1
- Simulator: MuJoCo
- Deploy: both
- Summary: Releases GRIT v0.0.1 as a whole-body motion-tracking deployment stack with an ONNX policy contract, 50 Hz Python runtime, PICO/XRoboToolkit retargeting, MuJoCo sim2sim, and a native Unitree SDK2 hardware bridge.
- Notes: Created 2026-08-29 under MIT. The repository includes model/interface checks, example motions, deployment tests, explicit physical-safety warnings, and a stale-command watchdog, but excludes training and data-generation code. The bundled beta policy is described as trained on only 10+ hours of open-source data; the stated September and October releases remain a maintainer roadmap rather than verified deliverables.

### BeijingDynamics/open_sprite
- Link: https://github.com/BeijingDynamics/open_sprite
- Category: robot description / simulator asset / open hardware
- Robot Type: humanoid — Sprite0825, approximately 0.95 m with 31 actuated joints
- Simulator: MuJoCo / Isaac Lab-compatible URDF
- Deploy: simulation / hardware design data
- Summary: Publishes meshes, a sanitized training URDF, validated MuJoCo visual and floating-base external-PD models, and reproducibility metadata for the Sprite humanoid, with companion FreeCAD hardware sources in a separate official repository.
- Notes: Created 2026-08-28 under AGPL-3.0; the companion [FreeCAD source repository](https://github.com/BeijingDynamics/sprite_humanoid_freecad) uses CERN-OHL-S-2.0. The release is unusually clear that it is not a complete robot controller and lacks hardware communications, state estimation, current limits, emergency stopping, and interlocks. Research checkpoints are not included or described as sim-to-real-ready.

### godhandcrash/go2-pace-sim2real
- Link: https://github.com/godhandcrash/go2-pace-sim2real
- Category: reinforcement learning / system identification / sim-to-real / toolkit
- Robot Type: quadruped — Unitree Go2
- Simulator: Isaac Lab
- Deploy: both
- Summary: Integrates PACE-style 49-parameter system identification, curriculum and domain-randomized PPO training, symmetry augmentation, teacher-student distillation, recurrent ONNX validation, read-only hardware shadow logging, and a C++ Go2 controller framework.
- Notes: Created 2026-08-29. The README reports simulation and Go2 deployment validation, while also requiring staged checks and an independent physical emergency stop. Raw real-robot identification data, CMA-ES checkpoints, and trained policy weights are not published, and GitHub did not detect a repository-level license at verification time; results and hardware claims should therefore be treated as maintainer-reported until independently reproduced.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### BeijingDynamics
- Institution: Independent GitHub organization; institutional identity not stated publicly
- GitHub: https://github.com/BeijingDynamics
- Lab / Department: Not publicly specified
- Key Topics: humanoid / open hardware / robot description / MuJoCo / locomotion assets
- Notes: The organization appeared on 2026-08-28 with two coordinated Sprite releases: AGPL-3.0 simulation/description assets and CERN-OHL-S-2.0 FreeCAD hardware sources. No public members or external institutional homepage were visible at verification time, so the organization identity remains unverified; the artifact-level licensing and explicit validation boundaries nevertheless make it a useful source to monitor.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- Type: PhD
- Location: Talence / Bordeaux, France, with planned visits to Toulouse
- Source: [official Inria posting](https://jobs.inria.fr/public/classic/en/offres/2026-10319)
- Deadline: 2026-08-31; planned start 2026-10-01
- Topics: quadruped / mechatronic co-design / local compliance / loco-manipulation / reinforcement learning / real-to-sim calibration / prototyping
- Status: active — closes tomorrow
- Notes: Status update to the opportunity already surfaced on 2026-08-28. The official page remained reachable today and still listed the 2026-08-31 deadline and EUR 2,300 monthly gross pay. The project jointly studies architecture, actuation, compliance distribution, and control for a new quadruped, with experimental goals including outdoor high-speed galloping and flying-object catching.

</details>
