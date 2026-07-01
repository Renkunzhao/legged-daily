[English](../../drafts/legged-daily-2026-07-01.md) | **中文**
# Legged Daily - 2026-07-01

## 摘要
- 本次没有核实到比 2026-06-29 批次更新的 arXiv 2607 腿足机器人高信号论文；今天最值得补入草稿的是仓库里尚未出现过的 ICRA 2026 候选论文：用 MuJoCo iLQR 做四足和人形机器人的全身 MPC。
- MuJoCo-iLQR 工作的价值在于提供一个可复现实机 model-based baseline：覆盖动态四足运动、四足机器人双腿行走，以及全尺寸人形双足运动。
- 仓库信号新增一个 EPFL BioRob 相关学生项目：CPG 先验 + PPO 四足运动；同时记录 Google DeepMind MuJoCo MPC 作为预测控制工作流相关的软件基座。
- 招聘信号新增 ASU 官方 Fall 2026 PhD opening：面向四足和人形平台的 robot learning/control、locomotion 与 mobile manipulation。
- EPFL BioRob 与 ETH RSL 官方 openings 仍为 active；今天不提出过期招聘删除项。

<details>
<summary><strong>新论文</strong></summary>

### Whole-Body Model-Predictive Control of Legged Robots with MuJoCo
- Link: https://arxiv.org/abs/2503.04613
- Source: arXiv
- Date: 2026-03-06（v3）；arXiv 页面注明 ICRA 2026
- Authors: John Z. Zhang, Taylor A. Howell, Zeji Yi, Chaoyi Pan, Guanya Shi, Guannan Qu, Tom Erez, Yuval Tassa, Zachary Manchester
- Topics: quadruped, humanoid, whole-body MPC, iLQR, MuJoCo, sim-to-real, model-based control
- Summary: 使用 MuJoCo dynamics 和有限差分导数构建简单的实时全身 MPC / iLQR baseline，并在动态四足运动、四足机器人双腿行走、全尺寸人形双足运动等硬件实验上展示效果。
- Notes: 项目页：https://johnzhang3.github.io/mujoco_ilqr/。这是值得进入 master paper list 的强 baseline，因为它给近期偏 RL 的运动系统提供了 model-based 对照。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### AlexandrosDellios/Legged-Robot
- Link: https://github.com/AlexandrosDellios/Legged-Robot
- Category: RL / CPG / quadruped locomotion / student project
- Robot Type: quadruped
- Simulator: PyBullet
- Deploy: sim
- Summary: EPFL BioRob M.Sc. 项目，将 Hopf oscillator CPG gait prior 与 PPO policy 结合，用于四足运动；覆盖 trot/walk/pace/bound、坡面穿越、课程训练和 action-space 对比。
- Notes: 适合作为 hybrid CPG + DRL 设计取舍的轻量参考；README 报告可通过 29% 坡度，并提到 domain randomization 等 sim-to-real 考虑，但本次未核实到硬件部署。

### google-deepmind/mujoco_mpc
- Link: https://github.com/google-deepmind/mujoco_mpc
- Category: MPC / predictive control / MuJoCo toolkit
- Robot Type: general robotics；文档/媒体中包含 quadruped 和 humanoid 示例
- Simulator: MuJoCo
- Deploy: sim / research prototype
- Summary: Google DeepMind 的 MuJoCo MPC 框架，用于实时 predictive control，支持 iLQG、gradient descent、predictive sampling 等规划器，并提供 GUI 与实验性 Python API。
- Notes: 这不是 2026 whole-body legged MPC 论文的专用开源代码，但它是 MuJoCo-based predictive-control 工作流的重要相关软件基座。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### CMU / Google DeepMind MuJoCo-iLQR collaboration
- Institution: Carnegie Mellon University; Google DeepMind
- Homepage: https://johnzhang3.github.io/mujoco_ilqr/
- arXiv: https://arxiv.org/abs/2503.04613
- Key Topics: whole-body MPC, humanoid locomotion, quadruped locomotion, MuJoCo, iLQR, sim-to-real
- Notes: 作者网络连接 Zachary Manchester / CMU 与 Google DeepMind MuJoCo 研究人员；这是 model-based whole-body control 方向的重要来源线，可与近期 RL / VLA humanoid tracking 趋势互补追踪。

### EPFL BioRob / Auke Ijspeert group student-project signal
- Institution: EPFL BioRobotics Laboratory
- Homepage: https://www.epfl.ch/labs/biorob/
- GitHub: https://github.com/AlexandrosDellios/Legged-Robot
- Key Topics: bio-inspired locomotion, CPG, reinforcement learning, quadruped control, neuromechanics-inspired robotics
- Notes: Legged-Robot 仓库是 BioRob 生态下的 M.Sc. Robotics 项目；可作为轻量 source signal，与 BioRob 官方 humanoid neuromechanics opening 一起持续关注。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Arizona State University — Robotic Actuators and Dynamics Lab / Prof. Jiefeng Sun
- Type: PhD
- Location: Tempe, Arizona, USA
- Source: official lab website
- Deadline: Fall 2026 admission cycle / 页面未注明具体截止时间
- Topics: robot learning, control, locomotion, mobile manipulation, quadruped robots, humanoid robots, MuJoCo, Isaac Lab
- Status: active
- Notes: 官方页面发布 fully funded Fall 2026 PhD opening，方向是面向 customized quadruped / humanoid platforms 的 robot learning and control、locomotion 与 mobile manipulation。来源：https://sunrobotics.lab.asu.edu/blog/2025/opening/

### EPFL BioRobotics Laboratory
- Type: PhD / Postdoc
- Location: Lausanne, Switzerland
- Source: official lab page
- Deadline: continuously until filled；理想开始时间 September 2026
- Topics: humanoid, human locomotion, neuromechanics, bio-inspired control, reinforcement learning
- Status: active
- Notes: 官方 openings 页面继续列出 Fall 2026 Postdoc 与 PhD position，主题是使用 humanoid robots 研究并利用 human locomotion neuromechanics。来源：https://www.epfl.ch/labs/biorob/openings/

### ETH Zurich Robotic Systems Lab
- Type: PhD / Postdoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- Location: Zurich, Switzerland
- Source: official lab page
- Deadline: rolling / unknown
- Topics: legged robots, mobile manipulation, MPC, reinforcement learning, perception, planning, actuation, teleoperation
- Status: active
- Notes: 官方 RSL 页面继续列出多个 rolling openings，覆盖 legged robots、mobile manipulators 和 field robotics 相关 research / engineering roles。来源：https://rsl.ethz.ch/the-lab/open-positions.html

</details>
