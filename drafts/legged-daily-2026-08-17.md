**English** | [中文](../zh/drafts/legged-daily-2026-08-17.md)
# Legged Daily - 2026-08-17

## Summary
- `HiPHI` is today's strongest signal: an official 617.5-hour, 200.1-million-frame optical motion-capture release for humanoid learning, with 245.7 hours of synchronized human-object interaction data and reported real-world Unitree G1 validation.
- `G1-MOTION` packages a full video-to-hardware Unitree G1 motion-imitation workflow spanning pose extraction, retargeting, data conversion, Isaac Lab training, MuJoCo validation, model export, and deployment.
- No new paper was selected. The relevant loco-manipulation paper found in the current arXiv batch had already been captured in the August 13 draft; the remaining newly listed records did not clear the direct legged-robotics relevance bar.
- No sufficiently new, independently verified lab/professor or hiring signal was added today; previously tracked active opportunities remain more actionable than the noisy search results surfaced in this run.

<details>
<summary><strong>New Papers</strong></summary>

No new paper was selected today. The strongest relevant item surfaced during screening, “Learning Loco-Manipulation From SMPC Demonstrations With Sparse Offline-to-Online RL” (arXiv:2608.12063), was already included in the 2026-08-13 draft. Other records in the new robotics listing were either outside the legged-robotics scope or lacked enough direct relevance to justify inclusion.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### HiPHI
- Link: [GitHub](https://github.com/noitom-robotics/hiphi) · [Project page](https://noitom-robotics.github.io/hiphi/) · [Dataset](https://huggingface.co/datasets/noitomrobotics/HiPHI)
- Category: dataset / benchmark / viewer
- Robot Type: humanoid / general
- Simulator: none
- Deploy: data / browser / hardware validation
- Summary: A large-scale optical motion-capture benchmark releasing 617.5 hours and 200.1 million frames of standardized 55-joint BVH motion, including 245.7 hours of synchronized human-object interaction with object trajectories and high-resolution meshes for humanoid imitation, retargeting, generation, and whole-body control.
- Notes: The official Noitom Robotics repository and project page launched on 2026-08-17. The release covers 132 performers at 90 Hz, 22 FrameNet frames, 214 Frame-LU labels, and 40 canonical object meshes; the project reports motion-tracking scaling experiments and real-world Unitree G1 deployment. Data uses the ModalityNet Open Research License v1.0 for non-commercial research, education, and evaluation, and BVH motion still requires embodiment-specific retargeting and validation.

### G1-MOTION
- Link: https://github.com/tangweixing/G1-MOTION
- Category: retargeting / RL / control / toolkit
- Robot Type: humanoid — Unitree G1
- Simulator: Isaac Lab / Isaac Sim / MuJoCo
- Deploy: both
- Summary: An integrated workflow that takes a human-motion video through GVHMR pose recovery, GMR retargeting, motion-data conversion, Isaac Lab whole-body tracking training, ONNX/MNN export, simulation validation, and Unitree G1 hardware deployment.
- Notes: Created 2026-08-17 and MIT licensed at the repository root. It bundles seven upstream projects plus training and inference artifacts, CSV/NPZ conversion utilities, deployment templates, and step-by-step Chinese and English documentation. The repository is unusually large and aggregates third-party components, so users should review each bundled project's original documentation, licenses, model-weight terms, and machine-specific path assumptions before reuse.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No sufficiently new lab or professor signal was selected today. HiPHI provides a useful new industry research source around Noitom Robotics and its academic collaborators, but the available launch materials did not establish a distinct lab/professor update that should be added separately from the dataset entry.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence hiring signal was selected today. Official and targeted searches did not surface a newly posted, directly legged-robotics role with enough specific and verifiable details to improve on the active opportunities already tracked in `jobs.md`.

No stale-item removal was identified today.

</details>
