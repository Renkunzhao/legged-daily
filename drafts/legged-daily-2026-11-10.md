**English** | [中文](../zh/drafts/legged-daily-2026-11-10.md)
# Legged Daily - 2026-11-10

## Summary
- User-requested retrospective curation, not a claim that these projects were released today: prioritize OpenTrack, HoloMotion and BFM-Zero as missing formal repository entries.
- OpenTrack provides an especially relevant reference-entry implementation: QP/IK stepping transitions from the default pose, with foot and CoM constraints.
- Trampoline-model calibration, learned dynamics and video-derived motion are covered in the [full supplementary review](repo-additions-2026-11-10.md), including 17 standalone repository-entry proposals and explicit cross-references to existing papers/datasets.
- No public ready-to-use trampoline-specific world model was verified in this search. RWM/RWM-U are general legged-dynamics baselines; GVHMR/PromptHMR/WHAM are human-motion estimators, not dynamics world models.
- GitHub API discovery was followed by web/project-page fallback after actual HTTP 403 search-rate-limit errors. Availability claims are source-reviewed, not local execution results.

<details>
<summary><strong>New Papers</strong></summary>

No new paper entries proposed in this repository-focused review.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### GalaxyGeneralRobotics/OpenTrack (Any2Track)
- Link: https://github.com/GalaxyGeneralRobotics/OpenTrack
- Category: motion tracking / RL / distillation / dynamics adaptation
- Robot Type: humanoid (Unitree G1)
- Simulator: MuJoCo / JAX
- Deploy: both
- Summary: Official Any2Track codebase with specialist PPO teachers, DAgger generalist students, AnyAdapter dynamics adaptation and a real-robot deployment path.
- Notes: README provides LAFAN1 generalist v2 checkpoint links and training/export commands; its 40/40 tracking result is author-reported. Motion preprocessing includes QP/IK stepping transitions from the default pose to a clip's first frame with foot and CoM constraints. Particularly useful for reference-entry design; not evidence of trampoline transfer.

### HorizonRobotics/HoloMotion
- Link: https://github.com/HorizonRobotics/HoloMotion
- Category: motion tracking / foundation model / teleoperation
- Robot Type: humanoid (Unitree G1)
- Simulator: Isaac / MuJoCo; SuperMimic path also supports MuJoCo Warp
- Deploy: both
- Summary: Whole-body humanoid motion-tracking framework with pretrained models, training, MuJoCo evaluation and G1 teleoperation/deployment documentation.
- Notes: README links the v2.0.0 checkpoint bundle and a separate SuperMimic training route added on 2026-10-24. Availability and validation vary by mode; do not assume the SuperMimic actor shares the main HoloMotion deployment interface. Consolidates the 2026-10-22 draft entry.

### LeCAR-Lab/BFM-Zero
- Link: https://github.com/LeCAR-Lab/BFM-Zero
- Category: unsupervised RL / behavioral foundation model / motion tracking
- Robot Type: humanoid
- Simulator: Isaac Sim / MuJoCo; distributed MJLab training is also linked
- Deploy: both
- Summary: Promptable behavioral foundation model supporting motion tracking, goal-reaching and reward-conditioned behavior through inferred latent representations.
- Notes: Main README marks full training/evaluation, pretrained models and deployment as released; see the deploy and minimal_inference branches for their respective interfaces. A smaller RTX 4090 training implementation remains unchecked on its roadmap. CC BY-NC 4.0. Distinct from the original BFM and ScaleBFM research line.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

No new data release proposed. Existing trampoline calibration and somersault data in datasets.md are cross-referenced in the supplementary review; this run did not re-download or revalidate their data files.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

Not reviewed in this targeted repository search.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

Not reviewed in this targeted repository search; no job additions or removals proposed.

</details>
