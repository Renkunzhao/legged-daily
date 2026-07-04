**English** | [中文](../zh/drafts/legged-daily-2026-07-04.md)
# Legged Daily - 2026-07-04

## Summary
- No new arXiv cs.RO humanoid/legged submissions were found for 2026-07-03 to 2026-07-04 UTC in the focused arXiv API check; today is therefore a light incremental run rather than a forced paper list.
- RSS 2026 accepted-paper pages remain the strongest current source: the Humanoids session contains several high-signal locomotion / loco-manipulation papers, including Perceptive Humanoid Parkour and an open humanoid loco-manipulation foundation-model paper.
- GitHub follow-up: `zitongbai/legged_lab` has a 2026-06-30 update adapting the Isaac Lab extension to Isaac Lab v2.3.2; `yang-zj1026/legged-loco` remains a useful Go2/H1 low-level locomotion training baseline but is not a new item today.
- Lab signal: Guanya Shi / Karen Liu / Pieter Abbeel / collaborators have a current RSS 2026 humanoid parkour paper using Unitree G1 real-world experiments.
- Job signal: EPFL BioRob's official page still lists a Fall 2026 humanoid neuromechanics PhD / Postdoc project summary; based on today's page text, treat this as active-watch and verify exact role status before applying.

<details>
<summary><strong>New Papers</strong></summary>

### Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching
- Link: https://roboticsconference.org/program/papers/20/
- Source: RSS 2026 accepted papers / official program page
- Date: 2026-07-04 check; RSS 2026 program page
- Authors: Zhen Wu, Xiaoyu Huang, Lujie Yang, Yuanhang Zhang, Xi Chen, Pieter Abbeel, Rocky Duan, Angjoo Kanazawa, Carmelo Sferrazza, Guanya Shi, Karen Liu
- Topics: humanoid, parkour, motion matching, depth-based policy, reinforcement learning, Unitree G1
- Summary: Proposes Perceptive Humanoid Parkour, a modular framework that composes retargeted human skills with motion matching, trains motion-tracking RL experts, and distills them into a depth-based multi-skill student policy for autonomous Unitree G1 parkour over obstacles.
- Notes: Official abstract reports real-world climbs up to 1.25 m, about 96% of robot height, plus long-horizon multi-obstacle traversal with real-time perturbation adaptation.

### Ψ₀: An Open Foundation Model Towards Universal Humanoid Loco-Manipulation
- Link: https://roboticsconference.org/program/papers/21/
- Source: RSS 2026 accepted papers / official program page
- Date: 2026-07-04 check; RSS 2026 program page
- Authors: Songlin Wei, Hongyi Jing, Boqian Li, Zhenyu Zhao, Jiageng Mao, Zhenhao Ni, Sicheng He, Sheng Zang, Xiawei Liu, Kaidi Kang, Jie Liu, Weiduo Yuan, Marco Pavone, Di Huang, Yue Wang
- Topics: humanoid, loco-manipulation, foundation model, VLM, flow-based action expert, real-robot data
- Summary: Introduces Psi-Zero, a staged humanoid loco-manipulation model that pre-trains a VLM backbone on egocentric human video and post-trains a flow-based action expert on humanoid robot trajectories.
- Notes: Official abstract says the ecosystem will be open-sourced, including data processing/training pipeline, model, and real-time action inference engine; code availability should be rechecked later.

### HAIC: Humanoid Agile Object Interaction Control via Dynamics-Aware World Model
- Link: https://roboticsconference.org/program/papers/13/
- Source: RSS 2026 accepted papers / official program page
- Date: 2026-07-04 check; RSS 2026 program page
- Authors: Dongting Li, Xingyu Chen, Qianyang Wu, Bo Chen, Sikai Wu, Hanyu Wu, Guoyao Zhang, Liang Li, Mingliang Zhou, Diyun Xiang, Jianzhu Ma, Qiang Zhang, Renjing Xu
- Topics: humanoid, object interaction, world model, proprioception, Unitree G1, loco-manipulation
- Summary: Proposes a dynamics-aware world-model framework for humanoid interaction with underactuated objects, using proprioceptive history to infer object velocity/acceleration and support agile tasks such as skateboarding and cart pushing/pulling on Unitree G1.
- Notes: Relevant because it moves beyond pure locomotion into contact-rich humanoid object dynamics without relying on external state estimation.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### zitongbai/legged_lab
- Link: https://github.com/zitongbai/legged_lab
- Category: RL / simulator extension / humanoid motion imitation
- Robot Type: humanoid / legged robots; Unitree G1 highlighted
- Simulator: Isaac Lab v2.3.2
- Deploy: simulation / policy training stack
- Summary: Isaac Lab extension for legged robot reinforcement learning with DeepMimic and adversarial motion-prior support for humanoids; the README news log says the project adapted to Isaac Lab v2.3.2 on 2026-06-30 and fixed a pretrained checkpoint import path.
- Notes: Already tracked previously; today's value is the verified update, not a brand-new repository.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Guanya Shi / Karen Liu / Pieter Abbeel / Angjoo Kanazawa collaboration line
- Institution: CMU / Stanford / UC Berkeley collaboration line, based on RSS 2026 paper authorship
- Source: https://roboticsconference.org/program/papers/20/
- Key Topics: humanoid parkour, motion matching, human-skill retargeting, depth-based locomotion policy, Unitree G1
- Update: RSS 2026 lists Perceptive Humanoid Parkour in the Humanoids session, with real-world Unitree G1 experiments on tall obstacle climbing and long-horizon parkour. This is a strong follow-up source for humanoid agility and human-motion composition.

### Yue Wang / Di Huang / Marco Pavone collaboration line
- Institution: institutional affiliation not verified from the RSS page alone
- Source: https://roboticsconference.org/program/papers/21/
- Key Topics: humanoid loco-manipulation, foundation models, egocentric human video pretraining, humanoid action expert
- Update: RSS 2026 lists Psi-Zero as an open foundation-model direction for humanoid loco-manipulation, claiming future open-source release of the training/data pipeline, model, and inference engine.

### EPFL BioRob / Auke Ijspeert
- Institution: EPFL
- Source: https://www.epfl.ch/labs/biorob/openings/
- Key Topics: humanoid locomotion, human neuromechanics, bio-inspired control, reinforcement learning
- Update: Official openings page still describes a Fall 2026 project on investigating and leveraging human locomotion neuromechanics using humanoid robots; because prior checks indicated role-status nuance, exact PhD/postdoc availability should be verified before action.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### EPFL BioRob
- Type: PhD / Postdoc project page; exact role availability needs verification
- Location: Lausanne, Switzerland
- Source: official website, https://www.epfl.ch/labs/biorob/openings/
- Deadline: rolling / until filled; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid, neuromechanics, locomotion, reinforcement learning, bio-inspired controllers
- Status: active-watch
- Summary: The official page continues to list a Fall 2026 humanoid neuromechanics project and describes a PhD/postdoc track; treat as worth monitoring, but verify whether the postdoc slot is still open before recommending application.

### No newly verified industry / faculty job additions today
- Status: no addition
- Reason: General web search hit bot-detection challenges today; no additional official, high-confidence opening was verified beyond EPFL BioRob during this run.

</details>
