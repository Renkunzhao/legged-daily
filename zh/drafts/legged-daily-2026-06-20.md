[English](../../drafts/legged-daily-2026-06-20.md) | **中文**
# Legged Daily - 2026-06-20

## 摘要
- 今天最强的技术信号是 SCAN-Planner：上海交通大学的四足局部规划器，在狭窄 / 3D 场景里显式建模 yaw-aware whole-body collision，并承诺后续开源代码。
- ForEnt 是有用的 field robotics 数据集信号：Unitree Go2 在森林中采集约 1.7 km、11 个序列、69 次 entrapment 事件，包含同步 RGB-D、LiDAR、本体感知和第三视角视频。
- humanoid data-standard 论文更偏基础设施而不是控制算法，但值得跟踪：它把人形机器人数据集设计与 ISO/WD 26264-1 联系起来，强调可追踪的 embodied-interaction data。
- GitHub 信号今天故意收窄：只列 AugMPC 和 IHMC Open Robotics Software 两个有用 / 活跃条目；此前已记录过的 BotBrain 和 Unitree RL Mjlab 不重复收录。
- 招聘信号：今天没有验证到新的官方腿足 / 人形岗位。第三方聚合页出现 Chalmers RAIL 的 legged humanoid robotics 博后线索，但本轮没有找到官方招聘页，所以标为未确认。

<details>
<summary><strong>新论文</strong></summary>

### SCAN-Planner: Spatial Collision-Aware Local Planning for Route-Guided Long-Range Quadruped Navigation
- Link: https://arxiv.org/abs/2606.19555
- Source: arXiv
- Date: 2026-06-17
- Authors: Han Zheng, Zhe Chen, Yiwen Fu, Ming Yang, Tong Qin
- Topics: quadruped, navigation, local planning, whole-body collision checking, 3D occupancy map, stair / clutter navigation
- Summary: 提出面向长距离四足导航的 spatial collision-aware local planner，用 yaw-aware twin-cylinder footprint、inflated 3D occupancy map 上的稀疏 whole-body collision query、projected A* guidance 和 robot-centric sliding map 来处理狭窄空间、3D 障碍与长距离路线引导。
- Notes: arXiv HTML 显示作者单位为上海交通大学，并写明代码将发布在 https://github.com/wuyi2121/SCAN-Planner。本轮未确认仓库已可用，后续需要复查。

### ForEnt: A Multi-Modal Dataset for Characterizing Quadruped Robot Entrapments in Forest Environments
- Link: https://arxiv.org/abs/2606.19675
- Source: arXiv
- Date: 2026-06-18
- Authors: Natapat Kirdwichai, Danesh Tarapore
- Topics: quadruped, field robotics, forest autonomy, entrapment detection, dataset, Unitree Go2
- Summary: 提出 ForEnt，多模态森林 entrapment 数据集，用 Unitree Go2 在英国 Southampton Common Woodlands 的 8 个森林点位采集，目标是研究腿被藤蔓 / 植被缠住导致失稳翻倒等失败模式。
- Notes: 摘要报告约 1.7 km traverse、11 个序列、69 次 entrapment 事件，包含同步 RGB-D、LiDAR、本体感知和第三视角视频。arXiv HTML 显示作者来自 University of Southampton Faculty of Engineering and Physical Sciences。

### Data Standards for Humanoid Robotics: The Missing Infrastructure for Physical AI
- Link: https://arxiv.org/abs/2606.19769
- Source: arXiv
- Date: 2026-06-18
- Authors: Shaoshan Liu, Xiugong Qin, Xuan Wu, Xuan Xia, Ning Ding, Jialu Liu, Jie Tang
- Topics: humanoid, datasets, Physical AI, standardization, ISO/TC 299/WG 16, data infrastructure
- Summary: 认为人形机器人数据需要围绕 embodied interaction trace、physical coherence、metadata、provenance、quality、versioning、traceability 以及不同能力域的数据语法建立标准。
- Notes: 不是 locomotion 方法论文，但对 humanoid research infrastructure 有关，因为它引用 ISO/WD 26264-1, Humanoid robot datasets -- Part 1: General requirements。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### AugMPC
- Link: https://github.com/AndrePatri/AugMPC
- Source: GitHub
- Date: updated 2026-06-19
- Language: Python / robotics stack
- Topics: RL-augmented MPC, legged locomotion, hybrid locomotion, contact scheduling, sim-to-real
- Summary: 面向 non-gaited legged / hybrid locomotion 的 RL-Augmented Model Predictive Control 栈，RL agent 选择 contact schedules / twist commands，底层由 MPC controllers 执行。
- Notes: README 报告在工作站上可达到 50+× real-time experience generation、800 parallel environments / MPC instances at 20 Hz，支持 SAC / PPO，并展示 Centauro 等 sim-to-sim / sim-to-real 案例。GitHub API 显示 license 为 GPL-2.0。它不是新仓库，但 2026-06-19 有 push，且此前 archive 未收录。

### IHMC Open Robotics Software
- Link: https://github.com/ihmcrobotics/ihmc-open-robotics-software
- Source: GitHub
- Date: updated 2026-06-18
- Language: Java / Gradle robotics stack
- Topics: humanoid, legged locomotion, momentum-based control, optimization, robotics software infrastructure
- Summary: IHMC 成熟机器人软件栈，包含 legged locomotion algorithms 和 momentum-based controller core，历史上支持 Nadia、Valkyrie、Alex 等人形机器人。
- Notes: 这不是新发布，但属于仍在维护的基础设施仓库，适合加入 watchlist。GitHub API 显示 license 为 Apache-2.0。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Tong Qin group / Shanghai Jiao Tong University
- Link: https://arxiv.org/html/2606.19555v1
- Source: arXiv HTML
- Date: 2026-06-17
- Institution: Shanghai Jiao Tong University
- People: Han Zheng, Zhe Chen, Yiwen Fu, Ming Yang, Tong Qin
- Topics: quadruped navigation, local planning, whole-body collision checking, 3D unstructured scenes
- Signal: SCAN-Planner 论文展示了四足机器人在狭窄室内、楼梯、密集 clutter、3D 非结构场景和校园长距离导航中的真实实验，并说明代码将发布到 `wuyi2121/SCAN-Planner`。

### University of Southampton — Faculty of Engineering and Physical Sciences
- Link: https://arxiv.org/html/2606.19675v1
- Source: arXiv HTML
- Date: 2026-06-18
- Institution: University of Southampton
- People: Natapat Kirdwichai, Danesh Tarapore
- Topics: field quadrupeds, forest autonomy, entrapment detection, multimodal datasets
- Signal: ForEnt 显示该团队在森林环境 quadruped failure modes 上有具体数据集建设，平台为 Unitree Go2，场景为 Southampton Common Woodlands。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Chalmers RAIL — possible Postdoctoral Researcher in Legged Humanoid Robotics
- Link: https://scholarnexus.ai/position/Postdoctoral-Researcher-In-Legged-Humanoid-Robotics?id=f44b2959-d66a-4058-a362-01bf113aea2d
- Type: Postdoc
- Location: Gothenburg, Sweden
- Source: third-party aggregator; official source not verified in this run
- Deadline: unknown
- Topics: legged humanoid robotics, locomotion, control, experimental platforms
- Status: unconfirmed
- Notes: 第三方页面称 Chalmers University of Technology 的 Robot Athletic Intelligence Lab (RAIL) / Assistant Professor Shivesh Kumar 有一个博后岗位。因为今天没有验证到 Chalmers 官方招聘页，请只把它当作待人工复查线索，不当作已确认岗位。

</details>

## Operator Notes
- Draft only. Do not merge into official daily files until confirmed by 大天才。
- Paper count: 3. Repository count: 2.
- Search quality note: Chalmers 相关 web search 部分触发 bot-detection，所以招聘部分有意保守处理。
