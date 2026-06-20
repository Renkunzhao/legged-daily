[English](../../drafts/legged-daily-2026-06-06.md) | **中文**
# 腿足机器人日报 - 2026-06-06

## 摘要
- 最近 arXiv cs.RO 的人形机器人全身控制更新非常密集，HANDOFF、MotionDisco、TAGA、LadderMan、MPC-RL、GRAIL 都集中出现在 2026-06-03 至 2026-06-04 左右。
- 本次精选论文重点放在可部署的人形机器人 loco-manipulation：紧凑任务空间接口、长时域接触动作自动发现，以及高效 MPC 引导强化学习。
- 仓库信号主要来自人形机器人 loco-manipulation 代码与资源：`mpc-rl` 已发布占位仓库但代码仍在准备中，FALCON 已提供训练、sim2sim 与 sim2real 指令。
- 实验室/来源信号包括 Caltech AMBER 及其合作者的 HANDOFF/MPC-RL、Legged AI Lab 的 RSS 2026 PRIME，以及 NVIDIA DAIR 的 GRAIL 合成数据管线。
- 招聘检查确认 EPFL BioRob、ETH Zurich RSL、RoMI Lab 与 Field AI 官方机会仍活跃；今日没有建议删除的过期条目。

<details>
<summary><strong>新论文</strong></summary>

### HANDOFF: Humanoid Agentic Task-Space Whole-Body Control via Distilled Complementary Teachers
- Link: https://arxiv.org/abs/2606.06493
- Source: arXiv cs.RO
- Date: 2026-06-04
- Authors: Lizhi Yang, Junheng Li, Nehar Poddar, Yiling Hou, Gio Huh, Robert Griffin, Georgia Gkioxari, Aaron Ames
- Topics: humanoid / whole-body control / loco-manipulation / policy distillation / VLM planning
- Summary: 提出 HANDOFF，一个用于 Unitree G1 的全身控制器，以紧凑的任务空间命令作为规划与控制接口，并将运动跟踪、移动、摔倒恢复三个互补教师通过混合专家学生策略蒸馏到一起，从而支持无需任务特定控制器微调的语言驱动任务执行。
- Notes: 长期价值高，因为它同时连接任务规划接口、鲁棒人形移动、操作工作空间和 agentic VLM planning。

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Source: arXiv cs.RO
- Date: 2026-06-04
- Authors: Ilyass Taouil, Michal Ciebelski, Shafeef Omar, Haizhou Zhao, Angela Dai, Aaron M. Johnson, Majid Khadiv
- Topics: humanoid / loco-manipulation / contact-rich motion discovery / LLM-guided search / trajectory optimization / reinforcement learning
- Summary: 提出一个自动化框架，用 LLM 引导的进化搜索、序列式 kinodynamic 轨迹优化和 RL 跟踪策略，发现长时域、接触丰富的人形机器人 loco-manipulation 技能并迁移到真实硬件。
- Notes: 相比依赖遥操作或人体动作重定向的人形机器人管线，它更像是规划与控制侧的互补路线。

### Accelerating and Scaling MPC-Guided Reinforcement Learning for Humanoid Locomotion and Manipulation
- Link: https://arxiv.org/abs/2606.05687
- Source: arXiv cs.RO
- Date: 2026-06-04
- Authors: Junheng Li, Liang Wu, Sergio A. Esteban, Lizhi Yang, Ján Drgoňa, Aaron D. Ames
- Topics: humanoid / MPC / reinforcement learning / locomotion / manipulation / GPU optimization
- Summary: 研究训练阶段 MPC 对人形机器人 RL 的引导，提出基于质心动力学的 MPC reward 与面向批量 GPU 的 πⁿMPC 求解器，用于扩展 MPC-RL 到移动和操作任务，并包含硬件验证。
- Notes: 论文直接关联 `mpc-rl` 仓库；截至本次检查，代码仍标注为即将发布。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### junhengl/mpc-rl
- Link: https://github.com/junhengl/mpc-rl
- Category: RL / MPC / control
- Robot Type: humanoid
- Simulator: unknown
- Deploy: hardware planned / code pending
- Summary: 与 arXiv:2606.05687 对应的官方仓库，主题是 MPC 引导的强化学习，用于人形机器人移动与操作。
- Notes: GitHub README 写明代码正在准备、很快发布；今天应作为 watch item，而不是可直接复现实验的代码。

### LeCAR-Lab/FALCON
- Link: https://github.com/LeCAR-Lab/FALCON
- Category: RL / control / sim2real
- Robot Type: humanoid
- Simulator: Isaac Gym
- Deploy: both
- Summary: 面向力自适应人形机器人 loco-manipulation 的开源实现，提供 Unitree G1 与 Booster T1 风格配置的训练、评估、sim2sim 与 sim2real 部署脚本。
- Notes: README 标注 L4DC 2026 Oral，并给出 Isaac Gym 安装、训练命令、sim2real 指南，以及 ASAP / HumanoidVerse 依赖。

### OpenDriveLab/WholebodyVLA
- Link: https://github.com/OpenDriveLab/WholebodyVLA
- Category: toolkit / resource list / VLA
- Robot Type: humanoid
- Simulator: unknown
- Deploy: resource / references
- Summary: WholeBodyVLA 及相关人形机器人 Vision-Language-Action 工作的资源仓库，核心关注用 latent actions 与 locomotion-oriented RL policy 实现大空间闭环人形 loco-manipulation。
- Notes: README 明确说目前没有开源代码时间表；当前价值主要是整理过的参考列表和项目链接，不是可运行代码。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### AMBER Lab / Aaron Ames and collaborators
- Institution: California Institute of Technology; collaborators include Georgia Tech / FAIR-style vision-language planning links as listed on the paper
- Homepage: https://amber.caltech.edu/
- Key Topics: humanoid / whole-body control / locomotion / manipulation / MPC / safety / policy distillation
- Notes: HANDOFF 与 MPC-RL 都包含 Aaron D. Ames 和 Junheng Li，是人形机器人控制接口与 MPC-guided RL 的高优先级跟踪来源。

### Legged AI Lab / Xiaobin Xiong
- Institution: Shanghai Innovation Institute; UW-Madison collaborators listed on the project page
- Homepage: https://www.leggedai.com/
- Key Topics: legged robots / humanoid / state estimation / contact dynamics / robot learning data
- Notes: RSS 2026 PRIME 项目页描述了面向四足机器人和 Unitree G1 人形机器人的物理一致惯性与运动估计方法，可从机载运动学和电机命令中联合估计接触力与惯性参数。
- Students and Representative Works:
  - [Jiarong Kang](https://www.leggedai.com/author/jiarong-kang-%E5%BA%B7%E5%AE%B6%E8%8D%A3/) — [PRIME](https://www.leggedai.com/publication/2026rss_prime/)
  - [Kunzhao Ren](https://www.leggedai.com/author/kunzhao-ren-%E4%BB%BB%E5%9D%A4%E7%85%A7/) — [PRIME](https://www.leggedai.com/publication/2026rss_prime/)

### NVIDIA DAIR / GRAIL project
- Institution: NVIDIA Research
- Homepage: https://research.nvidia.com/labs/dair/grail/
- Key Topics: humanoid / loco-manipulation / synthetic data / video priors / sim-to-real / Unitree G1
- Notes: GRAIL 展示了一个用 3D assets 和视频基础模型 priors 生成数字数据的管线，生成超过 20,000 条序列，并迁移到 Unitree G1 的物体拾取和爬楼梯任务。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website — https://www.epfl.ch/labs/biorob/openings/
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: 官方页面仍列出 1 个 Postdoc 和 1 个 PhD 机会，研究用人形机器人理解和利用人类行走神经力学，方向包括神经肌肉仿真、仿生控制器和强化学习。

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official website — https://rsl.ethz.ch/the-lab/open-positions.html
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulation / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: 官方页面继续列出持续 PhD/Postdoc 招聘，以及多个与腿足机器人、移动操作、野外部署、控制、学习、规划和硬件设计相关的工程/研究岗位。

### RoMI Lab / Carlos Mastalli
- Type: PhD
- Location: Edinburgh, United Kingdom
- Source: official lab joining page — https://www.romilab.org/joining
- Deadline: as soon as possible / rolling
- Topics: legged robotics / MPC / numerical optimization / optimal control / reinforcement learning / contact physics / state estimation / perception
- Status: active
- Notes: 官方 joining 页面写明 RoMI 有一个 fully funded PhD position 希望尽快招满，也提供 D2AIR 和 SPADS 路径；页面同时说明当前没有 funded postdoc 名额。

### Field AI
- Type: Robotics Autonomy Engineer - Locomotion
- Location: Irvine / Mission Viejo area, California, USA
- Source: Lever official careers page — https://jobs.lever.co/field-ai/00be5e27-c434-4cde-b367-f1688aa7bd2b
- Deadline: unknown
- Topics: legged robots / humanoid robots / reinforcement learning / locomotion / sim-to-real / field deployment
- Status: active
- Notes: 搜索结果和官方 Lever 页面标题显示 Locomotion Autonomy 岗位仍可见；角色与 RL 控制器开发和从仿真到真实复杂环境部署高度相关。

</details>
