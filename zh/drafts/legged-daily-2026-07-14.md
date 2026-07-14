[English](../../drafts/legged-daily-2026-07-14.md) | **中文**
# 腿足机器人日报 - 2026-07-14

## 摘要
- 今天最强的论文信号是直接腿足方向：flowable slope 上的双足 terradynamics、面向腿足 RL 的 symmetry/Koopman 辅助学习，以及触觉增强的四足移动操作。
- 双足坡面论文尤其值得看：它提醒我们，形态设计和“主动操纵地形响应”也可以进入 locomotion policy/design space，而不只是被当作需要抑制的扰动。
- SKooP 是高信号学习方法论文：它把形态对称性和 learned Koopman predictions 结合起来，并把 Koopman 预测作为 critic privileged observation，用于提升腿足 RL 的学习速度和泛化/迁移能力。
- 今天仓库信号偏实用：一个 Isaac Lab fault-tolerant quadruped locomotion 环境、一个 Unitree G1 linear MPC/WBID locomotion stack，以及一个 MuJoCo convex-MPC biped 实现。
- 招聘跟踪需要修正：EPFL BioRob 的 humanoid-neuromechanics opening 页面现在在摘要里显示 CLOSED，因此现有 active/watching 条目需要复核后再继续作为 active 推送。

<details>
<summary><strong>新论文</strong></summary>

### Robust bipedal locomotion on flowable slopes via foot-driven terrain manipulation
- 链接: https://arxiv.org/abs/2607.11855
- 来源: arXiv
- 日期: 2026-07-13
- 作者: Deniz Kerimoglu, Junnosuke Kamohara, Jiyeon Maeng, Ziwon Yoon, Seth Hutchinson, Ye Zhao, Daniel I. Goldman
- 主题: bipedal locomotion / granular terrain / terradynamics / foot morphology / terrain manipulation
- 摘要: 研究双足机器人在颗粒坡面等 flowable terrain 上的运动，用带 cleated feet 的小型 robophysical biped 做系统实验，发现中等 cleat spacing 可以调节基质应力并改善坡面行走，而过稀或过密都会导致性能下降甚至失败。
- 备注: 对户外可变形地形上的腿足机器人很相关；关键启发是 foot design 和 terrain response control 可以成为主动 locomotion mechanism，而不只是鲁棒控制要抵消的误差源。

### SKooP: Symmetric Koopman Predictions for Faster and More Generalizable Legged Robot Locomotion with Reinforcement Learning
- 链接: https://arxiv.org/abs/2607.11624
- 来源: arXiv
- 日期: 2026-07-13
- 作者: Evelyn D'Elia, Weishu Zhan, Giulio Turrisi, Giulio Romualdi, Giuseppe L'Erario, Raffaello Camoriano, Wei Pan, Daniele Pucci
- 主题: legged locomotion / reinforcement learning / symmetry / Koopman models / sample efficiency / sim-to-real transfer
- 摘要: 提出 SKooP，在训练 locomotion policy 的同时学习 Koopman dynamics model，把 Koopman predictions 作为 critic 的 privileged observations，并在 actor、critic、encoder、decoder 中加入 group symmetries，以得到更等变、更容易学习和迁移的腿足 RL 策略。
- 备注: 如果后续 artifact 或 benchmark 细节足够完整，适合进入长期论文列表；也和 iit-DLSLab 一类关注 sample-efficient / transferable locomotion learning 的工作形成连接。

### TAC-LOCO: Unified Whole-Body Control for Quadrupedal TACtile-Informed LOCO-Manipulation
- 链接: https://arxiv.org/abs/2607.10132
- 来源: arXiv
- 日期: 2026-07-11
- 作者: Muqun Hu, Yuhao Zhou, Kabir Ray Malik, Chi Lin, Won Suk Lee, Yu She, Yan Gu
- 主题: quadruped / loco-manipulation / tactile sensing / whole-body control / reinforcement learning / sim-to-real
- 摘要: 提出 TAC-LOCO，一个触觉增强的统一 RL 控制器；它把 tactile array latent features 和 proprioception 融合起来，同时控制 Unitree Go2、机械臂和夹爪，在外力变化的动态移动操作任务中调节身体、末端和抓取稳定性。
- 备注: 论文报告了在 Unitree Go2 + WidowX 250 + tactile gripper 上的 zero-shot hardware deployment，并在 load changes / sudden release 场景下降低抓取力、提升物体稳定性。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### fault-locomotion-isaaclab
- 链接: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- 类别: RL / locomotion / simulator / deployment
- 机器人类型: quadruped
- 仿真器: Isaac Lab / MuJoCo
- 部署: both
- 摘要: 面向 motor failures 的 quadrupedal locomotion Isaac Lab DirectEnv，支持 Aliengo 和 Go2 的 flat/rough blind、rough-vision 环境，提供 MuJoCo sim-to-sim 和 ROS2 sim-to-real 部署路径。
- 备注: README 关联 concurrent state estimation、rapid motor adaptation 和 Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion；是跟踪执行器退化/失效下四足鲁棒 locomotion 的实用来源。

### g1_locomotion
- 链接: https://github.com/ioloizou/g1_locomotion
- 类别: MPC / whole-body control / simulator
- 机器人类型: humanoid
- 仿真器: MuJoCo
- 部署: sim
- 摘要: 一个硕士论文实现的 Unitree G1 线性 locomotion stack，把 Single Rigid Body Dynamics 和 Whole-Body Inverse Dynamics 组合成级联控制架构，并提供 MuJoCo 直线行走 demo。
- 备注: README 明确说明尚未在真机上测试；更适合作为 Unitree G1 上 linear MPC/WBID 的紧凑参考实现，而不是 deployment-ready stack。

### convex-mpc-biped
- 链接: https://github.com/ispaik06/convex-mpc-biped
- 类别: MPC / control / simulator
- 机器人类型: humanoid / biped
- 仿真器: MuJoCo
- 部署: sim
- 摘要: C++17 / MuJoCo 实现的 convex MPC biped/humanoid locomotion 原型，基于 single-rigid-body model，包含 contact-wrench optimization、Raibert-style swing-foot planning，以及 OSQP/Eigen 基础设施。
- 备注: 近期小仓库；在出现硬件验证或更广机器人支持前，先按教育/原型级 convex-MPC 实现跟踪。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Dynamic Legged Systems Lab / IIT
- 机构: Istituto Italiano di Tecnologia
- 主页: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- GitHub: https://github.com/iit-DLSLab
- 实验室 / 部门: Dynamic Legged Systems Lab
- 关键主题: quadruped / locomotion / fault tolerance / reinforcement learning / Isaac Lab / MuJoCo / ROS2 deployment
- 备注: 新的 fault-locomotion-isaaclab 仓库是围绕 motor-failure robustness、sim-to-sim 和 sim-to-real quadruped locomotion 的具体来源信号，并关联 arXiv 工作 “Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion”。

### Georgia Tech / bipedal granular locomotion collaboration signal
- 机构: Georgia Institute of Technology and collaborators
- 主页: https://arxiv.org/abs/2607.11855
- 实验室 / 部门: paper source / collaboration network
- 关键主题: bipedal locomotion / granular media / terradynamics / foot-terrain interaction
- 备注: Deniz Kerimoglu 等人的 flowable-slope biped 论文，是围绕 Daniel I. Goldman、Ye Zhao 及合作者在可变形基质上腿足运动研究的有用 source-network 信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL Biorobotics Laboratory / Auke Ijspeert
- 类型: PhD / Postdoc
- 地点: Lausanne, Switzerland
- 来源: 官方网站
- 截止时间: unknown / review needed
- 主题: humanoid / human locomotion neuromechanics / bio-inspired locomotion control / reinforcement learning
- 状态: watching
- 备注: 官方 openings 页面仍保留 humanoid-neuromechanics 项目描述，但摘要现在把该 opening 标为 CLOSED，postdoc 申请段落也写着 positions are now closed。现有 master-list 状态应复核后再继续标 active。

### Proposed Removal / Stale Item
- Current Status: possibly stale / no longer actionable
- Reason: EPFL BioRob humanoid-neuromechanics opening 之前被跟踪为 active，但官方页面现在在 summary 中显示 CLOSED，并在 postdoc 段落说明 positions are now closed；PhD 段落仍留有旧的 rolling-style instructions，因此建议人工确认后再删除或降级。
- Source Checked: https://www.epfl.ch/labs/biorob/openings/

### ETH Zurich Robotic Systems Lab
- 类型: PhD / PostDoc / Research Staff / Software Engineer / Robot Design Engineer / Embedded Systems Engineer / Electronic Engineer
- 地点: Zurich, Switzerland
- 来源: 官方网站
- 截止时间: rolling / unknown
- 主题: legged robots / mobile manipulators / motion planning / MPC / reinforcement learning / perception / navigation / robot design / ROS / C++
- 状态: active
- 备注: ETH RSL 官方页面继续列出 PhD、postdoc、research staff/software engineering、robot design、embedded systems 和 electronics 等滚动机会，并明确关联 legged robots、mobile manipulators、field robotics、control、learning、planning 和 deployment。

</details>
