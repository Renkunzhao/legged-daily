[English](../../drafts/legged-daily-2026-06-14.md) | **中文**
# 腿足机器人日报 - 2026-06-14

## 摘要
- 周末运行暂未发现更新的 6 月 14 日 arXiv 批次强信号；近期最值得跟踪的仍是 6 月 9-11 日的 humanoid control、navigation、loco-manipulation 方向论文。
- 精选 3 篇高信号论文：生成视频驱动的人形机器人交互、统一的人形导航与运动控制、omni-modal 全身动作生成。
- 精选 3 个实用仓库/资源：WholeBodyVLA 作为人形 loco-manipulation VLA 资源中枢，`legged_lab` 用于 Isaac Lab 人形 AMP/DeepMimic 流程，`legged-loco` 用于 Go2/H1 低层运动策略训练。
- 实验室信号：Tsinghua MARS Lab / Hang Zhao 网络因 OMG 再次出现；USC Dynamic Robotics and Control Lab 官方页面明确覆盖 legged、humanoid、wheel-legged control/RL，值得加入来源网络观察。
- 招聘信号：Field AI 除已追踪的 locomotion engineer 外，还有明确的 Summer 2026 locomotion/planning research internship；EPFL BioRob 与 ETH RSL 官方岗位仍处于 active。

<details>
<summary><strong>新论文</strong></summary>

### GenHOI: Contact-Aware Humanoid-Object Interaction by Imitating Generated Videos without Task-Specific Training
- Link: https://arxiv.org/abs/2606.12995
- Source: arXiv
- Date: 2026-06-11
- Authors: Zhihai Bi, Qiang Zhang, Guoyang Zhao, Jiahang Cao, Xueyin Luo, Yushan Zhang, Jinglan Xu, Ruoyu Geng, Yulin Li, Andrew F. Luo, Jun Ma
- Topics: humanoid-object interaction / loco-manipulation / generated video / contact-aware planning / whole-body control
- Summary: 提出一个 zero-shot humanoid-object interaction 流程，把生成的任务视频转成接触区域约束和优化后的参考轨迹，再由闭环 tracking controller 执行。
- Notes: 对人形 loco-manipulation 很相关，因为它显式处理平衡、手-物接触，以及 grasping、carrying、lifting、enveloping 等真实物体交互任务。

### GuideWalk: Learning Unified Autonomous Navigation and Locomotion for Humanoid Robots across Versatile Terrains
- Link: https://arxiv.org/abs/2606.10449
- Source: arXiv
- Date: 2026-06-09
- Authors: Haoxuan Han, Chen Chen, Linao Gong, Xin Yang, Hao Hu, Junhong Guo, Zhicheng He, Yao Su
- Topics: humanoid navigation / locomotion / terrain adaptation / teacher distillation / reinforcement learning
- Summary: 提出端到端人形导航与运动框架，结合 traversability-aware velocity guidance、terrain-adaptive locomotion teacher、composite teacher distillation 和 RL refinement。
- Notes: 价值在于把避障和动态可行的人形 locomotion 当成耦合问题处理，而不是简单的高层 planner + 低层 gait controller。

### OMG: Omni-Modal Motion Generation for Generalist Humanoid Control
- Link: https://arxiv.org/abs/2606.10340
- Source: arXiv
- Date: 2026-06-09
- Authors: Siqiao Huang, Kun-Ying Lee, Dongming Qiao, Guanqi He, Zhenyu Wang, Yitang Li, Shaoting Zhu, Hang Zhao
- Topics: humanoid whole-body control / motion generation / diffusion model / multimodal conditioning / foundation models
- Summary: 提出一个 omni-modal 人形全身控制器，使用精心整理的动作数据和 diffusion-based generator，支持语言、音频、人类参考动作等多模态条件输入。
- Notes: 作者列出的项目页为 https://tsinghua-mars-lab.github.io/OMG/ 。这是 Tsinghua MARS Lab / Hang Zhao 人形 generalist-control 方向的强来源网络信号。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### OpenDriveLab/WholebodyVLA
- Link: https://github.com/OpenDriveLab/WholebodyVLA
- Category: toolkit / VLA / resource list / loco-manipulation
- Robot Type: humanoid
- Simulator: not specified
- Deploy: data / reference resources
- Summary: ICLR 2026 WholeBodyVLA 项目仓库与 humanoid VLA / loco-manipulation 资源列表，核心是面向全身人形控制的 unified latent actions。
- Notes: README 明确表示当前没有开源代码的具体时间表，因此应按项目/资源中枢追踪，而不是可直接复现实验的代码发布。GitHub API 检查：476 stars，2026-06-11 更新。

### zitongbai/legged_lab
- Link: https://github.com/zitongbai/legged_lab
- Category: RL / imitation / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab
- Deploy: sim / possible hardware workflow dependency
- Summary: 面向腿足机器人 RL 的 Isaac Lab extension，支持 Unitree G1 的 DeepMimic 与 Adversarial Motion Priors，并使用 forked RSL-RL AMP 工作流。
- Notes: README 强调 GMR 人体动作重定向、Git LFS assets、2026-02-09 新增 Docker workflow、Isaac Lab 2.3.1 支持，以及 AMP/symmetry data augmentation 更新。GitHub API 检查：353 stars，2026-06-13 更新。

### yang-zj1026/legged-loco
- Link: https://github.com/yang-zj1026/legged-loco
- Category: RL / locomotion / toolkit
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: 用于 Unitree Go2 和 H1 的 Isaac Lab 低层 locomotion policy training 代码，包含 train/play 脚本与可扩展环境配置。
- Notes: README 表示代码测试于 Isaac Lab 1.1.0，并依赖修改版 Isaac Lab fork；在新版 Isaac Lab 上复用前需要先检查兼容性。GitHub API 检查：436 stars，2026-06-14 更新。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Hang Zhao — Tsinghua University / MARS Lab
- Institution: Tsinghua University
- Homepage: https://hangzhaomit.github.io/
- Lab / Department: https://group.iiis.tsinghua.edu.cn/~marslab/#/
- Key Topics: humanoid whole-body control / multimodal motion generation / robot learning / embodied AI
- Notes: OMG（arXiv:2606.10340）将 Hang Zhao 列为合作者，并使用 Tsinghua MARS Lab 项目页，进一步确认该来源对 humanoid generalist-control 值得持续观察。
- Students and Representative Works:
  - [Ziwen Zhuang](https://ziwenzhuang.github.io/) — [Humanoid Parkour Learning](https://humanoid4parkour.github.io/)

### Quan Nguyen — USC Dynamic Robotics and Control Laboratory
- Institution: University of Southern California
- Homepage: https://sites.usc.edu/quann/
- Lab / Department: Dynamic Robotics and Control Laboratory
- Key Topics: legged robots / humanoid robots / quadruped robots / wheel-legged robots / control / optimization / planning / reinforcement learning
- Notes: 官方 lab page 表示团队长期寻找与 control、optimization、planning、RL for legged robots 匹配的学生，且明确包含 quadrupeds、humanoids、wheel-legged robots。今天只验证到 general recruiting statement，未验证到具体 funded opening。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Field AI — Robotics Research Internship: Locomotion & Planning (Summer 2026)
- Type: Internship
- Location: Mission Viejo / Irvine area, California, USA; Field AI team context
- Source: official Lever careers page
- Deadline: unknown
- Topics: learning-based locomotion / planning / reinforcement learning / legged robots / autonomous field robotics
- Status: active
- Notes: 官方岗位描述这是面向 PhD students 的 Summer 2026 internship，重点是 learning-based locomotion and planning，用于复杂真实环境中的 autonomous legged robot capabilities。

### EPFL BioRob / Auke Ijspeert
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: rolling until filled; EPFL doctoral program deadlines typically April 15 and December 15
- Topics: humanoid robots / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- Status: active
- Notes: 官方 openings page 仍列出 Postdoc and PhD student position，方向是用 humanoid robots 研究并利用 human locomotion neuromechanics，时间点为 Fall 2026。

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling / unknown
- Topics: legged robots / mobile manipulators / MPC / reinforcement learning / perception / navigation / actuation / teleoperation / ROS / C++
- Status: active
- Notes: 官方 open-positions page 继续列出 PhD、PostDoc、research staff/software engineering 路线，方向覆盖 legged robots、mobile manipulation、field deployment、control、learning、planning、perception、system design。

</details>
