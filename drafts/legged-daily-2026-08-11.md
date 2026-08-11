**English** | [中文](../zh/drafts/legged-daily-2026-08-11.md)
# Legged Daily - 2026-08-11

## Summary
- LUCID is today's strongest paper signal: it replaces scripted humanoid skill handoffs with a learned macro-dynamics model and high-level planning through imagined skill transitions, although evaluation is simulation-only and no public code was verified.
- `madderscientist/g1_rl_mjlab` is a substantial new Unitree G1 reinforcement-learning codebase with lower-body locomotion, standing, full-body motion tracking, curriculum persistence, mirror augmentation, ONNX export, and a CPU deployment-path check; it has no explicit license or hardware result.
- `Baoshang-Zhou/Go1-MPC-WBC` offers a compact simulation-first SRB-MPC plus QP-WBC walking controller for Unitree Go1, but the repository currently contains only one Python implementation file and a short demo, with no license or hardware validation.
- No new high-confidence lab/professor source was selected today. The LUCID author network connects humanoid skill learning and long-horizon loco-manipulation, but a sufficiently complete official lab source was not verified for a new master-list entry.
- Amazon Robotics Compass's official Safe Locomotion role remains active and was rechecked today; it is a continuing pending proposal, not a newly discovered opening.

<details>
<summary><strong>New Papers</strong></summary>

### LUCID: Latent-Skill Unified Control via Imagined Dynamics for Long-Horizon Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2608.07746
- Source: arXiv
- Date: 2026-08-07
- Authors: Cheng Guo, Mingzhe Ni, Angelo Cangelosi, Arash Ajoudani
- Topics: humanoid / loco-manipulation / hierarchical reinforcement learning / world models / latent skills
- Summary: LUCID freezes a latent-conditioned whole-body skill policy, then jointly learns a high-level controller and macro-dynamics world model so long-horizon humanoid rearrangement can be optimized through imagined skill-level transitions rather than scripted handoffs.
- Notes: The paper surfaced in the 2026-08-11 arXiv robotics update. Across simulated multi-object rearrangement scenarios, it reports higher full-task success and partial-completion rates than compared baselines. Evidence is currently simulation-only, and no official public code or project repository was verified today.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### madderscientist/g1_rl_mjlab
- Link: https://github.com/madderscientist/g1_rl_mjlab
- Category: RL / control / motion tracking / deployment toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: sim / deployment-path check
- Summary: Unitree G1 plus dual Gloria-M gripper reinforcement-learning package covering lower-body velocity control, minimal standing, and 29-DoF motion tracking, with curriculum persistence, mirror augmentation, evaluation, ONNX export, and a CPU closed-loop deployment check.
- Notes: Created on 2026-08-11 and migrated to mjlab 1.5.3. The repository contains 104 tracked files and detailed task/reward implementations; motion data must be downloaded separately. It documents an ONNX deployment contract but does not provide verified physical-robot results, an explicit license, or community validation; zero stars at verification time.

### Baoshang-Zhou/Go1-MPC-WBC
- Link: https://github.com/Baoshang-Zhou/Go1-MPC-WBC
- Category: MPC / whole-body control
- Robot Type: quadruped
- Simulator: custom Python simulation / unspecified backend
- Deploy: sim
- Summary: A compact Unitree Go1 walking-controller prototype combining single-rigid-body model predictive control for contact-force planning with QP whole-body control for lower-level motion realization.
- Notes: Created on 2026-08-11. The repository currently consists of a short README and one `mpc_wbc_walk.py` implementation plus a demo video, so it is best treated as an early prototype rather than a reusable framework. No explicit license, setup documentation, benchmark, hardware deployment, or community validation was verified; zero stars at verification time.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No new high-confidence lab or professor source was selected today. LUCID provides a useful author and collaboration signal around humanoid latent-skill control, world models, and long-horizon loco-manipulation, but no sufficiently complete official lab page or new source channel was verified for master-list insertion.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- Type: Senior Applied Scientist
- Location: Pasadena, California, USA
- Source: official careers page — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- Deadline: rolling / unknown
- Topics: safe legged locomotion / reinforcement learning / control barrier functions / whole-body control / sim-to-real / quadrupeds / humanoids / physical deployment
- Status: active at 2026-08-11 verification; previously proposed on 2026-07-27 and still pending confirmation for master-list addition
- Notes: The role owns RL locomotion controllers for walking, running, stair climbing, and fall recovery on physical quadruped and humanoid platforms, integrating formal safety mechanisms, sim-to-real pipelines, and model-based whole-body control. The official page remains accessible and lists a Pasadena base salary range of USD 167,100-226,100.

</details>
