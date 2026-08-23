**English** | [中文](../zh/drafts/legged-daily-2026-08-23.md)
# Legged Daily - 2026-08-23

## Summary
- `GigaBrain-WBC-0.5` reframes humanoid whole-body tracking as a behavior world model that predicts action, next state, and feasible next behavior, reporting strong terrain interaction, implausible-command robustness, and fall recovery.
- `MILD` introduces a physics-grounded discrete-element terrain model and terrain-aware RL controller for bipedal locomotion on yielding surfaces, with hardware demonstrations of online stiffness identification and adaptation.
- `AdaPT` learns professional tennis styles from broadcast video, explicitly adapts planning to execution-speed errors, and demonstrates rallying and serving on Unitree G1 and full-size Dobot Atom humanoids.
- The official Apache-2.0 `noitom-robotics/AdaPT` repository is today's only new repository that cleared the quality bar; the current release covers first-stage adaptive serve tracking in MJLab/MuJoCo and includes a pretrained checkpoint.
- No distinct new lab/professor entry or actionable hiring opening was selected; the EPFL BioRob humanoid-neuromechanics PhD/postdoc posting is explicitly closed.

<details>
<summary><strong>New Papers</strong></summary>

### GigaBrain-WBC-0.5: A Behavior World Model for Robust Whole-Body Control with Environment Interaction
- Link: [arXiv](https://arxiv.org/abs/2608.18234) · [Project page](https://shepherd1226.github.io/gigabrain-wbc-0.5/)
- Source: arXiv / official project page
- Date: 2026-08-18
- Authors: Ziyang Cheng, Tianshu Tang, Jinxin Lan, Xinze Chen, Yuhan Gong, et al.
- Topics: humanoid / whole-body control / behavior world model / terrain and object interaction / fall recovery
- Summary: Trains a causal Transformer to jointly predict the next action, proprioceptive state, and latent behavior-command distribution, then uses the learned distribution to project physically implausible commands toward feasible best-effort behaviors online.
- Notes: The project reports 81.3% terrain-interaction success, 83.1% survival under implausible commands, and 99.3% fall recovery against three large-scale tracking baselines. Hardware trials use Unitree G1, and the paper reports transfer to Maker L01 with simple fine-tuning. No official code or checkpoint release was verified today.

### MILD: Tractable Terrain Modeling for Learning Improved Bipedal Locomotion on Deformable Surfaces
- Link: https://arxiv.org/abs/2608.19955
- Source: arXiv; journal reference IEEE Robotics and Automation Letters (2025)
- Date: 2026-08-20
- Authors: Jiahui Zhang, Zhe Xu, Wanyue Li, Xinqi Li, Xuechao Chen, Zhangguo Yu, Annan Tang, Peng Lu
- Topics: bipedal locomotion / deformable terrain / contact modeling / reinforcement learning / sim-to-real
- Summary: Combines a physics-grounded discrete-element contact solver for spatially varying yielding terrain with a latent-modulated, proprioceptive terrain-aware locomotion controller trained by deep RL.
- Notes: The authors report more diverse and realistic training contacts than comparison methods plus real-hardware online identification and adaptation across surfaces with varied stiffness. The work comes from HKU ArcLab with collaborators at Beijing Institute of Technology and the University of Tokyo; Peng Lu / ArcLab is already tracked, so it is not duplicated as a new lab entry.

### Towards Professional Tennis Styles for Humanoid Robots with Adaptive Motion Planning and Tracking
- Link: [arXiv](https://arxiv.org/abs/2608.20087) · [Project page](https://humanoidtennis.github.io/AdaPT/) · [Code](https://github.com/noitom-robotics/AdaPT)
- Source: arXiv / official project page
- Date: 2026-08-20
- Authors: Tao Huang, Ruofei Liu, Xuchen Tang, Xinyin Zhang, Junli Ren, et al.
- Topics: humanoid / athletic skills / motion planning and tracking / imitation from video / sim-to-real
- Summary: AdaPT separates stylistic motion planning from low-level tracking, randomizes execution speed during tracker training, and conditions the planner on a learned motion-speed adapter to reduce long-horizon sim-to-real error accumulation.
- Notes: Official materials demonstrate professional-style rallying and serving learned from broadcast video and motion capture on Unitree G1 and full-size Dobot Atom robots, including in-the-wild serving without motion capture. The project reports a 21.5-hour dataset spanning six athlete styles and seven stroke/serve types.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### noitom-robotics/AdaPT
- Link: https://github.com/noitom-robotics/AdaPT
- Category: humanoid motion learning / reinforcement learning / toolkit
- Robot Type: humanoid — Unitree G1 in the released training configuration; the paper also evaluates Dobot Atom
- Simulator: MJLab / MuJoCo
- Deploy: sim training and playback; real-robot results are documented by the paper/project page, but hardware deployment code is not documented in the current README
- Summary: Official Apache-2.0 PyTorch implementation of AdaPT, currently releasing the first-stage adaptive tennis-serve tracking environment, training/playback commands, motion examples, and a pretrained Unitree G1 checkpoint.
- Notes: Created 2026-08-20; 55 stars at verification time. The release trains 4,096 environments and is built on `mjlab` and AdaMimic. It does not yet expose the complete rally/planning stack described in the paper, so the repository should be treated as a partial but substantive first release.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

No sufficiently distinct new lab or professor entry was selected today. MILD reinforces the already tracked Peng Lu / HKU Adaptive Robotic Controls Lab signal, while AdaPT is a new Noitom Robotics–Shanghai AI Laboratory–Dobot Robotics–Shanghai Jiao Tong University collaboration but does not by itself establish a separate lab/professor update beyond the selected paper and repository.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new high-confidence, actionable legged-robotics hiring opportunity was selected today.

The official [EPFL BioRob openings page](https://www.epfl.ch/labs/biorob/openings/) lists a Fall 2026 PhD and postdoc project on human-locomotion neuromechanics, bio-inspired control, reinforcement learning, and humanoid robots, but the page explicitly marks both positions as **CLOSED**. It is therefore recorded as a closed source check, not an active opportunity.

No stale-item removal was identified in the tracked jobs lists today.

</details>
