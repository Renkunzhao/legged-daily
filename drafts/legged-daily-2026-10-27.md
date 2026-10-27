**English** | [中文](../zh/drafts/legged-daily-2026-10-27.md)
# Legged Daily - 2026-10-27

## Summary
- A sim-to-sim study (arXiv, 2026-10-23) finds that learned humanoid motion trackers tolerate only 20-30 ms of command delay; randomizing delay over 0-50 ms during training raises survival at 40 ms from 15% to 95% on average.
- IIT's Dynamic Legged Systems Lab reports a practical recipe for fine-tuning a VLA on a Unitree Go2 + AgileX Piper legged manipulator, separating data coverage from model capacity, with closed-loop real-robot pick-and-place.
- HoloBoxing (arXiv, 2026-10-23) learns humanoid boxing in about 7 minutes of single-GPU task training by putting a compact body-target planner on top of a frozen, pretrained whole-body controller (simulation only).
- Menlo Research's open-source Cyclotron framework now publishes Asimov-1 locomotion training (Isaac Lab, PPO + AMP) with sim-to-real deployment, plus a public 65-scenario MuJoCo locomotion robustness benchmark on Hugging Face.
- Berkeley Humanoids published Lite Motion Retargeting and a Lite-Kimodo dataset (~29k text-generated G1 motions retargeted to Lite Pro, Apache-2.0); a SuperMimic port to the 31-DoF LimX Oli humanoid also appeared.
- Follow-up: the ViT-H official repository (github.com/mileret/ViT-H-release, MIT) is now public, but it holds only a README; the authors plan to release offline code by 2026-11-01 and teleoperation code by 2026-12-01. No new verified job signals today.

<details>
<summary><strong>New Papers</strong></summary>

### Delay Randomization Widens the Delay Margin of Learned Humanoid Motion Trackers
- Link: https://arxiv.org/abs/2610.32277
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-23
- Authors: Shaoqin Li, Yi Sun
- Topics: humanoid / motion tracking / sim-to-sim / actuation delay / domain randomization / robustness evaluation
- Summary: Trains 24-joint humanoid motion-tracking policies on five video-derived motions and measures them in an independent, verified CPU MuJoCo harness. Unrandomized policies have only a 20-30 ms delay margin (15% average survival at 40 ms). Randomizing delay over 0-50 ms in training raises 40 ms survival to 95% on average and moves the margin to 50-70 ms, at the cost of slightly looser tracking.
- Notes: A control arm with equal extra training iterations does not improve, which isolates the randomization effect. The authors argue that the delay range should come from the robot's measured latency and that delay margin should be reported alongside other sim-to-sim metrics. They also trace their first apparent sim-to-sim gap to harness bugs (missing floor, wrong timestep). 8 pages; simulation only.

### From Tabletop to Walking Bot: Deploying a VLA Model on a Legged Manipulator Robot
- Link: https://arxiv.org/abs/2610.32271
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-23
- Authors: Giovanni Minelli, Antonio Langella, Giovanni B. Dessy, Lorenzo Amatucci, Giulio Turrisi, Victor Barasuol, Claudio Semini
- Topics: quadruped / legged manipulation / loco-manipulation / vision-language-action / fine-tuning / real robot
- Summary: Studies what it takes to adapt a pretrained VLA from a fixed-base arm to a Unitree Go2 carrying an AgileX Piper arm, covering data collection, model variant, action horizon and demonstration conventions, and reports closed-loop real-world pick-and-place.
- Notes: Wider demonstration coverage cuts held-out end-effector error by 30%, and adding secondary skills (for example, pushing) adds behaviour modes without degrading the base task. Author list matches the IIT Dynamic Legged Systems Lab (Claudio Semini); code release not stated.

### HoloBoxing: A Simple Recipe for Humanoid Boxing with 7 Minutes of Single-GPU Training
- Link: https://arxiv.org/abs/2610.32909
- Source: arXiv preprint; venue acceptance not stated
- Date: 2026-10-23
- Authors: Xihan Ma, Bo Zhang, Boxiong Li, Yuhan Bao, Ziyue Liu, Yucheng Wang
- Topics: humanoid / hierarchical control / pretrained whole-body controller / imitation initialization / RL / interaction skills
- Summary: Separates reusable motor skills from task decisions. A compact planner outputs 32-dimensional actions that a learned decoder maps to future body-point target windows, a frozen pretrained whole-body controller executes them, and imitation on measured states initializes the planner before RL.
- Notes: The 7-minute figure covers only additional representation fitting and the single-GPU task run. It excludes controller pretraining, data preparation, evaluation and search. Experiments are in simulation only. No code or project link is given on arXiv.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### menloresearch/cyclotron
- Link: https://github.com/menloresearch/cyclotron
- Category: RL / training framework / benchmark tooling
- Robot Type: humanoid (Menlo Asimov 1)
- Simulator: Isaac Lab (training); MuJoCo (benchmark harness)
- Deploy: both
- Summary: Official training and evaluation framework for Asimov-1 locomotion policies, packaged as a standalone Isaac Lab extension with PPO plus adversarial motion priors. It covers train, export, viewing and benchmarking, and the README shows a sim-to-real walking comparison.
- Notes: BSD-3-Clause; created 2026-09-11, last pushed 2026-10-23, ~130 stars. Pairs with the Asimov Locomotion Benchmark dataset below. It resolves the earlier labs.md note that Asimov's locomotion policy was still marked forthcoming.

### Berkeley-Humanoids/Lite-Motion-Retargeting
- Link: https://github.com/Berkeley-Humanoids/Lite-Motion-Retargeting
- Category: retargeting / dataset tooling / viewer
- Robot Type: humanoid (Berkeley Lite Pro; source data from human mocap and Unitree G1)
- Simulator: none for IK retargeting; optional physics-based retargeting via ReActor
- Deploy: data
- Summary: Retargets LAFAN1, AMASS, BONES-SEED, MotionDecode and Kimodo G1 sources to the Lite Pro humanoid with per-frame IK, compares IK, UMR and ReActor on the same frames, and publishes layered Rerun motion files with a browser Space.
- Notes: The repository has no license file detected by GitHub (license not stated). The README warns that most source datasets do not permit redistribution. Last pushed 2026-10-25.

### liuskywalkerjskd/supermimic_oli
- Link: https://github.com/liuskywalkerjskd/supermimic_oli
- Category: control / world model / motion tracking / retargeting
- Robot Type: humanoid (LimX Oli HU_D04_01, 31 DoF; Unitree G1 retained)
- Simulator: Isaac Lab 3 (kit-less, MuJoCo-Warp)
- Deploy: sim
- Summary: Unofficial port of a SuperMimic reproduction (zita-ch/supermimic_vibed) to the LimX Oli humanoid, adding Oli motion preparation, IK retargeting configs and full rollout exports.
- Notes: The author reports one Oli policy tracking 40 LAFAN1 clips with normalized return 0.6783, 36/40 clips completed without termination, and about 2.2 h on one RTX 4090. MIT; created 2026-10-23. It adds to the SuperMimic reproductions already tracked in repos.md and the 2026-10-26 draft.

</details>

<details>
<summary><strong>New Datasets</strong></summary>

### Lite Kimodo Dataset
- Link: https://huggingface.co/datasets/Berkeley-Humanoids/Lite-Kimodo-Dataset
- Category: optimization-generated / robot motion
- Subject: Berkeley Lite Pro humanoid (retargeted from simulated Unitree G1 clips)
- Content: Per the dataset card, 9,490 single-action clips (~10 h), 9,947 long-horizon clips (~54 h) and 9,941 long-horizon clips (~118 h), all at 50 Hz, each stored next to its source G1 clip.
- Format: Rerun `.rrd` (layered: source G1 joints and body poses, retargeted Lite Pro joints and body goals), plus web packs for the browser Space
- Access: open
- License: Apache-2.0 (dataset card; stated as inherited from the cagataydev Kimodo G1 sets)
- Summary: Large text-generated humanoid motion set retargeted to an open-source small humanoid, with goals in the robot's link frames for direct tracking rewards.
- Notes: This is not motion capture. The clips were generated by NVIDIA's Kimodo model and played on a simulated G1 by a tracking policy before retargeting. Check the upstream Kimodo model terms before redistributing. Created 2026-10-12; newly curated today. A companion Lite-LAFAN1 set is private.

### Asimov Locomotion Benchmark
- Link: https://huggingface.co/datasets/yipjiaqi/asimov-locomotion-bench
- Category: benchmark
- Subject: Menlo Asimov 1 humanoid (velocity-command locomotion policies)
- Content: 65 seeded MuJoCo scenarios: 13 locomotion, 20 standing-push, 16 walking-push, 4 sustained-push, 4 low-friction, 1 100 m lap and 7 terrain tests (stairs, ramps, scattered boxes, rough tiles) with end-zone success criteria.
- Format: JSONL test definitions plus YAML benchmark and eval configs
- Access: open
- License: BSD-3-Clause (dataset card metadata)
- Summary: Reproducible robustness benchmark for humanoid velocity-tracking policies, run through Cyclotron, with optional submission of results to a policy's Hub repository.
- Notes: Created 2026-10-23 under a personal Hugging Face account and references Menlo's official Cyclotron and asimov-1 repositories. Official Menlo endorsement is not verified. It contains scenario specifications, not recorded trajectories.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Menlo Research / Asimov (existing entry update)
- Institution: Menlo Research
- Homepage: https://www.menlo.ai/
- GitHub: https://github.com/menloresearch
- Lab / Department: Applied R&D / Asimov / Cyclotron locomotion team
- Key Topics: open-source humanoid / bipedal locomotion / reinforcement learning / AMP / benchmarking / sim-to-real
- Notes: Update to the existing note, which said the locomotion policy was still forthcoming. Cyclotron now publishes Asimov-1 locomotion training, export and benchmarking code with a sim-to-real demonstration, and a public 65-scenario benchmark exists on Hugging Face.

### Dynamic Legged Systems Lab / IIT (existing entry update)
- Institution: Istituto Italiano di Tecnologia
- GitHub: https://github.com/iit-DLSLab
- Lab / Department: Dynamic Legged Systems Lab
- Key Topics: quadruped / legged manipulation / vision-language-action / real-robot deployment
- Notes: New source signal: Semini, Barasuol, Turrisi and Amatucci co-author the Go2 + Piper VLA deployment study (arXiv:2610.32271), which extends the lab beyond fault-tolerant locomotion into learned loco-manipulation.

### Berkeley Humanoids (organization signal)
- Institution: UC Berkeley (per the GitHub organization profile: "a team at UC Berkeley aiming to build full-stack humanoid platform")
- GitHub: https://github.com/Berkeley-Humanoids
- Key Topics: humanoid / Berkeley Lite hardware / motion retargeting / motion datasets
- Notes: The organization now publishes a retargeting toolkit, a Hugging Face motion dataset and a motion browser Space for Lite Pro. It was previously seen only for build infrastructure (2026-08-10 draft). Students and representative works omitted pending verification.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

No new verified job signals today. Checked: EPFL BioRob's humanoid neuromechanics PhD and postdoc posting, which its official page now marks as closed. It was not in jobs.md, so no removal is needed. Reminder: the Aarhus A3 Lab Physical AI PhD from the 2026-10-26 draft closes on 2026-11-01.

</details>
