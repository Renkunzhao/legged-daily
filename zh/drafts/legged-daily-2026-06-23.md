[English](../../drafts/legged-daily-2026-06-23.md) | **中文**
# 腿足机器人日报 - 2026-06-23

## 摘要
- 今天 arXiv 的人形机器人全身运动与移动操作信号很强，6 月 19-22 日有多篇值得跟踪的新提交。
- OpenHLM 是今天最强的人形 VLA 信号：它把全身移动操作拆成可复现 recipe，系统比较全身遥操作、VLA 设计和异构数据协同训练。
- CoorDex 是今天最强的灵巧移动操作信号：它发布了 Isaac Lab 代码与 checkpoints，面向 Unitree G1 + Wuji 灵巧手边走边操作。
- Go2-W 长距离导航是偏落地的部署信号：论文报告 DRL 控制器和自主导航栈在 Tsukuba Challenge 2025 完成约 2.8 km，且没有因过热停机。
- 仓库方面新增 CoorDex，并继续保留 `g1_locomotion` 作为 G1 经典控制参考；后者的重要 caveat 是尚未做实体机器人测试。
- 机会方面：Chalmers RAIL 值得加入腿足人形机器人实验室 watch；官方实验室页明确欢迎 PhD、Postdoc 和硕士论文候选人，但第三方的 Chalmers legged humanoid postdoc 信号还需要在官方 vacancies 页二次确认后再作为已确认岗位加入。

<details>
<summary><strong>新论文</strong></summary>

### OpenHLM: An Empirical Recipe for Whole-Body Humanoid Loco-Manipulation
- 链接: https://arxiv.org/abs/2606.22174
- 来源: arXiv
- 日期: 2026-06-20
- 作者: Yingdong Hu, Haodong Zhu, Boyuan Zheng, Yihang Hu, Tong Zhang, Zunhao Chen, Junming Zhao, Ruiqian Nai, Yang Gao
- 主题: 人形机器人 / 移动操作 / VLA / 全身遥操作 / 协同训练 / 语言条件控制
- 摘要: OpenHLM 提出一个开源的全身人形移动操作 recipe，系统研究全关节遥操作、VLA 向人形全身动作空间适配，以及异构数据协同训练；项目页报告其在长时程 pick-and-place 任务上达到 87.5% task progress，且演示时间少于两个 humanoid VLA baseline 的一半。
- 备注: 很适合跟踪从“上下半身解耦控制”走向“语言-视觉-全身动作统一控制”的人形 VLA 系统。

### CoorDex: Coordinating Body and Hand Priors for Continuous Dexterous Humanoid Loco-Manipulation
- 链接: https://arxiv.org/abs/2606.23680
- 来源: arXiv
- 日期: 2026-06-22
- 作者: Sikai Li, Shuning Li, Zhenyu Wei, Yunchao Yao, Chenran Li, Mingyu Ding
- 主题: 人形机器人 / 灵巧手 / 移动操作 / 强化学习 / latent priors / Unitree G1
- 摘要: CoorDex 用 coordinated latent-residual policy 组合冻结的身体和手部先验，使带高自由度灵巧手的 Unitree G1 可以边移动边抓取、搬运、开冰箱和 pick-turn 物体，目标是摆脱常见的 stop-and-go 移动操作模式。
- 备注: 高信号点在于项目页和代码/checkpoints 都已释放，可复现 Isaac Lab rollout。

### Long-Distance Real-World Navigation of the Legged-Wheeled Robot Go2-W Using Deep Reinforcement Learning
- 链接: https://arxiv.org/abs/2606.21387
- 来源: arXiv
- 日期: 2026-06-19
- 作者: Takaaki Matsuzawa, Kiyoshi Irie, Tomoaki Yoshida, Taro Suzuki, Yoshitaka Hara, Masahiro Tomono
- 主题: 腿轮机器人 / Go2-W / DRL / 真实世界导航 / 热鲁棒性 / 自主部署
- 摘要: 论文把仅本体感知的四足策略扩展到 16-DoF Unitree Go2-W，并接入自主导航栈；报告在 Tsukuba Challenge 2025 中穿越人行道、公园和楼梯等约 2.8 km 路线，期间没有因过热停止。
- 备注: 对持续长距离腿轮自主部署很有参考价值，尤其指出轮式步态的负载分布会影响髋关节发热。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Skevinci/coordex
- 链接: https://github.com/Skevinci/coordex/tree/main
- 类别: RL / 移动操作 / 仿真器 / checkpoints
- 机器人类型: 人形 / Unitree G1 + Wuji hand
- 仿真器: Isaac Sim 5.0 / Isaac Lab 2.2.0
- 部署: 仿真 / 项目页包含硬件 demo
- 摘要: CoorDex 官方代码库，提供 G1 Wuji 在 WalkGrab、OpenFridge、WalkPickTurn 三类移动操作任务上的 rollout，包含冻结的身体/手部 priors、训练好的 coordinated-residual policy checkpoints、Isaac Lab 任务配置和 rollout 脚本。
- 备注: 适合作为 master list 候选，因为它不只是论文展示页，而是释放了可跑任务和 checkpoints。

### ioloizou/g1_locomotion
- 链接: https://github.com/ioloizou/g1_locomotion
- 类别: MPC / 全身逆动力学 / 仿真器
- 机器人类型: 人形 / Unitree G1
- 仿真器: MuJoCo
- 部署: 仿真
- 摘要: 面向 Unitree G1 的硕士论文 locomotion stack，使用 single-rigid-body dynamics MPC + whole-body inverse dynamics 的线性级联控制流程，并提供 Docker/ROS 的直线行走仿真启动说明。
- 备注: 适合与学习型 G1 locomotion stack 并列作为经典控制参考；README 明确说明尚未在实体机器人上测试。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### OpenHLM Project / Yang Gao group
- 机构: 基于作者信息，属于清华大学相关研究生态；正式加入 master list 前需再确认具体实验室归属
- 主页: https://openhlm-project.github.io/
- arXiv: https://arxiv.org/abs/2606.22174
- 关键主题: 人形机器人 / VLA / 全身遥操作 / 移动操作 / 异构协同训练
- 备注: 项目页报告语言条件全身人形任务、与 GR00T N1.6 和 Psi_0 的系统比较，并显示会提供代码、数据和 checkpoints。

### CoorDex Team / UNC Chapel Hill and UC Berkeley
- 机构: University of North Carolina at Chapel Hill; University of California, Berkeley
- 主页: https://skevinci.github.io/coordex/
- GitHub: https://github.com/Skevinci/coordex/tree/main
- arXiv: https://arxiv.org/abs/2606.23680
- 关键主题: 人形机器人 / 灵巧手 / 移动操作 / Isaac Lab / 强化学习 / latent priors
- 备注: 值得后续跟踪灵巧人形移动操作，因为项目同时包含仿真 rollout 任务和真实 G1 demo。

### Robot Athletic Intelligence Lab / Shivesh Kumar
- 机构: Chalmers University of Technology
- 主页: https://chalmers-rail.github.io/
- 关键主题: 欠驱动机器人 / 腿足机器人 / 人形机器人 / 最优控制 / 强化学习 / 硬件-算法协同设计
- 备注: 官方实验室页说明 RAIL 研究 underactuated robots、legged machines 和 humanoids 的 physical and athletic intelligence，并欢迎 PhD、Postdoc 和硕士论文候选人。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Chalmers Robot Athletic Intelligence Lab (RAIL)
- 类型: PhD / Postdoc / 硕士论文；另有待核验的具体 postdoc 信号
- 地点: Gothenburg, Sweden
- 来源: 官方实验室页；具体 postdoc 信号来自第三方岗位聚合页
- 截止时间: unknown
- 主题: legged humanoid robotics / dynamic locomotion / optimal control / reinforcement learning / underactuated systems
- 状态: watching / 加入 confirmed 前需核验
- 摘要: RAIL 官方页明确欢迎 PhD students、postdoctoral researchers 和 master's thesis students。第三方页面提到 Chalmers 有 legged humanoid robotics postdoctoral researcher 岗位，但本次运行未能核验到官方 Chalmers vacancy 直链，因此先作为 watch item，不作为已确认岗位。

### EPFL BioRobotics Laboratory
- 类型: PhD / Postdoc
- 地点: Lausanne, Switzerland
- 来源: 官方实验室页
- 截止时间: unknown
- 主题: humanoid / locomotion / neuromechanics / bio-inspired control / reinforcement learning
- 状态: active
- 摘要: 官方 openings 页面继续列出 Fall 2026 的 PhD/Postdoc 机会，方向是用人形机器人研究和利用人类步行 neuromechanics。

</details>
