**English** | [中文](../zh/drafts/legged-daily-2026-10-29.md)
# Legged Daily - 2026-10-29

## Summary
- HumanoidNDM (CoRL 2026) uses real-robot proprioceptive data, a history-conditioned neural dynamics model, and differentiable forward kinematics to fine-tune G1 motion tracking policies without external motion capture.
- Whole-Body Humanoid Control via Stochastic Motion Tokenization (Humanoids 2026) introduces a compact motion-token interface and reports 16.8-second motion sequences and a 35-second skill transition on a real Unitree G1.
- Local Spatial Matrix Memory (LSMM) learns spatially indexed memory for legged exploration; the authors report a threefold reduction in maze-layout reconstruction error relative to baseline memory architectures, but no physical-robot evaluation is established.
- Newly inspected code includes Menlo's official Asimov-1 AMP extension, a muscle-driven SuperMimic reproduction, and a Go2 push-recovery benchmark emphasizing multi-seed evaluation and explicit negative ablation results.
- EPFL's MuscleMimic retargeted locomotion data are available through a gated Hugging Face release with explicit AMASS-derived noncommercial conditions; ETH Soft Robotics Lab lists doctoral and postdoctoral recruitment through November 30.

<details>
<summary><strong>New Papers</strong></summary>

### HumanoidNDM: Closing the Training-Deployment Gap of Motion Tracking via Humanoid Neural Dynamics Model
- Link: https://arxiv.org/abs/2610.34126
- Source: CoRL 2026 (accepted; also available as arXiv preprint)
- Date: 2026-10-25
- Authors: Chao Chen, Zhenrong Wang, Jilong Wang, Yusen Feng, Jiangran Lyu, Li Yi, He Wang
- Topics: humanoid / motion tracking / neural dynamics / model-based policy fine-tuning / sim-to-real / Unitree G1
- Summary: FENCE perturbs reference motions at low frequencies to gather safe hardware data, while a history-based, proprioception-only dynamics model uses differentiable forward kinematics for link-space supervision and backpropagates gradients to refine a motion-tracking policy.
- Notes: Authors demonstrate online, motion-capture-free policy adaptation to external loads and other disturbances on a physical G1. CoRL 2026 acceptance is stated by the authors' publication pages. https://shenbiachao.github.io/publications/ ; no verified open training-code release.

### Whole-Body Humanoid Control via Stochastic Motion Tokenization
- Link: https://arxiv.org/abs/2610.36452
- Source: Humanoids 2026 (accepted; arXiv preprint available)
- Date: 2026-10-27
- Authors: Michael Drolet, Oleg Arenz, Jan Peters
- Topics: humanoid / whole-body motion / stochastic motion tokens / skill transitions / motion tracking / Unitree G1
- Summary: A stochastic motion tokenizer provides a compact discrete interface for higher-level behavior or text-conditioned generation, supplying structured future motion references to a low-level tracking controller instead of velocity-only commands.
- Notes: Authors report 16.8-second dance, fight and walk sequences and a 35-second fight-to-dance transition on a physical G1; comparison to FSQ and VQ-VAE is at matched tokenizer capacity. Acceptance at IEEE-RAS Humanoids 2026 is stated in the arXiv comments.

### Remember Where You Walk: Learning Spatial Memory for End-to-End Legged Robot Exploration
- Link: https://arxiv.org/abs/2610.37203
- Source: arXiv preprint (no confirmed peer-reviewed venue)
- Date: 2026-10-27
- Authors: Leon Magnus, Nico Bohlinger, Jan Peters, Oleg Arenz
- Topics: legged robots / autonomous exploration / long-horizon memory / RL / spatial representation
- Summary: Local Spatial Matrix Memory (LSMM) uses Hadamard-memory-based, position-indexed cells to retain spatial information beyond the receptive field of standard recurrent locomotion/navigation policies.
- Notes: In maze exploration, authors report comparable coverage to recurrent and finite-history baselines while reducing maze-layout reconstruction error about threefold; the demonstrated benchmark is navigation simulation rather than verified real-robot locomotion.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### menloresearch/asimov-1-amp
- Link: https://github.com/menloresearch/asimov-1-amp
- Category: RL / AMP / locomotion / training toolkit
- Robot Type: humanoid (Menlo Asimov-1)
- Simulator: Isaac Lab 3.0 / Isaac Sim PhysX
- Deploy: sim
- Summary: Official Menlo Research extension that adds an adversarial-motion-prior discriminator and PPO training loop to an Asimov-1 velocity-tracking task, with a 49-second 50-Hz expert walking clip and reproducible training commands.
- Notes: BSD-3-Clause; Isaac Lab's upstream base task is still pending integration (PR #7071). Newton and OvPhysX are not supported; real-hardware validation is not asserted by this repository.

### kaibohex/muscle-supermimic
- Link: https://github.com/kaibohex/muscle-supermimic
- Category: motion tracking / differentiable world model / RL / toolkit
- Robot Type: musculoskeletal humanoid (MS-Human-700 / MyoFullBody)
- Simulator: mjlab / MuJoCo-Warp
- Deploy: sim
- Summary: Independent SuperMimic adaptation for muscle-actuated humanoids, combining a differentiable muscle/tendon model with a world-model-driven tracker that outputs muscle excitation at 100 Hz.
- Notes: Author documents 700-muscle and 354-muscle models, checkpoints and held-out clip evaluations; results are evolving and remain simulation-only. Apache-2.0 code; source motions are gated AMASS-derived data with noncommercial and nonredistribution restrictions. Not an official SuperMimic reproduction.

### lbm23/go2-rl-isaacsim
- Link: https://github.com/lbm23/go2-rl-isaacsim
- Category: RL / robustness evaluation / sim-to-sim / toolkit
- Robot Type: quadruped (Unitree Go2)
- Simulator: Isaac Lab (Newton/MJWarp) / Isaac Sim PhysX
- Deploy: sim
- Summary: Engineering reproduction for Go2 velocity tracking and directional push recovery, with seeded evaluations, frozen checkpoints, explicit ablation statistics and transfer of an unchanged policy between physics backends.
- Notes: Author reports a specific leftward-push checkpoint comparison with fall rate falling from 53.81% to 16.31%, but the controlled eight-seed ablation did not show a statistically significant primary contrast after multiple-testing correction. No hardware results; project-code license is pending.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### MuscleMimic GMR Retargeted Motions (full-body)
- Link: https://huggingface.co/datasets/amathislab/musclemimic-retargeted
- Category: human mocap / robot-ready motion / retargeted motion
- Subject: human / MyoFullBody musculoskeletal humanoid
- Content: 972 KIT locomotion training motions, 108 KIT locomotion testing motions and 110 AMASS transition motions; listed repository size approximately 5.64 GB.
- Format: npz (qpos, qvel, link positions/orientations, velocities, metadata)
- Access: gated (accept license conditions before download; actual file tree is listed)
- License: other — dataset requires noncommercial research use and AMASS-derived terms; no redistribution of source/derivative data without separate permissions.
- Summary: GMR-preprocessed human motion for MuscleMimic's full-body neuromuscular tracker, avoiding repeated offline retargeting and providing explicit train/test motion splits.
- Notes: This is a rediscovered existing data release, not a claim of first release today. The access restriction is material: public metadata does not imply anonymous file download. Related project: https://github.com/amathislab/musclemimic.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### He Wang / Peking University humanoid control group
- Institution: Peking University
- Homepage: https://hughw19.github.io/
- Lab / Department: humanoid robotics / computer science research network
- Key Topics: humanoid / motion tracking / real-world neural dynamics / policy fine-tuning / sim-to-real
- Notes: CoRL 2026 paper HumanoidNDM reports on-hardware, MoCap-free G1 adaptation and connects model-based real-world learning to whole-body tracking. Chao Chen's author page confirms the venue and research direction: https://shenbiachao.github.io/.

### Jan Peters / Oleg Arenz — TU Darmstadt / DFKI research network
- Institution: Technical University of Darmstadt / DFKI / Robotics Institute Germany
- Homepage: https://www.ias.informatik.tu-darmstadt.de/
- Lab / Department: Intelligent Autonomous Systems
- Key Topics: humanoid / whole-body motion / motion representation / reinforcement learning / spatial memory
- Notes: Two new arXiv works in the same author network cover stochastic whole-body motion tokenization (Humanoids 2026) and Local Spatial Matrix Memory for long-horizon legged exploration; track future code and physical navigation validation.

### Alexander Mathis / Mathis Group — EPFL (data and method update)
- Institution: EPFL
- Homepage: https://cnai.epfl.ch/mm-blog/
- GitHub: https://github.com/amathislab/musclemimic
- Lab / Department: Mathis Group
- Key Topics: musculoskeletal robotics / motion imitation / retargeting / GPU simulation
- Notes: Gated MuscleMimic GMR retargeted full-body motion files are accessible after accepting AMASS-derived restrictions; an independent muscle-supermimic project now explores world-model tracking of musculoskeletal embodiments. The latter is not an official lab release.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### ETH Zurich / Soft Robotics Lab — Doctoral Positions in Robot Learning and Soft, Musculoskeletal, and Biohybrid Robotics (proposed addition)
- Type: PhD
- Location: Zurich, Switzerland
- Source: official careers page — https://jobs.ethz.ch/job/view/JOPG_ethz_d3lDgHgDI4ewDFQ1Fb
- Deadline: 2026-11-30 (rolling review until this date)
- Topics: robot learning / musculoskeletal actuation / compliant robots / sim-to-real / embodied AI / real-robot RL
- Status: active
- Notes: Several funded 100% doctoral posts in Robert Katzschmann's lab, including people designing robots and developing real-world policies. Strong adjacency to legged actuation and learning; not a locomotion-only opening. Official posting requests one merged application PDF.

### ETH Zurich / Soft Robotics Lab — Postdoctoral Positions in Robot Learning and Soft, Musculoskeletal, and Biohybrid Robotics (proposed addition)
- Type: Postdoc
- Location: Zurich, Switzerland
- Source: official careers page — https://jobs.ethz.ch/job/view/JOPG_ethz_0Dk3rwrfGt0kHlu7Rh
- Deadline: 2026-11-30 (rolling review until this date)
- Topics: soft robotics / robot learning / physical intelligence / musculoskeletal systems / contact-rich control
- Status: active
- Notes: Multiple postdoctoral vacancies from the same lab; applications through the official ETH portal. Distinct from the doctoral vacancy, and relevant to compliant actuation and physical robot learning.

</details>
