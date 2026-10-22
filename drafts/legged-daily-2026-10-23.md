**English** | [中文](../zh/drafts/legged-daily-2026-10-23.md)
# Legged Daily - 2026-10-23

## Summary
- HuMiT (Tsinghua IIIS / CUHK) tracks a compact reference of root height, root velocity, and four sparse keypoint poses for whole-body G1 teleoperation, reporting about 20 ms from headset input to policy output; training code is public.
- RISE (Stella X. Yu group) lets task costs steer how a fallen humanoid stands up at inference time, through a learned recovery vocabulary and a visual diffusion planner, with real-world demonstrations on a Unitree G1.
- SP-HLM uses five task-critical body poses as the interface between a VLA, a real-time motion generator, and a general motion tracker for humanoid loco-manipulation.
- New repo: `btx0424/active-adaptation`, the RL framework behind FACET, HDMI, GentleHumanoid, and Gallant, with Isaac Sim, MuJoCo, and mjlab backends.
- HoloMotion's README added a 2026-10-22 entry for the H-bot Competition (Track 2 boxing baseline in about 21 minutes on one GPU); v2.1 and the HoloMotion-2 report are still scheduled for late October.
- No new job opening was verified; the EPFL BioRob humanoid neuromechanics PhD/postdoc call is marked CLOSED.

<details>
<summary><strong>New Papers</strong></summary>

### HuMiT: Low-Latency Whole-Body Humanoid Teleoperation via Compact Reference Tracking
- Link: https://arxiv.org/abs/2610.29903
- Source: arXiv
- Date: 2026-10-21
- Authors: Liu Cao, Botian Xu, Ruoqu Chen, Jiajun Liu, Mingzhi Pei, Zihao Wang, Zhongyu Li, Mengdi Xu
- Topics: humanoid / whole-body teleoperation / motion tracking / low latency / sim-to-real
- Summary: A unified tracking policy that needs only a compact per-frame reference (root height, root velocity, and SE(3) poses of four sparse keypoints) and matches methods that use richer reference data, enabling low-latency whole-body humanoid teleoperation.
- Notes: Reports about 20 ms from headset input to policy output and a 65 ms median optical-flow latency; real-world demos on a Unitree G1 include reactive catching and coordinated manipulation. Project page: https://xiaohu-art.github.io/Track/; code: https://github.com/xiaohu-art/Track. Related: ExtremControl (arXiv 2602.11321) on low-latency teleoperation.

### Test-Time Motion Steering for Perceptive Humanoid Fall Recovery
- Link: https://arxiv.org/abs/2610.30061
- Source: arXiv
- Date: 2026-10-21
- Authors: Osher Azulay, Cheng-Lin Hsieh, Stella X. Yu
- Topics: humanoid / fall recovery / diffusion planning / perceptive control / test-time steering
- Summary: RISE learns a recovery vocabulary that links intended movements to motor actions, then uses a visual diffusion planner whose predicted future body states are guided by task costs (heading, rise speed, or path) to steer how the robot stands up without retraining.
- Notes: Simulation shows diverse recoveries, terrain adaptation, and test-time steering; real-world demonstrations are on a Unitree G1. Project page: https://osheraz.github.io/RISE/ (code marked "coming soon").

### SP-HLM: Sparse-Pose-Driven Motion Generation and Whole-Body Control for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.30044
- Source: arXiv
- Date: 2026-10-21
- Authors: Zhaohui Yang, Quanbao Lin, Chengqi Shi, Zhenglang Weng, Jicheng Lin, Boyu Chen, Tengjie Zhu, Guanzhu Ren, Jiahao Xu, Yang Feng, Xiaokang Yang, Yao Mu
- Topics: humanoid / loco-manipulation / VLA / motion generation / motion tracking
- Summary: Uses five task-critical body poses plus a learned latent motion prior as the interface between high-level policy and whole-body control: SP-VLA predicts sparse poses from observations and language, SP-MGM reconstructs full-body motion in real time, and SP-GMT tracks it.
- Notes: The abstract reports improvements in motion tracking and loco-manipulation but gives no headline numbers. Project page: https://sp-hlm.github.io/ (could not be fetched in this run, so code availability is unverified).

</details>

<details>
<summary><strong>New Repos</strong></summary>

### btx0424/active-adaptation
- Link: https://github.com/btx0424/active-adaptation
- Category: RL / toolkit
- Robot Type: general / quadruped / humanoid
- Simulator: Isaac Lab / Isaac Sim (5.1.0+), MuJoCo, mjlab
- Deploy: sim
- Summary: RL framework for legged locomotion and loco-manipulation with automatic shape handling, single-file RL implementations, symmetry augmentation, MuJoCo sim2sim, and a project-scaffolding CLI.
- Notes: The README lists Unitree Go2, G1, A2, and B2 and cites FACET, HDMI, GentleHumanoid, and Gallant as built on it; HuMiT's Track repo depends on it. About 163 stars; no license or release tags were visible.

### xiaohu-art/Track
- Link: https://github.com/xiaohu-art/Track
- Category: motion tracking / RL
- Robot Type: humanoid
- Simulator: Isaac Lab (Isaac Sim 5.1.0)
- Deploy: sim
- Summary: Code linked from the HuMiT project page for training and evaluating PPO reference-motion tracking policies, with optional ONNX export; built on active-adaptation.
- Notes: Minimal README, no visible license or released checkpoints; real-robot deployment code was not seen. Related paper: HuMiT (arXiv 2610.29903).

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Zhongyu Li — The Chinese University of Hong Kong
- Institution: The Chinese University of Hong Kong
- Homepage: https://zyliatzju.github.io/
- X: https://x.com/ZhongyuLi4
- Key Topics: humanoid / whole-body teleoperation / motion tracking / RL / control
- Notes: Update to the existing labs.md entry: co-author of HuMiT (arXiv 2610.29903) with Mengdi Xu (Tsinghua IIIS) and Botian Xu (CUHK), with open training code built on Botian Xu's active-adaptation framework. Botian Xu's role in the group was not verified, so no student line is proposed.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### No newly verified opening
- Source: official-source review
- Status: watching
- Notes: The EPFL BioRob postdoc + PhD call on human-locomotion neuromechanics with humanoid robots is marked CLOSED on the official openings page and is not proposed for jobs.md. The previously proposed LAAS-CNRS safe-RL PhD removal (deadline 2026-07-31, expired) remains pending confirmation.

</details>
