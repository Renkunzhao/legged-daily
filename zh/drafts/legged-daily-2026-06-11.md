[English](../../drafts/legged-daily-2026-06-11.md) | **中文**
# Legged Daily - 2026-06-11

## 摘要
- 今天最强的主线是人形机器人的全身控制与移动操作学习：OMG 面向多模态通用 Unitree G1 控制，OASIS 面向仿真数据驱动的真实人形移动操作。
- 一篇简短的 ICRA 2026 workshop 论文把 critic architecture 作为多目标人形 RL 的明确设计变量：在 Isaac Lab 的 Unitree G1 任务中，dual critics 相比 unified critic 有更好的 reaching 效率。
- 仓库信号偏实现：OASIS 已开放数据采集代码和资产，LeggedGym-Ex 仍是活跃更新的多仿真器腿足 RL 框架，NeuroGait 是新的 Isaac Lab 四足运动 benchmark/template，但目前还偏早期。
- 建议继续跟踪的来源包括 Tsinghua MARS Lab 的人形 motion-generation foundation model 线，以及 TeleHuman/OASIS 的仿真优先 humanoid loco-manipulation 数据采集线。
- 招聘检查发现 Field AI 官方 Lever 新列出 Boston 的 humanoid manipulation research 岗位；EPFL BioRob 和 ETH RSL 的官方 openings 仍为 active。

<details>
<summary><strong>New Papers</strong></summary>

### OMG: Omni-Modal Motion Generation for Generalist Humanoid Control
- Link: https://arxiv.org/abs/2606.10340
- Source: arXiv
- Date: 2026-06-09
- Authors: Siqiao Huang, Kun-Ying Lee, Dongming Qiao, Guanqi He, Zhenyu Wang, Yitang Li, Shaoting Zhu, Hang Zhao
- Topics: humanoid / whole-body control / motion generation / diffusion model / foundation model / Unitree G1
- Summary: 提出 OMG，一个用于通用人形控制的 generator-tracker 层级架构：diffusion motion generator 可基于语言、音频、人体参考动作和历史动作生成未来全身轨迹，再由预训练 tracker 在 Unitree G1 上执行。
- Notes: 项目页：https://tsinghua-mars-lab.github.io/OMG/ 。页面报告了 1174.66 小时、重定向并对齐到 Unitree G1 的 omni-modal humanoid motion corpus，并强调可扩展控制模态；本轮没有在项目页确认代码释放。

### OASIS: From Simulation Data Collection to Real-World Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.08548
- Source: arXiv
- Date: 2026-06-07
- Authors: Zehao Yu, Jiakun Zheng, Weiji Xie, Jiyuan Shi, Chenyun Zhang, Chenjia Bai, Xuelong Li
- Topics: humanoid / loco-manipulation / simulation data / teleoperation / domain randomization / visuomotor policy
- Summary: 提出 OASIS，一个仿真数据驱动的人形移动操作框架：从真实图像重建物体资产，在仿真中遥操作采集轨迹，再做 domain randomization，并训练可迁移到真实人形机器人的层级视觉运动策略。
- Notes: 项目页：https://oasis-humanoid.github.io/ 。官方仓库：https://github.com/TeleHuman/OASIS 。可作为近期真实遥操作数据、合成数据和人形操作流水线的仿真数据补充方向跟踪。

### Critic Architecture Matters: Dual vs. Unified Critics for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.11891
- Source: arXiv / ICRA 2026 Workshop on Reinforcement Learning for Imitation Learning
- Date: 2026-06-10
- Authors: Mehmet Turan Yardımcı
- Topics: humanoid / loco-manipulation / reinforcement learning / critic architecture / Isaac Lab / Unitree G1
- Summary: 在 Isaac Lab 的 Unitree G1 移动操作 RL 中比较 unified critic 与 dual critic；结果显示 dual critics 的目标到达速度快 3.5 倍，validated reaching throughput 约翻倍，并且比额外 anti-gaming reward 机制更有效。
- Notes: 虽然是短 workshop paper，但它把 critic architecture 这个常被忽略的训练设计变量单独拎出来，对多目标人形 RL 和 imitation-learned policies 的 RL fine-tuning 有实用参考价值。

</details>

<details>
<summary><strong>New Repos</strong></summary>

### OASIS
- Link: https://github.com/TeleHuman/OASIS
- Category: dataset / toolkit / simulator / teleoperation
- Robot Type: humanoid
- Simulator: Isaac Lab / Isaac Sim
- Deploy: both
- Summary: OASIS 官方仓库，用于基于仿真的人形移动操作数据采集，包含 Isaac Lab 配置、场景/物体资产、PICO 遥操作流程、轨迹 replay 和 domain-randomized rendering。
- Notes: 仓库创建于 2026-06-07；README 称 2026-06 release 了 OASIS 的 data collection code、assets 和论文；依赖 GMR、PICO SDK、unitree_sim_isaaclab、TWIST2、Teleopit。

### LeggedGym-Ex
- Link: https://github.com/lupinjia/LeggedGym-Ex
- Category: RL / simulator / toolkit
- Robot Type: humanoid / quadruped / general
- Simulator: IsaacGym / Genesis / IsaacSim
- Deploy: both
- Summary: 基于 legged_gym 的腿足机器人训练框架，支持 IsaacGym、Genesis、IsaacSim，并包含 Unitree Go2、Unitree G1、Booster K1、TRON1 等示例，以及多种已发表 RL 方法实现。
- Notes: 2026 年 6 月仍活跃更新；README 列出 warp-based depth rendering/height query、DeepMimic、AMP、teacher-student、system ID 和多个 sim-to-real demo。不是全新仓库，但属于高信号活跃工具栈。

### NeuroGait
- Link: https://github.com/Tanishq-C-Saha/NeuroGait
- Category: RL / simulator / benchmark
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: 新的 Isaac Lab extension，GitHub 描述为用于 Unitree Go2 四足 locomotion 的 benchmarking 和 terrain-adaptive reinforcement learning。
- Notes: 创建于 2026-06-06。GitHub description 与方向相关，但 README 目前仍主要是 Isaac Lab extension template，因此更适合作为早期 watch item，而不是成熟 benchmark。

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Tsinghua MARS Lab / OMG project
- Institution: Tsinghua University
- Homepage: https://tsinghua-mars-lab.github.io/OMG/
- Lab / Department: MARS Lab, Tsinghua University
- Key Topics: humanoid / whole-body control / motion generation / multi-modal conditioning / Unitree G1 / robot foundation models
- Notes: OMG 明确显示该组正在做人形 motion generation 的可扩展路线：项目页展示 generator-tracker hierarchy、OMG-DiT diffusion backbone，以及 1174.66 小时的 Unitree G1-aligned omni-modal motion corpus。建议继续跟踪代码/数据 release 和后续 generalist humanoid control 工作。

### TeleHuman / OASIS project line
- Homepage: https://oasis-humanoid.github.io/
- GitHub: https://github.com/TeleHuman/OASIS
- Key Topics: humanoid / loco-manipulation / simulation data collection / teleoperation / domain randomization / real-world transfer
- Notes: OASIS 在 2026 年 6 月公开仓库，方向是仿真数据驱动的人形移动操作。这个来源适合与 GRAIL、SIMPLE、EgoHumanoid 等 humanoid manipulation-data pipelines 一起跟踪；本轮未能从项目页确认机构归属，因此不强填 institution。

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### Field AI
- Type: Research Engineer / Internship
- Location: Boston, MA, USA
- Source: official Lever careers page
- Deadline: unknown
- Topics: humanoid manipulation / loco-manipulation / embodied intelligence / robot learning / real hardware
- Status: active
- Notes: 官方 postings 包括 “Senior Research Engineer – Humanoid Manipulation” 和 “Robotics Research Internship, Humanoid Manipulation (Summer 2026) | PhD Internship”。岗位强调 humanoid manipulation、loco-manipulation、真实机器人系统、偏 foundation-model 的 robot learning 和部署。来源：https://jobs.lever.co/field-ai/1ae59c17-eabd-4e36-a2c2-e9ac96ba0f85 和 https://jobs.lever.co/field-ai/2a2c8f00-3a28-481b-882c-33cb0ec4a3a0

### EPFL Biorobotics Laboratory / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official website
- Deadline: rolling until filled; Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
- Topics: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: 官方 openings 页面仍列出一个 Postdoc 和一个 PhD 位置，主题是利用人形机器人研究/利用 human locomotion neuromechanics，包含数值神经肌肉仿真、生物启发 controller 和 reinforcement learning。来源：https://www.epfl.ch/labs/biorob/openings/

### ETH Zurich Robotic Systems Lab
- Type: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer
- Location: Zurich, Switzerland
- Source: official website
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / motion planning / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: RSL 官方页面仍列出 rolling 的 PhD、postdoc、research staff/software engineer、robot design 和 embedded-systems 岗位，方向覆盖 legged robots、mobile manipulation、control、learning、planning 和部署。来源：https://rsl.ethz.ch/the-lab/open-positions.html

</details>
