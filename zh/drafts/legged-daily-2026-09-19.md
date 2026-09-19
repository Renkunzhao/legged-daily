[English](../../drafts/legged-daily-2026-09-19.md) | **中文**
# 腿足机器人日报 - 2026-09-19

## 摘要
- SGPS 将采样式 MPC、行为克隆初始化和穿过 MJX 的一阶梯度结合起来，为 Go2、H1 与 G1 训练状态及深度视觉策略；作者报告已在真实 Go2 上使用机载深度实现零样本部署。
- OmniMimic 通过动力学补全的数据增强与渐进式指令扩展，把方向覆盖狭窄的动物示范转化为单一全向四步态策略，并直接在 Unitree Go2 上展示 sim-to-real。
- DR-MPC 将动力学与仿射输入关系松弛为惩罚项，仅保留非空 box constraints，再配合定制内点法；作者报告在 Unitree Go1 上取得 4.4 ms 的机载 MPC 中位耗时。
- 两个研究发布需要区别标注：SGPS 是实质性的 MuJoCo MJX 训练实现，而 OmniMimic 仓库明确只是项目与演示网站，不包含策略训练代码。
- Adorno Lab 新建了实验性 C++ 库，统一封装 Unitree SDK2 的运动、G1 手臂/腰部、低层关节及状态/IMU 接口；它是可复用组件，不是完整机器人驱动。
- NVIDIA 官方招聘站出现新的“Machine Learning Engineer - Humanoid Robotics”职位标题页；当前抓取页未展示地点和详细要求，因此先作为待进一步核验的观察信号。

<details>
<summary><strong>新论文</strong></summary>

### Accelerating Visual Policy Learning with Sampling-Based Model Predictive Control
- 链接：https://arxiv.org/abs/2609.20575
- 来源：arXiv
- 日期：2026-09-17
- 作者：Yilang Liu、Haoxiang You、Qian Wang、Daniel Rakita、Ian Abraham
- 主题：视觉运动 / 采样式 MPC / 可微仿真 / 一阶策略梯度 / sim-to-real
- 摘要：Sampling-Guided Policy Search 用采样式 MPC 反复修正动作目标，并通过 MuJoCo MJX 动力学优化策略，使系统无需特权状态教师策略即可直接训练深度视觉策略。
- 备注：论文覆盖仿真 Unitree Go2 与 G1 上的运动、越障、推箱和双手搬运任务。作者报告可在单 GPU 上训练，并将统一视觉 Go2 策略零样本迁移到实机，依靠机载深度完成小跑、匍匐、跨栏及行为切换；本次未独立复现结果。

### OmniMimic: Dynamics-completed Motion Augmentation for Multi-style Omnidirectional Quadruped Locomotion
- 链接：https://arxiv.org/abs/2609.20566
- 来源：arXiv
- 日期：2026-09-17
- 作者：Sheng Wu、Guoqiang Zhao、Zhe Yang、Fei Teng、Zhikun Zhou、Zheng Fang、Hong Zheng、Yaonan Wang、Kailun Yang
- 主题：四足运动 / 动作模仿 / 多步态控制 / 强化学习 / sim-to-real
- 摘要：OmniMimic 将方向有限的动物示范转化为机器人特定的时间反转和镜像物理监督，再通过渐进式指令扩展及步态专用残差专家，训练单一全向策略。
- 备注：评测覆盖 trot、pace、canter 和 pronk。作者报告相对匹配的 APEX 基线，足端位置 RMSE 降低 12.9%，指令网格速度跟踪 RMSE 降低 63.1%，并无需微调直接部署到 Unitree Go2；公开项目仓库只有演示，没有训练代码。

### DR-MPC: Fast and Feasible Dynamics-Relaxed Model-Predictive Control for Legged Locomotion
- 链接：https://arxiv.org/abs/2609.20035
- 来源：arXiv
- 日期：2026-09-17
- 作者：Run Wang、Alapati Tuerxun、Shuo Liu、Wei Xiao、Ján Drgoňa、Yilin Mo、Liang Wu
- 主题：四足运动 / 模型预测控制 / 二次规划 / 实时优化 / 实机控制
- 摘要：DR-MPC 将近似动力学和仿射输入关系移入二次惩罚，仅保留非空 box constraints，并利用所得 block-arrow 结构设计定制内点求解器。
- 备注：在相同 DR-MPC 形式下，作者报告端到端中位速度相对 HPIPM 提升 16.0 倍、相对 OSQP 提升 4.4 倍，机载 MPC 更新中位耗时为 4.4 ms，并在 Unitree Go1 上完成实机验证。论文称代码将在发表后开放；今日未找到官方实现。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### YilangLiu/Sampling-Guided-Policy-Search
- 链接：https://github.com/YilangLiu/Sampling-Guided-Policy-Search
- 类别：强化学习 / MPC / 控制 / 工具链
- 机器人类型：四足 / 人形
- 仿真器：MuJoCo MJX
- 部署：仿真 / 实机
- 摘要：SGPS 官方实现将 DIAL-MPC 参考生成和循环修正、行为克隆预热以及穿过 MJX 的一阶策略优化结合起来，覆盖 Go2、H1 与 G1 任务。
- 备注：仓库记录了状态与第一视角深度两条流程、运动和越障任务、G1 推箱、任务 YAML、参考轨迹校验及训练入口。机器人模型已随仓库提供，但生成的参考轨迹和检查点未托管；检查时 GitHub 元数据未声明许可证。

### Adorno-Lab/unitree_drivers
- 链接：https://github.com/Adorno-Lab/unitree_drivers
- 类别：工具链 / 控制 / 硬件接口
- 机器人类型：人形 / 四足 / Unitree 通用产品线
- 仿真器：无
- 部署：实机
- 摘要：基于 C++17 与 pImpl 的实验性 Unitree SDK2 封装，覆盖高层运动、G1 手臂/腰部控制、低层关节指令以及状态/IMU 遥测。
- 备注：该库构建三个可复用 CMake target，依赖 Unitree SDK2、Eigen3 与 DQ Robotics。文档明确说明它是上层 facade 或机器人驱动的构件，而非完整驱动；仓库采用 LGPL-2.1，于 2026-09-18 创建。

### OmniMimic/OmniMimic.github.io
- 链接：https://github.com/OmniMimic/OmniMimic.github.io
- 类别：查看器 / 项目页
- 机器人类型：四足
- 仿真器：无
- 部署：浏览器 / 实机演示
- 摘要：OmniMimic 官方项目站仓库，托管仿真结果以及 Unitree Go2 在全向指令下执行 trot、pace、canter、pronk 的视频。
- 备注：这是无依赖的 GitHub Pages 与媒体预处理仓库。README 明确声明它只托管网站，并非策略训练实现；检查时 GitHub 元数据未声明许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Yale University / University of Sydney — SGPS 合作
- 机构：Yale University / University of Sydney
- arXiv：https://arxiv.org/abs/2609.20575
- GitHub：https://github.com/YilangLiu/Sampling-Guided-Policy-Search
- 实验室 / 院系：Yale Mechanical Engineering 与 Computer Science；University of Sydney Electrical and Computer Engineering
- 关键主题：采样式 MPC / 可微仿真 / 视觉运动 / 移动操作 / sim-to-real
- 备注：Yilang Liu、Haoxiang You、Qian Wang、Daniel Rakita 与 Ian Abraham 将采样规划、可微策略学习和直接视觉策略部署连接起来，并横跨 Go2 与 G1。配套仓库完整度较高，使该合作网络成为计算高效、接触丰富策略学习的重要新来源。
- 学生及代表作：
  - [Yilang Liu](https://github.com/YilangLiu) — [Sampling-Guided Policy Search](https://github.com/YilangLiu/Sampling-Guided-Policy-Search)

### Kailun Yang / Hunan University — OmniMimic 合作
- 机构：Hunan University / China Mobile Group Hunan Company
- 主页：https://omnimimic.github.io/
- arXiv：https://arxiv.org/abs/2609.20566
- GitHub：https://github.com/OmniMimic/OmniMimic.github.io
- 实验室 / 院系：School of Artificial Intelligence and Robotics；National Engineering Research Center of Robot Visual Perception and Control Technology
- 关键主题：四足运动 / 动作模仿 / 表现型多步态控制 / 强化学习 / sim-to-real
- 备注：Sheng Wu、Kailun Yang 等合作者围绕“从动物示范学习表现型四足运动，同时保留广域指令跟踪和实机迁移”形成了新的来源信号。后续跟踪价值取决于团队是否发布训练代码或动作数据。
- 学生及代表作：
  - [Sheng Wu](https://arxiv.org/abs/2609.20566) — [OmniMimic](https://omnimimic.github.io/)

### Tsinghua University / Johns Hopkins University — DR-MPC 合作
- 机构：Tsinghua University / Johns Hopkins University / Boston University / Nanyang Technological University
- arXiv：https://arxiv.org/abs/2609.20035
- 实验室 / 院系：Tsinghua Department of Automation 与跨机构控制/优化合作网络
- 关键主题：腿足 MPC / 实时优化 / QP 求解器 / 接触感知控制 / 实机部署
- 备注：Run Wang、Liang Wu、Yilin Mo、Ján Drgoňa 等合作者围绕机载计算时延和在线可行性，共同设计 MPC 形式、接触感知参数化与求解器，是高相关度的模型控制信号。值得继续关注论文所称的发表后代码发布。
- 学生及代表作：
  - [Run Wang](https://arxiv.org/abs/2609.20035) — [DR-MPC](https://arxiv.org/abs/2609.20035)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### NVIDIA — Humanoid Robotics
- 类型：Machine Learning Engineer
- 来源：官方招聘页 — https://jobs.nvidia.com/careers/job/893394875865?domain=nvidia.com
- 截止时间：未知
- 主题：人形机器人 / 机器学习 / 机器人学习
- 状态：观察中
- 备注：NVIDIA 官方招聘端点当前显示“Machine Learning Engineer - Humanoid Robotics”标题。抓取页面未展示地点、职责或申请截止时间，因此先记录为高相关观察信号，而不是完整核验的活跃岗位；加入正式 jobs 列表前应再次检查完整职位页。

### 拟移除 / 过期条目 — LAAS-CNRS Gepetto Team，PhD in Humanoid Robotics: Safe Reinforcement Learning
- 当前状态：已过期 / 不再可申请
- 原因：申请截止时间为 2026-07-31，CNRS 官方门户现已显示该职位不再可用。此移除项已在 2026-09-17 草稿中提出，目前仍等待确认。
- 核验来源：https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
