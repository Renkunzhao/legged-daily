[English](../../drafts/legged-daily-2026-07-09.md) | **中文**
# Legged Daily - 2026-07-09

## 摘要
- 今天最强的新论文是 ABot-C0：一篇新的四足机器人行为基础技术报告，结合大规模运动数据、Flow Matching 策略学习、感知式全地形运动和真实部署声明。
- X-Morph 仍然是高信号方向：它把人类运动转化为四足、六足和带机械臂四足机器人的跨形态行为先验。
- KYON v2 值得跟踪：这是一个具备双臂上身能力的轮腿四足硬件平台，面向移动操作任务。
- 今天的仓库信号质量不错：Quadrrl 提供 Isaac Lab 四足 / 轮腿四足 RL benchmark；mujoco_mpc_deploy 和 MPX 则是腿足硬件或 MJX 模型相关的 MPC / 控制基础设施。
- Chalmers 的 RAIL Lab 是新的实验室 / 教授跟踪源，覆盖欠驱动、腿足、人形、最优控制和 RL；官网明确表示欢迎博士、博士后和硕士论文学生。

<details>
<summary><strong>新论文</strong></summary>

### Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report
- 链接: https://arxiv.org/abs/2607.07370
- 来源: arXiv
- 日期: 2026-07-08
- 作者: Xufeng Zhao, Fuzhi Yang, Jianhui Chen, Li Gao, Zhang Meng, Jie Gao, Yao Zheng, Wenyu Liu, Menglin Yang, Minqi Gu, Yaru Zhao, Honglin Han, Shihui Su, Zixiao Tang, Liu Liu, Mu Xu, Yang Cai, Wenbin Tang
- 主题: 四足机器人、运动控制、行为基础、Flow Matching、运动跟踪、运动控制、场景交互、LiDAR 感知、真实部署
- 摘要: ABot-C0 提出一个通用四足运动控制系统，包含 16,074 段物理可行动作片段、Flow Matching 通用策略、带时序 LiDAR 记忆的 privileged-to-perceptive 全地形运动栈，以及用于城市导航和陪伴式交互的多策略部署机制。
- 备注: arXiv 页面说明项目页稍后发布，因此代码 / 数据集可用性今天尚未验证。

### Human Motion Priors for Scalable Robot Learning Across Morphologies
- 链接: https://arxiv.org/abs/2606.30290
- 来源: arXiv
- 日期: 2026-06-29
- 作者: Guillaume Sartoretti 等
- 主题: 跨形态重定向、机器人学习、四足、六足、四足机械臂、privileged RL、行为先验、遥操作、文本条件运动
- 摘要: X-Morph 将人类运动转化为非人形腿足机器人的可部署运动和移动操作策略：先把人类动作重定向为机器人参考轨迹，再用 privileged RL 跟踪，并蒸馏为因果学生策略。
- 备注: 该工作直接面向非人形腿足机器人运动数据稀缺问题，也与 ABot-C0 的四足运动语料方向互补。

### Semi-Modular Wheel-Legged Quadruped With Agile Bimanual Capability
- 链接: https://arxiv.org/abs/2606.30243
- 来源: arXiv
- 日期: 2026-06-29；v2 2026-07-07
- 作者: Luca Rossini, Arturo Laurenzi, Francesco Ruscelli, Yifang Zhang, Jingcheng Jiang, Giovanbattista Gravina, Lorenzo Baccelliere, Corrado Burchielli, Stefano Cordasco, Luca Muratore, Nikos Tsagarakis
- 主题: 轮腿四足、移动操作、双臂操作、机器人设计、全身控制、强化学习
- 摘要: KYON 是一个半模块化轮腿四足平台，具有可重构下肢和双臂上身；通过基座内置驱动、传动机构、全身控制和 RL 策略，展示动态运动与操作实验。
- 备注: v2 于 2026-07-07 更新；它更像一个高信号硬件形态更新，而不是纯学习方法。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### lbnmahs/quadrrl
- 链接: https://github.com/lbnmahs/quadrrl
- 类别: RL / benchmark / simulator / toolkit
- 机器人类型: 四足 / 轮腿四足
- 仿真器: Isaac Lab / Isaac Sim
- 部署: 仿真
- 摘要: Quadrrl 是一个面向腿足和轮腿四足运动的训练与 benchmarking 库，提供平地和复杂地形 RL 任务，覆盖 ANYmal C/D、Spot、Unitree Go2/B2、Go2W/B2W、Deeprobotics 和 Zsibot 等模型。
- 备注: README 列出 RSL-RL、RL Games、SKRL 和 HARL 支持；今天未验证硬件部署声明，因此应视为仿真 / benchmark 基础设施。

### johnzhang3/mujoco_mpc_deploy
- 链接: https://github.com/johnzhang3/mujoco_mpc_deploy
- 类别: MPC / control / hardware interface
- 机器人类型: 四足
- 仿真器: MuJoCo / MuJoCo MPC
- 部署: 硬件导向 / 进行中
- 摘要: 这是一个用于在 Unitree 机器人上部署 MuJoCo MPC 的硬件接口仓库，对应 Whole-Body Model-Predictive Control of Legged Robots with MuJoCo 项目，并依赖 MuJoCo MPC 与 MuJoCo Menagerie 资产。
- 备注: README 明确说该仓库仍是 work in progress，并指向 Go1 / Go2 的 MuJoCo MPC 分支。

### iit-DLSLab/mpx
- 链接: https://github.com/iit-DLSLab/mpx
- 类别: MPC / trajectory optimization / JAX / MJX
- 机器人类型: 人形 / 四足 / 通用腿足
- 仿真器: MJX / MuJoCo
- 部署: 仿真 / 研究基础设施
- 摘要: MPX 用 JAX 实现腿足机器人 MPC 与轨迹优化，包含 GPU 并行扫描、可微求解器、可接入批量学习 pipeline 的接口，以及 Talos、H1、Aliengo 和 Go2 的 MJX 示例。
- 备注: 更适合作为求解器基础设施，而不是某个具体机器人的完整发布；README 展示了四足 trot、人形跳跃和四足 barrel roll 示例。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Robot Athletic Intelligence Lab / Shivesh Kumar
- 机构: Chalmers University of Technology
- 主页: https://chalmers-rail.github.io/
- 实验室 / 院系: Robot Athletic Intelligence Lab; Department of Mechanical Engineering
- 关键主题: 欠驱动机器人、腿足机器人、人形机器人、多体动力学、最优控制、强化学习、生成式 AI、硬件-算法协同设计、腿足 MPC
- 备注: 官方主页称 RAIL 由 Shivesh Kumar 领导，研究面向欠驱动机器人、腿足机器和人形机器人的 physical and athletic intelligence。主页还列出 SSF Future Research Leader 资助、WASP 博士项目资助、7 台机器人，并在开放职位区明确欢迎博士、博士后和硕士论文学生。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Robot Athletic Intelligence Lab / Chalmers University of Technology
- 类型: PhD / Postdoc / Master's thesis
- 地点: Gothenburg, Sweden
- 来源: 官方实验室主页
- 截止时间: unknown
- 主题: 欠驱动机器人、腿足机器、人形机器人、最优控制、强化学习、开放可复现科学
- 状态: watching
- 备注: 实验室主页表示欢迎博士、博士后和硕士论文学生；今天没有验证到具体申请截止时间或独立招聘页面，因此作为 watchlist 信号，而不是已确认资助职位。

### Proposed Removal / Stale Item
- 当前状态: 今天不建议删除
- 原因: 今天检查发现 1 个新的 watchlist 信号，但没有验证出已过期的既有机会。
- 已检查来源: 今日网页检查与现有 jobs.md 上下文

</details>
