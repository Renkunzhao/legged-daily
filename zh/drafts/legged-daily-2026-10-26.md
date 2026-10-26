[English](../../drafts/legged-daily-2026-10-26.md) | **中文**
# Legged Daily - 2026-10-26

## 摘要
- RPL（CoRL 2026；arXiv 于 2026-10-04 更新）通过地形专家训练与多深度相机 Transformer 蒸馏实现双向感知运动；Amazon FAR 官方研究代码近期已公开，原官方仓库已收录在 repos.md。
- Humanoid SRL（2026-10-19，arXiv）为人形机器人增加辅助机械臂，结合轨迹优化、目标条件强化学习及接触丰富的实机移动操作。
- ProTrav（2026-10-22，arXiv）将空间相关的地形高程不确定性传播到可通行性分布，用于风险敏感 MPPI；尚未核实其使用腿足机器人验证。
- GitHub API 检索发现两个非官方 SuperMimic 复现工程，以及新的 G1 MuJoCo 全身 MPC/TSID 控制实现，均不应视为已经部署实机。
- Hugging Face 核验到三份既有公开资源：HIW-500 的 G1 居家实机记录、NVIDIA GRAIL 的物理验证交互动作，以及 MOSAIC 的 G1 重定向动作。
- 丹麦奥胡斯大学 A3 Lab 的 Physical AI 博士岗位 2026-11-01 截止；偏通用机器人基础模型，并非专门的腿足运动岗位。

<details>
<summary><strong>新论文</strong></summary>

### RPL: Learning Robust Humanoid Perceptive Locomotion on Challenging Terrains
- Link: https://arxiv.org/abs/2602.03002
- Source: CoRL 2026（项目官网标注）；arXiv 初稿 2026-02-03，最新版本 2026-10-04
- Date: 2026-10-04
- Authors: Yuanhang Zhang, Younggyo Seo, Juyue Chen, Yifu Yuan, Koushil Sreenath, Pieter Abbeel, Carmelo Sferrazza, Karen Liu, Rocky Duan, Guanya Shi
- Topics: 人形机器人 / 感知运动 / 多深度相机 / 师生蒸馏 / Transformer / sim-to-real
- Summary: 先训练具有特权高程图输入的地形专家，再蒸馏到多相机深度 Transformer，并利用与速度指令相关的深度特征缩放及随机侧向遮挡增强楼梯、坡面和踏石上的双向运动能力。
- Notes: 官网 https://rpl-humanoid.github.io/ 展示实机复杂地形和 2 kg 负载实验，报告深度渲染约 5 倍加速。官方代码 https://github.com/amazon-far/RPL 已在 repos.md 收录；本次是因近期公开代码而补录的历史论文，不是 10 月 26 日新发表。

### Humanoid SRL: Augmenting Humanoids with Supernumerary Limbs for Coordinated Loco-Manipulation
- Link: https://arxiv.org/abs/2610.25628
- Source: arXiv 预印本；尚未确认会议或期刊正式接收
- Date: 2026-10-19
- Authors: Fukang Liu, Feiyang Wu, Paul Barsa, Jaehwi Jang, Akshat Jain, Zhigen Zhao, Yipu Chen, Zhaoyuan Gu, Nikhil Vemuri, Anshul Chandaliya, Kaijie Zhu, Sean Lublinsky, Matthew Zhu, Tony G. Chen, Ye Zhao
- Topics: 人形机器人 / 形态增强 / 多接触移动操作 / 轨迹优化 / 强化学习
- Summary: 为人形机器人安装额外机械臂，通过模型驱动轨迹优化生成动态可行动作，训练目标条件化 RL 全身控制器，从而协调原有双臂和第三只机械臂执行接触丰富的任务。
- Notes: 作者报告了零样本仿真到实机迁移及部分任务的视觉引导扩散策略演示；实验视频：https://humanoid-srl.github.io/ 。正式发表状态与完整训练代码开放情况仍待核实。

### ProTrav: Probabilistic Traversability with Elevation Uncertainty Propagation for Risk-aware Off-road Navigation
- Link: https://arxiv.org/abs/2610.30839
- Source: arXiv 预印本；尚未确认正式会议或期刊接收
- Date: 2026-10-22
- Authors: Chuanlin Zuo, Miloš Prágr, Arun Kumar Singh, Mohammad Loni, Reza Ghabcheloo
- Topics: 地形感知 / 概率高程图 / 不确定性传播 / 可通行性 / MPPI
- Summary: 利用稀疏变分高斯过程建立概率高程场，通过函数空间采样保留相邻地形的空间相关性，将可通行性均值与风险传递给 MPPI 规划器。
- Notes: 作者报告仿真导航成功率超过 90%，所对比基线不足 40%，并进行了真实野外机器人测试。这属于与腿足感知相关的邻近工作；论文摘要未证明测试平台为腿足机器人。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### OMEGA-i/SuperMimicKit
- Link: https://github.com/OMEGA-i/SuperMimicKit
- Category: 强化学习 / 动作跟踪 / 可微仿真 / 动作重定向 / 工具框架
- Robot Type: 人形机器人 — Unitree G1 / Unitree H2 / Agibot A3
- Simulator: MuJoCo Warp；浏览器 ONNX Runtime Web / WebGPU 和 MuJoCo WASM
- Deploy: 仿真 / 浏览器
- Summary: 独立复现 SuperMimic 思路，提供 world model 与策略导出、UMR/SOMA 动作重定向、实验性 ONNX 权重预览和浏览器运行演示。
- Notes: 2026-10-24 发布预览权重；README 中 G1、H2 各自 val37 验证仍有大量失败（31/37 与 30/37）。并非原作者官方代码，也未验证实机部署；动作数据不随代码发布。

### tanmay2002/unitree-g1-whole-body-control
- Link: https://github.com/tanmay2002/unitree-g1-whole-body-control
- Category: MPC / 全身控制 / 轨迹规划 / 工具框架
- Robot Type: 人形机器人 — Unitree G1（23 个受控关节）
- Simulator: MuJoCo / Pinocchio / TSID
- Deploy: 仿真
- Summary: 建立从 Herdt/LIPM 在线 MPC 质心与落足规划到 2 ms TSID 逆动力学 QP 控制的闭环框架，支持步行期间同步执行手臂操作任务。
- Notes: 波恩大学学生研究工程；作者报告仿真中以 0.2 m/s 完成 12 步、特定测试中 QP 失败为零。没有证实真实机器人部署。

### kangzejian1896/supermimic-g1-reproduction
- Link: https://github.com/kangzejian1896/supermimic-g1-reproduction
- Category: 强化学习 / 可微世界模型 / 动作跟踪 / 可复现研究
- Robot Type: 人形机器人 — Unitree G1
- Simulator: MuJoCo Warp / mjlab
- Deploy: 仿真
- Summary: 独立 G1 SuperMimic 复现，提供 168k 迭代的策略和 world-model 预览权重、评测脚本、复现实验说明，以及参考轨迹和仿真跟踪对比视频。
- Notes: 约 2026-10-24 发布 v0.2.0-168k。README 报告使用 84,287 段动作（170.11 小时），128 条验证动作也用于选模型，不属于独立最终测试。代码 MIT，权重许可条款尚待明确；非论文作者官方实现。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### HIW-500: Humanoids In-the-Wild Dataset
- Link: https://huggingface.co/datasets/BitRobot/HIW-500
- Category: 机器人实机日志 / 机器人动作 / 视频
- Subject: Unitree G1；东南亚 12 处真实住宅
- Content: 作者报告 500+ 小时、23K+ 段轨迹、10+ 种家居任务、约 10 TB 原始数据；包含关节状态、腕部和头部图像、IMU、里程计和人类全身遥操作动作。
- Format: 原始 ROS bag / MCAP；另有 LeRobot 格式：https://huggingface.co/datasets/BitRobot/HIW-500-LeRobot
- Access: 公开；数据页面和文件列表可访问，但原始数据在线预览存在字段类型转换错误
- License: CC BY 4.0（数据卡声明）
- Summary: 跨家庭环境的真实 G1 全身遥操作数据，适合研究长期移动操作、视觉策略学习和泛化运动技能。
- Notes: 本次新发现并核验的既有 2026 年数据资源，不表示今日新发布；在线 Viewer 出错不等于数据文件未开放。

### NVIDIA GRAIL Loco-Manipulation Trajectories
- Link: https://huggingface.co/datasets/nvidia/PhysicalAI-Robotics-Locomanipulation-GRAIL
- Category: 机器人动作 / 优化或仿真生成 / 视频 / 基准
- Subject: Unitree G1 及仿真环境中的交互物体
- Content: 物理仿真验证的人形—物体交互动作，包括桌面与地面操作、坐下、路缘、坡面和楼梯；Hugging Face 训练集元数据约 2k 行。
- Format: SMPL-X 与物体 6-DoF 重建、机器人与物体轨迹、源视频和物体 USD 资产
- Access: 公开；文件已发布，但在线预览因单行内容过大而失败
- License: 原始动作数据采用 CC BY-NC 4.0；模型权重、RoboCasa/ComAsset 衍生网格和其他第三方资产另有上游许可
- Summary: 从合成视频和人体—物体四维重建到 G1 动作重定向，再通过仿真跟踪生成的全身交互动作，可作为移动操作的参考数据。
- Notes: 数据页显示 2026 年 7 月已有更新；不同预训练权重条目仍存在发布说明不一致，不能把所有资源一概视为同一许可。

### MOSAIC Human and G1 Motion Dataset
- Link: https://huggingface.co/datasets/BAAI-Humanoid/MOSAIC_Dataset
- Category: 机器人动作 / 人体动捕 / 生成动作
- Subject: Unitree G1 重定向动作与人体光学、惯性及生成动作
- Content: 仓库文件总量约 45.9 GB，包含光学、惯性和 GENMO 生成人体动作，及各约 30 分钟的 PICO VR、Noitom 适配数据。
- Format: 人体 AMASS 风格 NPZ / MCAP；G1 重定向 NPZ；生成动作和文本提示
- Access: 公开；数据卡及可下载文件列表已核验
- License: CDLA-Permissive-2.0（数据卡声明）；上游动作来源和工具仍可能有独立条款
- Summary: 面向人形动作跟踪、遥操作和残差自适应的多源动作集，并提供转换为 G1 格式的训练参考动作。
- Notes: Hugging Face 在线 Viewer 的 20 行文本不是完整动作数量；相关论文：https://arxiv.org/abs/2602.08594 。再次分发前须遵守 AMASS 等上游许可。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Amazon Frontier AI & Robotics — RPL 多机构合作
- Institution: Amazon FAR / Carnegie Mellon University / Stanford University / UC Berkeley
- Homepage: https://rpl-humanoid.github.io/
- GitHub: https://github.com/amazon-far/RPL
- Lab / Department: Amazon FAR（Frontier AI & Robotics）及高校合作者
- Key Topics: 人形机器人 / 感知运动 / 深度地形编码 / 师生蒸馏 / sim-to-real
- Notes: 已有研究网络的更新：CoRL 2026 RPL 和正式公开的研究代码串联多相机渲染、双向运动与复杂地形实机验证；并非新增成立的实验室。

### Fukang Liu / Ye Zhao — Humanoid SRL 合作团队
- Institution: Georgia Institute of Technology（佐治亚理工学院）
- Homepage: https://fukangl.github.io/
- Lab / Department: Humanoid SRL 作者合作网络
- Key Topics: 人形机器人 / 物理交互 / 形态增强 / 接触优化 / 全身强化学习
- Notes: Fukang Liu 个人研究主页列出 Humanoid SRL（arXiv:2610.25628，2026-10-19）、Opt2VLA 和 Opt2Skill；新增机械臂系统将接触规划、全身学习及真实机器人实验结合。该链接是研究者主页，而非单独实验室官网。
- Students and Representative Works:
  - [Fukang Liu](https://fukangl.github.io/) — [Humanoid SRL](https://arxiv.org/abs/2610.25628)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 丹麦奥胡斯大学 Aarhus University — A3 Lab Physical AI 博士
- Type: PhD（三年）
- Location: 丹麦奥胡斯（Aarhus）
- Source: 奥胡斯大学官方招聘 — https://phd.tech.au.dk/for-applicants/apply-here/saeropslag/phd-position-in-physical-ai-adaptive-foundation-models-for-robotics
- Deadline: 2026-11-01 23:59 CET
- Topics: 视觉语言动作模型 / 世界模型 / 机器人学习 / 自适应基础模型 / 边缘推理
- Status: active
- Notes: 导师为 Behzad Bozorgtabar 和 Qi Zhang；计划 2027-01-01 或之后入学。该岗位属于与腿足相邻的通用具身基础模型方向，并非专门研究双足/四足运动；官方要求入学前获得硕士学位、具备实际模型开发经验。本次为新发现的已有岗位，非今日新开放。

</details>
