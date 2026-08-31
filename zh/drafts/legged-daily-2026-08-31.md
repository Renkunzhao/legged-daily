[English](../../drafts/legged-daily-2026-08-31.md) | **中文**
# 腿足机器人日报 - 2026-08-31

## 摘要
- Contact-Guided Exploration 通过逐步衰减的探索 critic 缓解四足机器人非抓取式移动操作中的稀疏接触探索问题；该 RA-L 工作报告仿真成功率超过 90%，并完成 ALMA 实机搬椅实验。
- Stay Seated 在带被动脚轮的椅子上实现 Unitree G1 全向坐姿运动零样本 sim-to-real；actor 仅使用本体感知和速度指令，不观察椅子状态或接触信息。
- 三个新 Unitree G1 仓库分别覆盖鲁棒本体感知 PPO 行走、Isaac Sim 导航和面向安全的“被搬运模式”，但成熟度与实机证据差异明显。
- 本轮论文体现了比萨大学—苏黎世联邦理工—NVIDIA 在四足移动操作上的持续合作，也带来了大阪大学 Takato Horii 社会机器人组的新型人形运动方向。
- Inria Auctus / LAAS-CNRS 四足机器人机电全身协同设计博士职位今天 2026-08-31 正式截止。

<details>
<summary><strong>新论文</strong></summary>

### Contact-Guided Exploration for Non-Prehensile Locomanipulation with Multi-Critic RL
- 链接：https://arxiv.org/abs/2608.28140
- 来源：RA-L / arXiv
- 日期：2026-08-28
- 作者：Simone Tolomei、Mayank Mittal、Franco Angelini、Manolo Garabini、Paolo Salaris、Marco Hutter
- 主题：四足机器人、移动操作、非抓取操作、强化学习、多 critic 学习、sim-to-real
- 摘要：提出专门寻找接触的探索 critic，并在训练中逐步降低其权重，使四足移动操作机器人先发现有效接触、再优化任务性能；评测覆盖推箱、搬椅和开洗碗机，并在 ALMA 实机上完成搬椅实验。
- 备注：已被 IEEE Robotics and Automation Letters 接收。官方项目页报告两个仿真基准的成功率均超过 90%，并展示策略零样本迁移到未见过的 IKEA 家具；实机证据见项目页：https://tolomeis.github.io/contact-guided-exp/

### Stay Seated: Learning Omnidirectional Humanoid Locomotion on a Passive Mobile Chair with Casters
- 链接：https://arxiv.org/abs/2608.28090
- 来源：arXiv
- 日期：2026-08-28
- 作者：Kango Yanagida、Kazuki Miyazawa、Takato Horii
- 主题：人形机器人、坐姿运动、强化学习、sim-to-real、Unitree G1、能效
- 摘要：将速度跟踪强化学习扩展到人形机器人与椅子之间非固定接触及间歇式脚—地推进；actor 只观察本体感知和指令，即可在被动脚轮椅上产生全向坐姿运动，作者报告已零样本迁移到 Unitree G1 实机。
- 备注：论文用四个随机种子分析了对称正则、足部滑移正则和指令课程。其价值在于探索面向未来坐姿移动操作的运动能力，而非传统站立行走。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Humanoid_LocomotioN
- 链接：https://github.com/shubhamt2897/Humanoid_LocomotioN
- 类别：强化学习
- 机器人类型：人形机器人
- 仿真器：MuJoCo
- 部署：仿真
- 摘要：Unitree G1 的 PPO 训练栈，采用非对称 actor-critic、本体感知部署观测、载荷/摩擦/外力随机化、接触与稳定性奖励，并提供检查点回放和 ONNX 导出。
- 备注：仓库包含较完整的 Python 实现和 G1 资产，但当前后端以 Python 循环运行多个 CPU MuJoCo 环境，程序化地形默认关闭，也没有提供实机部署结果。截至 2026-08-31 未检测到许可证。

### g1_isaac_nav
- 链接：https://github.com/hyeonjin1998/g1_isaac_nav
- 类别：工具包
- 机器人类型：人形机器人
- 仿真器：Isaac
- 部署：仿真
- 摘要：将 Isaac Sim 中的 29 自由度 Unitree G1 与 ROS 2 Humble、RTAB-Map 定位、Nav2 导航、仿真激光雷达/相机、ONNX 行走策略、启动文件和可复现安装脚本集成起来。
- 备注：维护者报告已在仿真中跑通建图、导航并达到 0.118 m 定位误差，后续目标是 sim-to-real；目前未宣称已部署实机。文档较完整，但要求 Isaac Sim 5.1，并需另行下载 Unitree 模型资产。截至 2026-08-31 未检测到许可证。

### Cargo-Mode
- 链接：https://github.com/sissississi-013/Cargo-Mode
- 类别：控制
- 机器人类型：人形机器人
- 仿真器：MuJoCo
- 部署：仿真
- 摘要：一个 hackathon 原型，用于识别 Unitree G1 正在被抬起、折叠到紧凑姿态、被搬运时施加选择性阻抗，并通过受保护的有限状态机在落地后安全交还运动控制。
- 备注：仓库以 MIT 许可证发布，包含检测器、仿真、仪表盘、机载控制和安全层代码。团队状态文件说明各工作流已在仿真中验证，但实机访问受阻，因此其硬件运行手册和部署路径仍应视为未验证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### E. Piaggio 研究中心 / ETH Robotic Systems Lab 合作
- 机构：比萨大学 / 苏黎世联邦理工 / NVIDIA
- 主页：https://tolomeis.github.io/contact-guided-exp/
- arXiv：https://arxiv.org/abs/2608.28140
- 实验室 / 院系：E. Piaggio 研究中心、信息工程系 / Robotic Systems Lab
- 关键主题：四足机器人、运动、强化学习、操作
- 备注：新 RA-L 论文将比萨大学的 Simone Tolomei、Franco Angelini、Manolo Garabini、Paolo Salaris 与 ETH Zürich 的 Mayank Mittal、Marco Hutter 连接起来，且包含 NVIDIA 关联。该合作正在 ALMA 实机上推进接触丰富的非抓取式移动操作。

### Takato Horii / Social Robotics Group
- 机构：大阪大学
- 主页：https://soro.sys.es.osaka-u.ac.jp/en/members/
- arXiv：https://arxiv.org/abs/2608.28090
- 实验室 / 院系：社会机器人组，基础工学研究科系统创新系
- 关键主题：人形机器人、运动、机器人学习、认知发展机器人
- 备注：大阪大学官方将 Horii 列为副教授。Stay Seated 为一个以社会机器人和认知发展机器人见长的团队增加了 Unitree G1 实机坐姿运动方向，值得作为新的人形机器人学习信源继续观察。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- 类型：博士
- 地点：法国 Talence / Bordeaux，计划前往 Toulouse 交流
- 来源：官方页面 — https://jobs.inria.fr/public/classic/en/offres/2026-10319
- 截止时间：2026-08-31
- 主题：四足机器人、运动、强化学习、机器人系统、操作
- 状态：开放
- 备注：今天是申请最后一天。项目研究面向移动操作的局部柔顺四足机器人机电全身协同设计，结合仿真驱动机构设计、基于强化学习的协同优化、实验标定和整机原型。计划 2026-10-01 入职；标注薪资为税前每月 2,300 欧元。

</details>
