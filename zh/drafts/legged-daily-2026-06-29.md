[English](../../drafts/legged-daily-2026-06-29.md) | **中文**
# Legged Daily - 2026-06-29

## 摘要
- 本轮覆盖 2026-06-23 草稿之后的新信号，最强的一批集中在 6 月 24-26 日的 arXiv 投稿。
- 最重要的四足信号是 Uni-Mo / Quad-Imaginarium：用生成式视频先验构建 Unitree Go2 运动数据，开放 7,488 条语言标注运动，并报告了真机验证。
- 最重要的人形全身控制信号是 SceneBot：把参考动作和逐连杆接触标签作为统一接口，覆盖自由空间运动、地形通过和接触丰富的全身操作。
- Berkeley MPC Lab 及合作者给出了 Go2-W 竞速 / 控制信号，并开放了主动侧倾控制 MPC 的补充代码。
- 本轮未进入前三论文但值得继续观察的项目包括：LimX Oli 人形 loco-manipulation 的 CWI、可部署人形步态数据整理管线 Booster Lab、Unitree G1 少样本动态技能 TaskNPoint，以及用 MPC 轨迹偏置 locomotion RL 的 MPC-Injection。
- 本轮没有核验到足够可信的新招聘条目；机会列表建议暂不变，等下次找到官方直链再加入。

<details>
<summary><strong>新论文</strong></summary>

### Unleashing Infinite Motion: Scaling Expressive Quadrupedal Motion via Generative Video Priors
- Link: https://arxiv.org/abs/2606.28237
- Source: arXiv
- Date: 2026-06-26
- Authors: Youzhi Liu, Li Gao, Yifei Qian, Liu Liu, Yang Cai, Ziqiao Li
- Topics: quadruped / motion dataset / generative video priors / reinforcement learning / Unitree Go2 / sim-to-real
- Summary: 提出 Uni-Mo 管线：用 LLM 生成运动提示词，用视频扩散先验合成四足行为，再提升到 3D 轨迹并训练 Unitree Go2 跟踪策略；开放的 Quad-Imaginarium 数据集包含 7,488 条语言标注运动、总时长 18.5 小时，并报告在 392 条随机采样真机动作上达到 96.7% 部署成功率。
- Notes: 高信号数据集 / 管线候选，核心价值在于绕开动物动捕和遥操作，直接缓解四足机器人运动数据稀缺问题。

### SceneBot: Contact-Prompted General Humanoid Whole Body Tracking with Scene-Interaction
- Link: https://arxiv.org/abs/2606.27581
- Source: arXiv
- Date: 2026-06-25
- Authors: Sirui Chen, Shibo Zhao, Zhen Wu, Jiaman Li, Guanya Shi, C. Karen Liu
- Topics: humanoid / whole-body tracking / contact-rich locomotion / terrain traversal / loco-manipulation / reinforcement learning
- Summary: 提出统一的人形机器人动作跟踪框架，用参考动作和逐连杆接触标签共同条件化单一策略，并通过 hindsight scene reconstruction 从重定向人体动作中推断接触丰富的场景交互图；演示覆盖自由空间动作、地形通过、物体交互和搬箱上楼等任务。
- Notes: 对接触条件化人形控制很值得跟踪；项目页说明代码和数据将开源。

### Racing a Wheeled Quadruped: Active Load Transfer Mitigation via Model Predictive Control
- Link: https://arxiv.org/abs/2606.26313
- Source: arXiv
- Date: 2026-06-24
- Authors: Marla Eisman, Brian Lam, Samuel Sonnino, Francesco Borrelli
- Topics: wheeled quadruped / Unitree Go2-W / MPC / reinforcement learning / active suspension / high-speed locomotion
- Summary: 面向 Unitree Go2-W 自动竞速提出分层控制栈：离线最优赛线生成、在线 MPC 降低侧向载荷转移，以及低层全身 RL 策略；实车赛道实验报告平均 LTR 最高降低 44%，最快圈速提升 8.7%，峰值侧向加速度提升 21.3%。
- Notes: 这是学习型 locomotion 之外很实用的控制信号，公开仓库能直接看到 vehicle-dynamics/MPC 层。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### GaoLii/Quad-Imaginarium
- Link: https://github.com/GaoLii/Quad-Imaginarium
- Category: dataset / retargeting / RL / quadruped motion
- Robot Type: quadruped / Unitree Go2
- Simulator: 仓库摘要未明确指定；论文/仓库报告了仿真与真机验证
- Deploy: data / hardware validation reported
- Summary: Quad-Imaginarium 官方数据仓库，包含 7,488 条通过视频先验生成、带语言标注的四足机器人运动，并以 Unitree Go2 构型空间保存。
- Notes: README 报告总时长 18.5 小时、24 fps、双语言标注，以及 392 条真实 Go2 抽样动作验证。

### meisman-ucb/go2w-roll-control-mpc
- Link: https://github.com/meisman-ucb/go2w-roll-control-mpc
- Category: MPC / control / simulation / wheeled quadruped racing
- Robot Type: wheeled quadruped / Unitree Go2-W
- Simulator: dynamic-bicycle closed-loop simulation
- Deploy: sim / hardware experiment video and paper results
- Summary: Go2-W 主动侧倾控制 MPC 的补充代码，包含赛线生成、输出纵向加速度与偏航/侧倾力矩的 dynamic-bicycle MPC、仿真脚本和绘图资源。
- Notes: 适合加入高速度轮足控制观察列表；注意该仓库主要开放高层 MPC，不是完整低层机器人策略。

### SceneBot Project Page
- Link: https://ericcsr.github.io/scenebot/
- Category: project page / browser demo / humanoid whole-body tracking
- Robot Type: humanoid / Unitree G1
- Simulator: MuJoCo browser demo
- Deploy: browser / code and data announced as forthcoming
- Summary: SceneBot 项目页，提供交互式浏览器 MuJoCo demo，以及物体交互、地形通过、自由空间动作、遥操作和重建场景等视频。
- Notes: 在代码/数据正式开源前，先作为项目源跟踪；不要把它当作已发布代码库处理。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### SceneBot Team / Amazon FAR, Stanford University, CMU
- Institution: Amazon Frontier AI & Robotics; Stanford University; Carnegie Mellon University
- Homepage: https://ericcsr.github.io/scenebot/
- arXiv: https://arxiv.org/abs/2606.27581
- Key Topics: humanoid / whole-body tracking / contact-rich control / terrain interaction / loco-manipulation
- Notes: 项目页列出 Amazon FAR、Stanford、CMU 关联，作者中包括 Guanya Shi 和 C. Karen Liu；适合跟踪接触条件化人形控制与场景交互数据。

### Berkeley MPC Lab / Francesco Borrelli collaborators
- Institution: University of California, Berkeley; Politecnico di Milano collaboration on the Go2-W paper
- Homepage: https://www.mpc.berkeley.edu/
- GitHub: https://github.com/meisman-ucb/go2w-roll-control-mpc
- arXiv: https://arxiv.org/abs/2606.26313
- Lab / Department: Model Predictive Control Lab
- Key Topics: MPC / constrained predictive control / robotics / wheeled quadruped racing / active roll control
- Notes: 该实验室聚焦约束预测控制的理论与实时实现；Go2-W 竞速论文是一个明确的腿足 / 轮足机器人跟踪信号。

### Quad-Imaginarium / Uni-Mo Authors
- Homepage: https://github.com/GaoLii/Quad-Imaginarium
- arXiv: https://arxiv.org/abs/2606.28237
- GitHub: https://github.com/GaoLii/Quad-Imaginarium
- Key Topics: quadruped / motion generation / video diffusion priors / language-annotated datasets / Unitree Go2
- Notes: 因为论文开放大规模四足运动数据集并报告真机验证，建议持续观察作者网络；正式写入 `labs.md` 前还需要核验具体机构 / 实验室映射。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### No new verified job signal
- Type: watching
- Source: this 2026-06-29 search pass
- Deadline: unknown
- Topics: legged robotics / humanoid / quadruped / locomotion / control
- Status: no confirmed addition
- Notes: 本轮没有核验到足够可信、带官方直链的新机会。现有机会条目建议保持不变，下次继续查官方实验室 / careers 页面。

</details>
