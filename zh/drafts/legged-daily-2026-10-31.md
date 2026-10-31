[English](../../drafts/legged-daily-2026-10-31.md) | **中文**
# 腿足机器人研究日报 - 2026-10-31

## 摘要
- **TACOS** 利用腿足状态估计器的接触残差自动构造足端地形不稳定性标签，再训练视觉地形预测器；包含 ANYmal-D 野外测试和 50 m 森林路段实验，MIT 许可代码已开放。
- **FORGE** 已被 Humanoids 2026 接收：先学习在线简化动力学参考生成器，再训练完整人形机器人跟踪器，真实 G1 展示全向高速运动、转向和单脚跳。
- **SONIC-K1** 将通用全身 Motion Tracking 迁移到 22 自由度 Booster K1，作者报告约 100 GPU 小时训练，已开放策略权重；仿真表现较好，但实机迈步、转向仍有限。
- **新仓库**：核验 TACOS 正式实现、SONIC-K1 训练与评测工具，以及第三方 AME / AME-2 风格 G1 注意力高程图策略复现。
- **数据更新**：ETH RSL 于 2026-10-30 为已跟踪的 EgoHTR 发布全部 55 段 G1 重定向动作，提供 Isaac Lab 与 MuJoCo 两套格式；数据仍需同意访问条款，许可为 CC BY 4.0。
- **招聘**：新发现 Boston Dynamics Spot 强化学习研究岗位；此前跟踪的 Aarhus Physical AI 博士岗位于 **11 月 1 日 23:59 CET** 截止。

<details>
<summary><strong>新论文</strong></summary>

### TACOS: Terrain-Aware COntact Supervision for Visual Footstep Planning
- Link: https://arxiv.org/abs/2610.37806
- Source: arXiv 预印本，已投稿 ICRA 2027（尚未确认接收）
- Date: 2026-10-27
- Authors: Jean-Michel Fortin, William Larrivée-Hardy, Gabriel Jeanson, Olivier Gamache, Daniele De Martini, François Pomerleau, Philippe Giguère
- Topics: 四足机器人 / 足端落点安全 / 接触感知 / 自监督 / 地形不确定性 / 状态估计
- Summary: 利用腿足因子图状态估计的接触残差构建足端不稳定性分数，并投影到之前拍摄的相机图像以监督密集视觉预测；比较利用事后信息的 hard 分数与实时可用的 causal soft 分数。
- Notes: 1,716 个人工标注落足事件中，作者报告相对最强对照方法的严重程度排序提升 28%；真实 50 m 森林实验可识别泥地、植被等非几何地形因素。复现代码：https://github.com/norlab-ulaval/TACOS；使用 GrandTour ANYmal-D 数据及 DINOv3/DPT。尚未正式接收会议。

### FORGE: Feasible Online Reduced-Order Reference Generation and Whole-Body Execution for Agile Humanoid Locomotion
- Link: https://arxiv.org/abs/2610.37974
- Source: Humanoids 2026 已接收（arXiv 论文稿）
- Date: 2026-10-27
- Authors: Adrian B. Ghansah, Yujin An, Jeeseop Kim, Soon-Jo Chung
- Topics: 人形机器人 / 简化动力学 / 在线动作参考 / 强化学习 / 全身跟踪
- Summary: 首先结合单刚体动力学与完整人形运动学训练指令条件化的简化模型参考生成器，再固定生成器，通过在线参考轨迹训练完整动力学下的 Motion Tracking Policy，实现统一策略控制多种运动模式。
- Notes: 作者在真实 Unitree G1 报告前后速度 -2.0 至 2.8 m/s、侧向速度最大 ±1.0 m/s、角速度最大 ±3.0 rad/s，以及单脚跳和连续指令切换。这些是论文展示的实验范围，不是普适性能保证。尚未核实完整训练代码开放。

### SONIC-K1: Porting a Universal Humanoid Motion Tracker to a Small Humanoid on a Single GPU
- Link: https://arxiv.org/abs/2610.39327
- Source: arXiv 预印本（尚未确认正式会议或期刊）
- Date: 2026-10-29
- Authors: Kyrylo Kolesnichenko, Jong-Hoon Kim
- Topics: 人形机器人 / 通用动作跟踪 / 小型机器人迁移 / 低计算成本训练 / Sim-to-Real / 控制延迟
- Summary: 将 NVIDIA SONIC 方法适配 22 自由度 Booster K1，开放单 GPU 训练流程、策略权重、MuJoCo 评测工具和多动作全身跟踪方案。
- Notes: 作者报告约 100 GPU 小时训练，以及在 MuJoCo 中按 SONIC 成功判据计算的 97.4% 留出动作通过率；与原始 SONIC 的跨机器人计算量比较不构成严格对照。初步实机能跟踪上半身和缓慢动作，但迈步与转向仍不稳定。代码：https://github.com/Kyk0/sonic-k1；权重：https://huggingface.co/Kyry10/sonic-k1 。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### norlab-ulaval/TACOS
- Link: https://github.com/norlab-ulaval/TACOS
- Category: 感知 / 自监督地形标注 / 视觉落足风险预测 / 工具
- Robot Type: 四足机器人（ANYmal-D；可替换机器人专属运动学模块）
- Simulator: 以野外数据和离线模型训练为主，不依赖特定仿真器
- Deploy: 数据 / 真实机器人研究评测
- Summary: 提供 GrandTour 数据下载、因子图接触残差标签生成、DINOv3+DPT 训练、交叉验证和单张图像不稳定性预测完整流程。
- Notes: README 包含两次野外记录的小规模训练示例、CSV/PNG 数据规范与训练评测命令。代码 MIT 许可；下载的 DINOv3 预训练权重另受 Meta 许可约束。

### Kyk0/sonic-k1
- Link: https://github.com/Kyk0/sonic-k1
- Category: 强化学习 / Motion Tracking / 重定向接口 / 评测 / 部署工具
- Robot Type: 人形机器人（Booster K1，22 自由度）
- Simulator: Isaac Lab / MuJoCo
- Deploy: 仿真 / 初步实机实验
- Summary: 基于 SONIC 的 K1 全身跟踪开源工程，提供 PyTorch/ONNX 权重、留出动作评测、10 段演示动作、格式转换和可在普通电脑上运行的 MuJoCo 播放脚本。
- Notes: 基于 NVIDIA GR00T-WholeBodyControl 的第三方分支，不是 NVIDIA 官方 K1 版本。代码 Apache-2.0；权重 CC BY-NC 4.0；BONES-SEED 原始动作需遵守独立许可，仓库不重新分发。真实机器人敏捷步态尚未验证成熟。

### msllqsj/AME_Locomotion_Quad
- Link: https://github.com/msllqsj/AME_Locomotion_Quad
- Category: 强化学习 / 感知式运动 / 注意力高程图编码 / 方法复现
- Robot Type: 人形机器人（Unitree G1 29DoF；虽然仓库名包含 Quad）
- Simulator: Isaac Lab 2.3 / Isaac Sim 5.x
- Deploy: 仿真
- Summary: 第三方复现 AME 注意力地形编码，在自定义 RSL-RL Actor-Critic 中加入高程图编码，提供两阶段训练脚本和两份预训练 .pt 权重。
- Notes: 相比论文加入 xyz 高程点、CNN 步长下采样和 AME-2 风格全局上下文；作者仅报告定性收益，缺少独立受控评测。非 AME 原作者官方仓库，尚未确认真实机器人部署。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### EgoHTR — G1 地形重定向动作更新（已收录数据集的状态变化）
- 链接： https://huggingface.co/datasets/leggedrobotics/egohtr
- 类别： 人体动捕 / 机器人可用动作 / 扫描地形视频 / 优化生成动作
- 对象： 人体与人形机器人（29 自由度 Unitree G1）
- 内容： 55 段与真实地形对齐的 4D 人体动作，现均提供全长度 30 fps 的 G1 重定向版本；源数据包含第一视角视频、IMU 动捕和三维地形扫描，总托管数据约 763 GB。
- 格式： NPZ / SMPL-X / 视频 / 场景网格 / Isaac Lab USD / MuJoCo XML
- 获取方式： 需同意许可（登录 Hugging Face 并接受访问条款）
- 许可： CC BY 4.0，附带禁止去匿名化及遵守数据更新/删除请求等要求
- 摘要： ETH RSL 于 2026-10-30 新增两种完整 G1 重定向结果：基于 GMR、配备 Isaac Lab USD 场景的版本，以及基于 OmniRetarget、配备 MuJoCo 场景的非穿透版本，同时修复足部锁定数据泄漏和部分动作问题。
- 备注： 此项是现有 datasets.md 中 EgoHTR 条目的可核实更新，不是新增的另一套数据集。论文 CoRL 2026：https://arxiv.org/abs/2607.13472；处理代码：https://github.com/leggedrobotics/egohtr 。数据卡及文件目录公开，但实际下载需接受访问条件。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Northern Robotics Laboratory / Université Laval — TACOS
- Institution: 加拿大 Université Laval（与英国牛津大学 Mobile Robotics Group 合作）
- arXiv: https://arxiv.org/abs/2610.37806
- GitHub: https://github.com/norlab-ulaval/TACOS
- Lab / Department: Northern Robotics Laboratory
- Key Topics: 四足机器人 / 落足稳定性 / 地形可通行性 / 自监督视觉感知 / 状态估计
- Notes: 新发布的代码将腿足估计器接触残差转换为视觉监督信号，使用 GrandTour 野外数据并进行了真实室外落足风险预测实验。

### Soon-Jo Chung — Caltech / FORGE 合作
- Institution: 美国加州理工学院（合作作者来自 University of Texas at El Paso）
- arXiv: https://arxiv.org/abs/2610.37974
- Lab / Department: Control and Dynamical Systems
- Key Topics: 人形机器人 / 简化动力学 / 模型引导 / 敏捷运动 / 全身强化学习
- Notes: FORGE 已被 Humanoids 2026 接收，在 G1 上展示使用统一参考生成器与跟踪器完成多种敏捷运动。

### Marco Hutter / ETH Zurich Robotic Systems Lab — EgoHTR 更新
- Institution: ETH Zurich
- Homepage: https://rsl.ethz.ch/
- GitHub: https://github.com/leggedrobotics/egohtr
- Lab / Department: Robotic Systems Lab
- Key Topics: 人体地形重建 / 人形运动 / 动作重定向 / 地形感知
- Notes: 已追踪的研究来源于 2026-10-30 开放 EgoHTR 的全部 55 段全长度 G1 重定向动作，包含两类仿真器可用格式，值得关注它们在感知式全身动作跟踪中的应用。

### Jemin Hwangbo / KAIST Robotics and AI Lab — RAIBO-Wagon
- Institution: 韩国科学技术院（KAIST）
- arXiv: https://arxiv.org/abs/2610.39267
- GitHub: https://github.com/InsungYang/raibo-wagon
- Lab / Department: Robotics and Artificial Intelligence Lab
- Key Topics: 四足机器人 / 拖拽动力学 / 学习式正向模型 / Flow Matching / MPPI / 野外导航
- Notes: 2026-10-29 新预印本结合正向动力学、Flow Matching 初始化和 MPPI，作者报告狭窄室外路径 40 次测试成功率 85%，最多拖动 40 kg 负载。关联 GitHub 目前主要是项目页，并非已经确认开放完整训练与规划代码。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Boston Dynamics — Reinforcement Learning & Controls Research Scientist, Spot Behavior
- Type: Research Scientist / Research Engineer
- Location: 美国马萨诸塞州 Waltham
- Source: Boston Dynamics 官方 Workday 招聘 — https://bostondynamics.wd1.myworkdayjobs.com/Boston_Dynamics/job/Waltham-Office-POST/Reinforcement-Learning---Controls-Research-Scientist---Spot-Behavior_R2862
- Deadline: unknown
- Topics: 四足机器人 / Spot / 强化学习 / 运动控制 / Isaac Sim / MuJoCo / 实机部署
- Status: watching
- Notes: 本次新发现的已有官方岗位，负责 Spot 的 RL 运动策略训练、底层控制集成和 sim-to-real；招聘描述仍可检索，但未能独立确认当前申请表是否仍接受提交。

### Aarhus University / Adaptive & Agentic AI (A3) Lab — Physical AI PhD（截止提醒）
- Type: PhD
- Location: 丹麦奥胡斯
- Source: 大学官方岗位公告 — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: 机器人 / VLA / World Models / 适应学习 / Physical AI
- Status: active
- Notes: 前期草稿已出现过的岗位，此处为官网核对后的截止提醒，并非新岗位；截止日期为明天。属于相关具身智能方向，不是专门的腿足运动控制岗位。

</details>
