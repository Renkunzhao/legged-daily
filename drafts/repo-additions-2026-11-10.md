**English** | [中文](../zh/drafts/repo-additions-2026-11-10.md)
# Controller, Trampoline Dynamics, and Video-to-Motion Repository Review — 2026-11-10

## Review scope and deduplication

This is the user-requested full supplementary inventory, not a scheduled daily log. The [daily preview](legged-daily-2026-11-10.md) selects three repositories; this inventory preserves the additional explicitly requested projects for review. Entries use the repository fields from the canonical template. No formal master list has been changed.

- SONIC / GR00T-WholeBodyControl, TWIST2, zita-ch/supermimic_vibed and GMR already have entries in [repos.md](../repos.md); do not add duplicates.
- HoloMotion already appears in the committed 2026-10-22 draft; MOSAIC in the 2026-10-26 draft. They still lack formal repository entries. These are consolidated proposals, not newly released projects.
- ScaleBFM already appears in [papers.md](../papers.md). CuboiLeo and Motphys SuperMimic reproductions are already linked in the supermimic_vibed entry's Notes; the proposals below promote them to independently retrievable entries.
- Jules_toile_A2022, the MuJoCo flex example and OnDynamicsForSomersaults are already referenced by [datasets.md](../datasets.md). Below, index their code separately and retain the existing dataset records.
- RWM is already referenced by papers.md and backup.md, but has no standalone repos.md entry.
- GitHub API was used first for discovery and README retrieval. Later search requests returned HTTP 403 rate-limit errors; affected follow-up searches used web search and upstream project pages/raw source. No local installation or independent benchmark was performed. Release statements below describe upstream documentation checked on this date, not a guarantee that every external download works.

## Universal humanoid controllers — proposed standalone entries

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

### zengweishuai/ScaleBFM
- Link: https://github.com/zengweishuai/ScaleBFM
- Category: foundation model / motion tracking / retargeting / deployment
- Robot Type: humanoid (Unitree G1)
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Official ScaleBFM implementation combining ScaleRetarget motion preparation, ScaleTrack pretraining and ScaleBridge sim2sim/sim2real deployment.
- Notes: README documents single-/multi-GPU training, playback and export. A ready-to-download pretrained checkpoint was not confirmed in this review. Cross-reference the existing paper entry. The original BFM project page still labels its code link “In Coming”; do not treat it as a separately released codebase: https://bfm4humanoid.github.io/.

### zixuan417/humanoid-general-motion-tracking (GMT)
- Link: https://github.com/zixuan417/humanoid-general-motion-tracking
- Category: general motion tracking / inference
- Robot Type: humanoid (Unitree G1)
- Simulator: MuJoCo
- Deploy: sim
- Summary: Lightweight official GMT release for running a pretrained general humanoid tracker on example motions in MuJoCo.
- Notes: README provides a checkpoint and sim2sim command. A complete training pipeline and hardware deployment stack were not confirmed; data processing/retargeting remains marked for later release. Useful as an inference baseline rather than an assumed full training framework.

### BAAI-Humanoid/MOSAIC
- Link: https://github.com/BAAI-Humanoid/MOSAIC
- Category: general motion tracking / teleoperation / adaptation
- Robot Type: humanoid (G1 / H1-2 / Adam)
- Simulator: Isaac Lab; sim2sim through companion RobotBridge
- Deploy: sim / hardware through companion deployment project
- Summary: Training framework for generalist humanoid motion tracking and teleoperation adaptation, with multi-motion training, distillation and residual-adaptation configurations.
- Notes: Deployment is documented in the separately linked RobotBridge project. Pretrained-weight availability was not confirmed in this review. Consolidates the committed 2026-10-26 draft rather than duplicating that discovery.

### CuboiLeo/SuperMimic-Reproduced
- Link: https://github.com/CuboiLeo/SuperMimic-Reproduced
- Category: world model / model-based RL / motion tracking
- Robot Type: humanoid (Unitree G1)
- Simulator: mjlab / MuJoCo Warp
- Deploy: sim
- Summary: Independent SuperMimic reproduction with a learned differentiable dynamics model, BPTT actor updates, multi-GPU training and full-library motion evaluation.
- Notes: README links a BONES-SEED checkpoint release and explicitly lists ONNX export and real-robot deployment as not completed. MIT. Promote the existing Notes-only link to a standalone entry; current README distinguishes paper-observation experiments from earlier extra-observation runs, so avoid carrying over the old blanket description of its best results.

### Motphys/Uni-SuperMimic
- Link: https://github.com/Motphys/Uni-SuperMimic
- Category: world model / model-based RL / motion tracking
- Robot Type: humanoid (Unitree G1)
- Simulator: UniLab with mjwarp / MuJoCo / Motrix
- Deploy: sim
- Summary: Independent SuperMimic reproduction with interchangeable simulation backends, LAFAN1/BONES-SEED preparation, training and deterministic full-library evaluation.
- Notes: README links released LAFAN1 and BONES-SEED checkpoints, including an EMA/no-sync variant. Apache-2.0. Promote the existing Notes-only link; reported speed and tracking results are not independently reproduced here. Public code does not establish G1 trampoline deployment readiness.

## Trampoline mechanics and acrobatic dynamics — code cross-references

### EveCharbie/Jules_toile_A2022
- Link: https://github.com/EveCharbie/Jules_toile_A2022
- Category: physical modeling / system identification / optimization
- Robot Type: general (trampoline environment for legged systems)
- Simulator: custom spring-network model / CasADi
- Deploy: sim
- Summary: Experimental trampoline-model fitting using motion-capture and force-plate trials, with static spring-coefficient optimization and a proposed dynamic damping-identification workflow.
- Notes: Fork of Julo0/Jules_toile_A2022. README describes pygmo/gaco global search and CasADi/IPOPT refinement, but several dynamic/local-refinement and validation links are placeholders. Treat this as research code, not a completed calibrated robot simulator. No license was stated on the reviewed landing page. Related fitted-data entry already exists in datasets.md.

### MuJoCo flex trampoline example
- Link: https://github.com/google-deepmind/mujoco/blob/main/model/flex/trampoline.xml
- Category: simulator / elastic surface modeling
- Robot Type: general (compliant environment)
- Simulator: MuJoCo
- Deploy: sim
- Summary: Official MJCF example of a two-dimensional elastic flexcomp trampoline with a falling sphere, useful as an inspectable starting point for compliant-contact scenes.
- Notes: Checked XML specifies a 16×16 grid, 0.1 m spacing, four pinned corners, mass 10, Young's modulus 75000, thickness 0.01 and edge damping 10; timestep 0.001 s. Apache-2.0. These are demonstration parameters, not experimentally identified competition-bed parameters. Cross-link the existing datasets.md entry; this is not the same model as a centre-node-only trampoline.

### Ipuch/OnDynamicsForSomersaults
- Link: https://github.com/Ipuch/OnDynamicsForSomersaults
- Category: biomechanics / dynamics / trajectory optimization
- Robot Type: general (human acrobatics as a reference for humanoids)
- Simulator: biorbd / bioptim
- Deploy: sim
- Summary: Reproducible optimal-control study of a trampoline Miller somersault comparing free-floating/full-body dynamics and explicit/implicit formulations.
- Notes: MIT. The modeled acrobatics concern the airborne phase, not a trampoline-bed contact model. Useful for angular-momentum and trajectory-reference reasoning; code expects biorbd 1.8.4 and bioptim 2.2.1. Simulation data are already tracked as Miller Somersault Optimal Control Solutions in datasets.md.

## Learned dynamics / world models

### leggedrobotics/robotic_world_model
- Link: https://github.com/leggedrobotics/robotic_world_model
- Category: learned dynamics / world model / model-based RL
- Robot Type: quadruped (ANYmal D reference pipeline)
- Simulator: Isaac Lab; offline imagination training can omit the simulator
- Deploy: sim
- Summary: Official RWM/RWM-U implementation for concurrent dynamics/policy learning, autoregressive prediction visualization and online/offline model-based policy optimization.
- Notes: The reference implementation provides configurable state, action, contact and termination heads and ensemble uncertainty settings. README links pretrained dynamics and initial-state data. Relevant to learning robot–bed dynamics, but it does not supply a trampoline-specific model. The GitHub license panel and README license badge disagree; inspect LICENCE before reuse rather than inferring a license from the badge.

### leggedrobotics/robotic_world_model_lite
- Link: https://github.com/leggedrobotics/robotic_world_model_lite
- Category: learned dynamics / offline model-based RL / toolkit
- Robot Type: quadruped (ANYmal D example)
- Simulator: none for offline model/policy training
- Deploy: offline training / external simulator evaluation
- Summary: Lightweight RWM/RWM-U pipeline for recurrent-ensemble dynamics learning from offline data and policy training in learned dynamics without installing a full robotics simulator.
- Notes: README links a pretrained RWM-U model, initial-state data and a Colab notebook; evaluation uses the full Isaac Lab extension or another compatible environment. It is a methodology baseline, not a released trampoline world model. License panel/badge inconsistency also exists here; check LICENCE directly.

## Video → human motion → robot reference

### zju3dv/GVHMR
- Link: https://github.com/zju3dv/GVHMR
- Category: monocular motion recovery / video-to-motion
- Robot Type: general (human motion upstream of humanoid retargeting)
- Simulator: none
- Deploy: offline inference / data
- Summary: Official gravity-view-coordinate method for recovering world-grounded human motion from monocular video, with video demos, pretrained-checkpoint references, evaluation and training commands.
- Notes: Static-camera mode skips visual odometry; README notes the newer default SimpleVO path. Pair recovered human motion with the existing GMR entry and then a robot tracker. No reviewed source establishes reliable trampoline-flip reconstruction under inversion, occlusion or moving-bed contact.

### yufu-wang/PromptHMR
- Link: https://github.com/yufu-wang/PromptHMR
- Category: human mesh recovery / video-to-motion
- Robot Type: general (human-to-humanoid motion pipeline)
- Simulator: none
- Deploy: offline inference / data
- Summary: Promptable human-mesh recovery with world-coordinate video reconstruction, static/moving-camera modes and released model-download scripts, suitable as the human-motion front end of a retargeting pipeline.
- Notes: README explicitly says training code is not planned for release due to licensing agreements. SMPL-family assets require registration. Non-commercial scientific-research restrictions apply in the linked video2robot pipeline; keep this distinct from a fully permissive end-to-end toolkit.

### AIM-Intelligence/video2robot
- Link: https://github.com/AIM-Intelligence/video2robot
- Category: video-to-motion / retargeting / pipeline
- Robot Type: humanoid (G1 / H1 / Booster T1)
- Simulator: no closed-loop controller; motion visualization provided
- Deploy: data / browser visualization
- Summary: Integrated existing-video or generated-video pipeline: PromptHMR human recovery → SMPL-X → GMR → robot reference motion, with CLI and browser visualization.
- Notes: Outputs robot_motion.pkl with root pose and joint positions; this is kinematic motion generation, not proof of dynamically feasible execution or a trained control policy. Existing videos do not require the optional video-generation step. Core code is MIT; the end-to-end path inherits PromptHMR's non-commercial scientific-research restriction.

### yohanshin/WHAM
- Link: https://github.com/yohanshin/WHAM
- Category: monocular motion recovery / video-to-motion
- Robot Type: general (human motion upstream of humanoid retargeting)
- Simulator: none
- Deploy: offline inference / data
- Summary: Official world-grounded human-motion reconstruction implementation with custom-video inference, camera-motion estimation, optional Temporal SMPLify refinement and two-stage training commands.
- Notes: Pretrained-model download scripts are provided; SMPL assets require registration. Use as an alternative human-motion estimator, then retarget to a robot separately. README still lists data preprocessing as incomplete; the camera-coordinate-only option is not equivalent to world-coordinate reconstruction.

## Research interpretation

- Suggested physical-model path: use experimental spring-network identification to calibrate bed response, then validate the chosen MuJoCo model against measured deflection and rebound. The existing FIG/Qian parameter entries in datasets.md are calibration references, not interchangeable material constants.
- Suggested learned-model path: use SuperMimic for policy learning and RWM/RWM-U as an offline dynamics/uncertainty baseline. This search did not verify a public, ready-to-use trampoline-specific world model; that is a search outcome, not a claim of nonexistence.
- Suggested video path: video → GVHMR or PromptHMR → GMR → reference/contact/phase checks → a motion tracker. video2robot packages one of these paths. Human reconstruction, robot retargeting and closed-loop execution are three separate capabilities.
- A world-grounded motion estimator is not a dynamics world model. Trampoline motion needs separate checking of camera scale, flight height, inverted poses, contact timing and bed-relative height; none of these repositories alone establishes end-to-end success on a compliant bed.
