[English](../../drafts/legged-daily-2026-07-06.md) | **中文**
# 腿足机器人日报 - 2026-07-06

## 摘要
- 本次检索到的近期 arXiv 腿足机器人投稿集中在：人形机器人遥操作、执行器层面的 sim-to-real 迁移，以及更可解释的四足步态强化学习。
- HEFT 是高信号人形遥操作论文：目标是 175 cm / 65 kg 全尺寸人形平台，并展示最高 24 kg 真实负载下的运动跟踪。
- Actuator Reality Shaping 值得跟踪：它不是只提高仿真器保真度，而是把真实硬件执行器的闭环响应整形成训练时假设的理想动力学接口。
- 基于时序逻辑规格的四足步态学习把形式化方法接入 PPO 奖励塑形，适合关注可控步态设计的人继续看。
- 仓库侧值得预览的更新包括：用于人形动作模仿 / 重定向的 ProtoMotions3、用于可微浮动基接触动力学的 FoCoDyn、以及用于泛化深度感知四足运动的 MGDP。
- 机会信号仍以 EPFL BioRob 最明确：官方页面仍列出 2026 Fall 的人形机器人 / 人类运动神经力学方向 Postdoc 和 PhD 岗位。

<details>
<summary><strong>新论文</strong></summary>

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid / teleoperation / motion tracking / payload handling / sim-to-real
- Summary: 提出 HEFT 全尺寸人形机器人遥操作框架，通过 Privileged Motion Guidance 和 Windowed Payload Curriculum，让带噪 VR 参考动作更适合真实负载下的人形运动跟踪。
- Notes: 部署在 L7 机器人上（175 cm、65 kg），展示前进 / 后退、转身、深蹲以及最高 24 kg 负载；项目页为 https://heft.axell.top/。

### Actuator Reality Shaping for Zero-Shot Sim-to-Real Robot Learning
- Link: https://arxiv.org/abs/2607.02205
- Source: arXiv cs.RO
- Date: 2026-07-02
- Authors: Satoshi Yamamori, Koji Ishihara, Kentaro Minamikawa, Kiyoharu Ohomori, Taiyo Yazaki, Norikazu Sugimoto, Jun Morimoto
- Topics: sim-to-real / actuator dynamics / robot learning / humanoid / wheeled-legged robot
- Summary: 提出把真实执行器闭环响应整形成仿真训练中假设的理想二阶参考动力学，从而不依赖任务级微调或学习型执行器模型实现 zero-shot 部署。
- Notes: 在单关节高减速比伺服、7-DoF 机械臂到达任务、轮腿机器人爬坡和人形行走上验证；可作为腿足 RL 部署中的执行器接口思路跟踪。

### Learning Gait-Aware Quadruped Locomotion with Temporal Logic Specifications
- Link: https://arxiv.org/abs/2607.00442
- Source: arXiv cs.RO / cs.AI
- Date: 2026-07-01
- Authors: Merve Atasever, Cagan Bakirci, Alfredo Reina Corona, Keyan Azbijari, Jyotirmoy V. Deshmukh
- Topics: quadruped / reinforcement learning / gait specification / signal temporal logic / MuJoCo XLA
- Summary: 用 Signal Temporal Logic 模板描述步态、安全、同步、速度跟踪和执行器约束，再把鲁棒性指标转换成 PPO 可用的稠密奖励。
- Notes: 在 Google Barkour 四足机器人和 MuJoCo XLA / MJX 中实现，覆盖 walking-trot、trot、bound 三种速度 / 步态区间；项目页为 https://stl-locomotion.github.io/。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### NVlabs/ProtoMotions
- Link: https://github.com/NVlabs/ProtoMotions
- Category: simulator / RL / retargeting / toolkit
- Robot Type: humanoid / digital human
- Simulator: Isaac Gym / Newton / MuJoCo
- Deploy: sim / hardware
- Summary: 面向物理仿真人和人形机器人的 GPU 加速仿真与学习框架，支持 AMASS 规模动作模仿、基于 PyRoki 的机器人重定向，以及跨多个物理引擎的策略测试。
- Notes: README 描述的是 ProtoMotions3，Apache-2.0 许可；包含 AMASS / BONES 工作流、H1_2 和 G1 示例，以及真实硬件部署方向。

### mstoelzle/focodyn
- Link: https://github.com/mstoelzle/focodyn
- Category: control / toolkit
- Robot Type: legged / humanoid
- Simulator: none
- Deploy: data / toolkit
- Summary: 面向腿足机器人的可微浮动基动力学与接触位姿雅可比工具包，适合 CBF/CLF、轨迹优化，以及需要刚体动力学 / 接触运动学梯度的学习流程。
- Notes: Python >=3.11 包，封装 Adam 的 PyTorch 后端；目前包含 Unitree G1 URDF/MJCF 资产、控制仿射 f(x) / g(x)、可微足端接触位姿和 Viser 可视化器。

### arclab-hku/MGDP
- Link: https://github.com/arclab-hku/MGDP
- Category: RL / perception / simulator
- Robot Type: quadruped
- Simulator: Isaac Gym / NVIDIA Warp sensors
- Deploy: sim
- Summary: MGDP 的代码实现，面向基于深度感知的泛化四足运动，使用低维地形特征、显式深度去噪和地形自适应奖励。
- Notes: 仓库 README 声称关联 Advanced Science 2026 论文；支持多四足机器人训练 / 微调流程和可视化脚本。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### HEFT / Jianyu Chen 相关信号
- Institution: not verified from arXiv page alone
- Homepage: https://heft.axell.top/
- Key Topics: humanoid / teleoperation / motion tracking / payload handling / robot learning
- Notes: HEFT 是新的 arXiv 信号，重点是全尺寸人形机器人在真实负载下的遥操作。后续应验证项目页、代码 / 视频开放情况和作者实验室归属，再决定是否加入正式 `labs.md`。

### STL Locomotion / Jyotirmoy V. Deshmukh 合作作者信号
- Institution: not verified from arXiv page alone
- Homepage: https://stl-locomotion.github.io/
- Key Topics: quadruped / formal methods / signal temporal logic / reinforcement learning / gait control
- Notes: 这篇四足步态论文把时序逻辑规格与腿足 RL 连接起来，是值得跟踪的 source-network 信号。后续应验证项目页和作者归属后，再决定是否加入 `labs.md`。

### NVIDIA / ProtoMotions 信号
- Institution: NVIDIA Research / NVLabs
- GitHub: https://github.com/NVlabs/ProtoMotions
- Key Topics: humanoid / digital human simulation / motion imitation / retargeting / robot learning
- Notes: ProtoMotions3 仍是人形机器人学习基础设施的重要跟踪源，因为它连接了 AMASS 规模动作模仿、机器人重定向和多仿真器策略评测。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: 官方 openings 页面仍列出 1 个 Postdoc 和 1 个 PhD 岗位，方向是用人形机器人研究和利用人类运动神经力学，包含数值神经力学仿真、生物启发运动控制器和强化学习。

### Proposed Removal / Stale Item
- Current Status: none identified in this run
- Reason: 今日检查中没有确认已过期、需要删除的跟踪岗位。
- Source Checked: EPFL BioRob 官方 openings 页面和仓库现有 `jobs.md` 上下文。

</details>
