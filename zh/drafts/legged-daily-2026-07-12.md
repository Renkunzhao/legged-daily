[English](../../drafts/legged-daily-2026-07-12.md) | **中文**
# 腿足机器人日报 - 2026-07-12

## 摘要
- 今天最值得跟踪的论文是 HEFT：一个面向全尺寸人形机器人的遥操作系统，明确处理嘈杂 VR 参考与最高 24 kg 的真实双手负载。
- ARDY 与 GIRAF 两篇相邻方向论文也值得关注：它们都在做带长时程、全身运动、接触/移动结构的运动生成，可能进入人形机器人策略或数据管线。
- 两个仓库具备直接实用价值：HEFT 官方 motion-tracking 代码，以及面向 Unitree 机器人的 MuJoCo MPC 硬件部署封装。
- 1X 官方招聘页当前列出 San Carlos 的 Simulation Engineer；先作为人形机器人仿真基础设施岗位信号跟踪，不把它过度解读为腿足控制专项岗位。

<details>
<summary><strong>新论文</strong></summary>

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv / project page
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid / whole-body teleoperation / motion tracking / payload-aware locomotion / reinforcement learning
- Summary: 提出 HEFT，全尺寸人形机器人遥操作框架：部署策略输入嘈杂 VR 参考，训练时用重建后的物理合理动作做 privileged guidance，并用 Windowed Payload Curriculum 学习不同动作片段对应的重载鲁棒性；在 175 cm、65 kg 的 L7 人形机器人上验证转身、前进/后退、下蹲与最高 24 kg 双手负载。
- Notes: 项目页：https://heft.axell.top/。arXiv HTML 标注作者机构为清华大学、RobotEra、上海期智研究院。

### ARDY: Autoregressive Diffusion with Hybrid Representation for Interactive Human Motion Generation
- Link: https://arxiv.org/abs/2607.08741
- Source: arXiv / SIGGRAPH 2026 / project page
- Date: 2026-07-09
- Authors: Kaifeng Zhao, Mathis Petrovich, Haotian Zhang, Tingwu Wang, Siyu Tang, Davis Rempe
- Topics: humanoid / human motion generation / interactive locomotion control / diffusion / text-conditioned control
- Summary: 提出流式自回归扩散框架，用于实时、可控的 3D 人体运动生成，支持在线文本提示、运动学约束、路径跟随，以及通过鼠标键盘进行交互式 locomotion 控制。
- Notes: 项目页与计划发布代码/模型：https://research.nvidia.com/labs/sil/projects/ardy/。它不是机器人控制论文，但对人形机器人运动数据生成与交互式策略条件输入有参考价值。

### GIRAF: Towards Generalizable Human Interactions with Articulated Objects
- Link: https://arxiv.org/abs/2607.07880
- Source: arXiv / CVPR 2026 HuMoGen Workshop
- Date: 2026-07-08
- Authors: Xiaohan Zhang, Sebastian Starke, Alexander Winkler, Federica Bogo, Samir Aroudj, Yuting Ye
- Topics: embodied AI / locomotion-to-manipulation transitions / full-body motion generation / articulated objects / contact
- Summary: 提出面向 articulated objects 的文本条件扩散模型，重点生成从接近移动到手-物接触、物体关节运动的全身交互，并强调对未见物体位置和形状的泛化。
- Notes: 不是腿足机器人部署结果，但适合作为人形 loco-manipulation、接触丰富全身行为合成方向的数据/模型信号。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Axellwppr/motion_tracking
- Link: https://github.com/Axellwppr/motion_tracking
- Category: RL / retargeting / dataset / deployment
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: both
- Summary: HEFT 官方实现，包含人形机器人全身 motion tracking 的训练、评估、导出和部署相关资产；分支覆盖 HEFT 训练、G1 compliance 工作，以及 sim2real runtime/checkpoints。
- Notes: README 提到 PMG、WPC、公开训练数据或样例、ONNX/PT 导出和 sim2real 分支资产；完整 HEFT 数据集和部分 WPC payload labels 似乎仍计划后续发布。

### johnzhang3/mujoco_mpc_deploy
- Link: https://github.com/johnzhang3/mujoco_mpc_deploy
- Category: MPC / control / deployment
- Robot Type: quadruped / humanoid-adjacent
- Simulator: MuJoCo / MuJoCo MPC
- Deploy: hardware
- Summary: 面向 Unitree 机器人部署 MuJoCo MPC 的硬件接口仓库，对应 ICRA 2026 论文 “Whole-Body Model-Predictive Control of Legged Robots with MuJoCo”，并与官方 MuJoCo MPC / Menagerie 栈配合使用。
- Notes: README 明确说仓库仍在 work in progress，并指向 Go1/Go2 分支的 MuJoCo MPC；作为从模型式 whole-body MPC 到 Unitree 硬件的实践桥梁值得跟踪。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Jianyu Chen group / Tsinghua University + RobotEra + Shanghai Qizhi Institute
- Institution: Tsinghua University / RobotEra / Shanghai Qizhi Institute
- Homepage: https://heft.axell.top/
- GitHub: https://github.com/Axellwppr/motion_tracking
- Lab / Department: arXiv affiliation signal from HEFT
- Key Topics: humanoid / whole-body teleoperation / payload-aware locomotion / motion tracking / sim-to-real
- Notes: HEFT 是强信号：这个清华-RobotEra-期智合作线正在推进全尺寸人形机器人的真实重载遥操作，而不只是 G1 这类紧凑平台验证。
- Students and Representative Works:
  - Chenxin Liu — HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum

### NVIDIA Spatial Intelligence Lab / human-motion generation line
- Institution: NVIDIA Research
- Homepage: https://research.nvidia.com/labs/sil/projects/ardy/
- Lab / Department: Spatial Intelligence Lab
- Key Topics: humanoid / human motion generation / diffusion / interactive control / motion priors
- Notes: ARDY 计划发布代码/模型，值得持续观察：它可能成为人形机器人 motion prior、交互式约束和上游动作数据生成工具。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 1X
- Type: Simulation Engineer
- Location: San Carlos, California
- Source: official careers page
- Deadline: unknown
- Topics: humanoid / simulation / robotics systems / validation
- Status: active / watching
- Notes: 1X 官方 careers 页面在 Hardware Engineering 下列出 San Carlos 的 “Simulation Engineer”。抓取到的岗位详情页只暴露标题，因此腿足控制相关性尚未验证；但作为人形机器人行业仿真基础设施信号值得跟踪。

</details>
