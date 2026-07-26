**English** | [中文](../zh/drafts/legged-daily-2026-07-26.md)
# Legged Daily - 2026-07-26

## Summary
- Two previously untracked papers met today’s relevance bar: ZONDA demonstrates multi-floor object navigation and dynamic pedestrian avoidance on a physical Direct Drive Tech TITA biped, while Robostral Navigate presents a monocular vision-language navigation model intended to transfer across wheeled, legged, and aerial embodiments.
- ZONDA is the more direct legged-robotics result: it combines geometry-conditioned stair traversability, multi-view VLM target verification, and anticipatory pedestrian avoidance, with real biped deployment.
- Robostral Navigate is a high-signal adjacent foundation-model result, but its paper’s disclosed hardware validation uses Galaxea R1 and JetAuto wheeled bases rather than a legged platform; its legged applicability is therefore a transfer claim, not a demonstrated legged deployment.
- No new public repository met the inclusion bar. Neither paper linked a paper-specific public implementation or model release during verification.
- Mistral AI is actively recruiting an AI Scientist and a Research Engineer for its Paris robotics team; both official postings focus on real-world mobile manipulation, embodied AI, navigation, and physical deployment. The previously tracked LAAS-CNRS/JRL humanoid PhD remains active until 2026-07-31.

<details>
<summary><strong>New Papers</strong></summary>

### ZONDA: Zero-shot Object Navigation with Dynamic Avoidance in Multi-floor Environments
- Link: https://arxiv.org/abs/2607.21025
- Source: arXiv
- Date: 2026-07-23
- Authors: Shaomin Liang, Xuanhong Liao, Shiyao Zhang
- Topics: biped navigation / object goal navigation / multi-floor planning / stair traversal / dynamic obstacle avoidance / vision-language models
- Summary: ZONDA combines a height-difference traversability map, heuristic cross-floor exploration, multi-view VLM target verification, and predicted pedestrian trajectories for zero-shot object navigation in multi-floor dynamic environments.
- Notes: The system is evaluated in Habitat on HM3D, MP3D, and the authors’ HM3D-DYNA extension, plus a physical Direct Drive Tech TITA biped deployment. Its platform transfer mechanism replaces a learned low-level PointNav policy with platform-dependent geometric limits, although the real-world evidence is currently limited to one biped platform. No paper-specific public code repository was found during verification.

### Robostral Navigate
- Link: https://arxiv.org/abs/2607.20785
- Source: arXiv
- Date: 2026-07-22
- Authors: Arjun Majumdar, Avinash Sooriyarachchi, Benjamin Tibi, Chris Bamford, Elliot Chane-Sane, Guillaume Lample, Khyathi Raghavi Chandu, Ludovic Ho Fuh, Mathieu Poiree, Olivier Duchenne, Rosalie Millner, Srijan Mishra, Theo Cachet, Thomas Chabal
- Topics: vision-language navigation / monocular navigation / cross-embodiment transfer / reinforcement learning / simulation data / mobile robots
- Summary: Robostral Navigate is an 8B vision-language model that predicts image-space waypoints from language instructions and monocular RGB history, using 2.4 million simulated trajectories, prefix-cached training, and online RL to support navigation across different robot geometries.
- Notes: The paper reports 77.4% success on R2R-CE validation unseen and 75.1% on English RxR-CE validation unseen. It claims transfer across wheeled, legged, and aerial robots, but the disclosed physical deployments use Galaxea R1 and Hiwonder JetAuto wheeled platforms; legged deployment remains unverified. Mistral’s official release page did not provide public model weights or a code repository during verification.

</details>

<details>
<summary><strong>New Repos</strong></summary>

No new public repository met today’s inclusion bar. The selected papers did not link paper-specific public code or model releases, and no independently verified recent repository offered enough legged-robotics relevance and documentation to justify inclusion.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Shiyao Zhang / ZONDA collaboration
- Institution: Great Bay University / Southern University of Science and Technology / Guangdong Direct Drive Technology
- Homepage: https://arxiv.org/abs/2607.21025
- arXiv: https://arxiv.org/abs/2607.21025
- Lab / Department: School of Advanced Engineering / School of Automation and Intelligent Manufacturing / Direct Drive Technology
- Key Topics: biped navigation / multi-floor exploration / dynamic obstacle avoidance / embodied perception / VLM-based target verification
- Notes: This university-industry collaboration is a useful source for navigation stacks validated on the Direct Drive Tech TITA biped. ZONDA’s combination of stair traversal, open-vocabulary object search, and pedestrian-aware planning makes the team particularly relevant to legged autonomy in human environments.
- Students and Representative Works:
  - [Shaomin Liang](https://arxiv.org/search/cs?searchtype=author&query=Liang,+S) — [ZONDA](https://arxiv.org/abs/2607.21025)

### Mistral AI Science Robotics
- Institution: Mistral AI, France
- Homepage: https://mistral.ai/news/robostral-navigate/
- arXiv: https://arxiv.org/abs/2607.20785
- Lab / Department: AI Science Robotics
- Key Topics: embodied navigation / vision-language models / cross-embodiment transfer / online reinforcement learning / mobile manipulation
- Notes: Robostral Navigate marks a concrete expansion of Mistral’s in-house foundation-model work into embodied navigation. The team is also hiring robotics scientists and engineers for physical deployment, making it worth tracking for future legged-platform validation, model availability, and mobile-manipulation work.
- Students and Representative Works:
  - [Theo Cachet](https://arxiv.org/search/cs?searchtype=author&query=Cachet,+T) — [Robostral Navigate](https://arxiv.org/abs/2607.20785)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Mistral AI Robotics — AI Scientist, Robotics
- Type: Research Scientist / Full-time
- Location: Paris, France; onsite
- Source: https://jobs.ashbyhq.com/mistral.ai/c70522d8-73cb-46ed-9f9a-5cb807420485
- Deadline: rolling / unknown
- Topics: mobile manipulation / embodied intelligence / vision-language models / robot learning / navigation / simulation / deployment
- Status: active; official listing published 2026-07-03
- Notes: Develops scalable AI methods and infrastructure for general-purpose mobile manipulation robots, including VLM/VLA capabilities and deployment on physical platforms.

### Mistral AI Robotics — Research Engineer, Robotics
- Type: Research Engineer / Full-time
- Location: Paris, France; onsite
- Source: https://jobs.ashbyhq.com/mistral.ai/25944723-62e2-498e-8149-a588907c39d6
- Deadline: rolling / unknown
- Topics: mobile manipulation / real-robot deployment / data pipelines / robot fleets / ROS / control / perception
- Status: active; official listing published 2026-07-03
- Notes: Focuses on deploying and refining AI models on real robots, building training-data pipelines, maintaining diverse robot fleets, and validating systems in production-like environments.

### LAAS-CNRS Gepetto / CNRS-AIST JRL — PhD in Humanoid Robotics
- Type: PhD
- Location: Toulouse, France, with part of the work at JRL in Tsukuba, Japan
- Source: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59 (posting local time)
- Topics: humanoid locomotion / reinforcement learning / online MPC / whole-body control / hybrid contact decisions
- Status: active; previously tracked, deadline reminder
- Notes: The project couples RL-based discrete contact, gait, and behavior decisions with online MPC for feasible continuous whole-body motion, with planned validation on PAL Robotics Kangaroo and/or Unitree humanoids.

</details>
