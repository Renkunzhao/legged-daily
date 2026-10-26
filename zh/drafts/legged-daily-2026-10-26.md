[English](../../drafts/legged-daily-2026-10-26.md) | **中文**
# Legged Daily - 2026-10-26

## 摘要
- 刷新（下午运行）：ViT-H（arXiv，2026-10-23；北大 / BIGAI）用扩散模型直接从单目视频生成人形参考动作，并以跟踪结果做 DPO 后训练；报告了 G1 实时视频遥操作。
- RPL（CoRL 2026；arXiv 于 2026-10-04 更新）通过地形专家训练与多深度相机 Transformer 蒸馏实现双向感知运动；Amazon FAR 官方代码已收录在 repos.md。
- 刷新：CoCarry（arXiv，2026-10-23；SII / 同济 / TUM）围绕共享物体接触结构，把双人协同搬运重定向到两台人形机器人；原始双人动捕已在 Hugging Face 公开（未注明许可）。
- 刷新：TeleAI 发布 NEXUS 感知全身遥操作官方代码及 G1 ONNX 模型；南大 SuperMimic 复现补齐 G1 完整 sim-to-real 部署并有约 46 秒实机舞蹈。另列一个 MuJoCo G1 全身 MPC/TSID 实现（仅仿真）。
- Hugging Face 核验到三份既有公开资源：HIW-500 的 G1 居家实机记录、NVIDIA GRAIL 的物理验证交互动作，以及 MOSAIC 的 G1 重定向动作。
- 丹麦奥胡斯大学 A3 Lab 的 Physical AI 博士岗位 2026-11-01 截止；偏通用机器人基础模型，并非专门的腿足运动岗位。

<details>
<summary><strong>新论文</strong></summary>

### ViT-H: Generative Video-To-Humanoid Control with Motion Tracking Feedback
- Link: https://arxiv.org/abs/2610.32966
- Source: arXiv 预印本；未注明正式接收会议或期刊
- Date: 2026-10-23
- Authors: Zimo He, Tianyi Bian, Zizhong Yang, Hongjie Li, Nan Jiang, Jieming Cui, Baoxiong Jia, Yizhou Wang, Siyuan Huang, Yixin Zhu
- Topics: 人形机器人 / 视频到动作 / 扩散模型 / 动作跟踪 / DPO / 遥操作
- Summary: 以扩散模型直接从单目视频生成人形参考动作，替代“重建—重定向—跟踪”流水线，并利用动作跟踪结果做直接偏好优化后训练；自回归变体支持实时视频遥操作。
- Notes: 在 Unitree G1 上评估；作者报告遥操作延迟低于 400 ms（项目页：平均约 250 ms，RealSense D455 RGB 输入），并随模型和数据规模提升。项目：https://awfuact.github.io/vit-h/ 。项目页链接的代码仓库（github.com/mileret/ViT-H-release）在 2026-10-26 返回 404，代码是否开放尚未确认。

### RPL: Learning Robust Humanoid Perceptive Locomotion on Challenging Terrains
- Link: https://arxiv.org/abs/2602.03002
- Source: CoRL 2026（项目官网标注）；arXiv 初稿 2026-02-03，最新版本 2026-10-04
- Date: 2026-10-04
- Authors: Yuanhang Zhang, Younggyo Seo, Juyue Chen, Yifu Yuan, Koushil Sreenath, Pieter Abbeel, Carmelo Sferrazza, Karen Liu, Rocky Duan, Guanya Shi
- Topics: 人形机器人 / 感知运动 / 多深度相机 / 师生蒸馏 / Transformer / sim-to-real
- Summary: 先训练具有特权高程图输入的地形专家，再蒸馏到多相机深度 Transformer，并利用与速度指令相关的深度特征缩放及随机侧向遮挡增强楼梯、坡面和踏石上的双向运动能力。
- Notes: 官网 https://rpl-humanoid.github.io/ 展示实机复杂地形和 2 kg 负载实验，报告深度渲染约 5 倍加速。官方代码 https://github.com/amazon-far/RPL 已在 repos.md 收录；本次是因近期公开代码而补录的历史论文，不是 10 月 26 日新发表。

### CoCarry: Contact-Support-Structured Retargeting for Dual-Humanoid Cooperative Carrying
- Link: https://arxiv.org/abs/2610.32460
- Source: arXiv 预印本；未注明正式接收会议或期刊
- Date: 2026-10-23
- Authors: Ziyu Lin, Shihang Du, Tianhang Wang, Xiaodong Liu, Runze Zhang, Zongyou Yu, Haodong Zhang, Alois Knoll, Guang Chen
- Topics: 人形机器人 / 多机器人 / 动作重定向 / 人-物交互 / 协同搬运 / 数据集
- Summary: 提出双人协同搬运动捕数据集，以及围绕同一物体轨迹联合优化两台人形机器人的重定向方法：物体局部手部锚点保持四手抓握关系，上身交互结构与下身支撑结构保持物体相对几何与协调支撑。
- Notes: 作者报告在两台智元 A3 上接触保持率 0.9995，穿透时长较 GMR / OmniRetarget 分别减少 67% / 71%；在 CORE4D + G1 上接触保持率 0.9906；并有两台 A3 实机协同搬运实验。论文描述 220 段 / 21 种方案，原始双人动捕已公开于 https://huggingface.co/datasets/sii-pi-lab/CoCarry （227 段 / 23 类，BVH 约 120 Hz + 1080p 视频，公开获取，未注明许可，不含重定向后的机器人轨迹）；许可明确后可作为数据集条目提议。与 STR（2026-10-25 草稿）为同一团队。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### Gamma-Robot/NEXUS
- Link: https://github.com/Gamma-Robot/NEXUS
- Category: 控制 / 强化学习 / 遥操作 / 动作数据工具
- Robot Type: 人形（Unitree G1）
- Simulator: mjlab 1.5.2（MuJoCo Warp）
- Deploy: 仿真（sim-to-sim 与 sim-to-real 部署代码标注为尚未发布）
- Summary: NEXUS（arXiv:2609.39000）官方代码：地形感知动作适配（接触检测、骨盆调整、关键帧 IK）、特权 PPO 教师、基于深度图的感知学生策略，实现地形自适应全身遥操作；附预训练 G1 ONNX 策略。
- Notes: 来自 TeleAI（中国电信人工智能研究院）/ 上海交大等；通讯作者为张伟楠、白辰甲。许可：CC BY-NC 4.0（LICENSE 文件）。包含平地/地形配对示例动作。项目：https://nexus-humanoid.github.io/ 。

### NJU-R-L-Group-Embodied-Lab/SuperMimic-Repro-Sim2Real
- Link: https://github.com/NJU-R-L-Group-Embodied-Lab/SuperMimic-Repro-Sim2Real
- Category: 控制 / 世界模型 / 动作跟踪 / 部署
- Robot Type: 人形（Unitree G1）
- Simulator: mjlab
- Deploy: 仿真 + 实机（ONNX + Unitree SDK 真机部署）
- Summary: 基于 CuboiLeo/SuperMimic-Reproduced 的非官方 SuperMimic 复现，增加 BONES-SEED 规模训练、自定义舞蹈动作、视频提取动作工具和完整 G1 部署代码；预训练模型和实机视频在 GitHub Releases。
- Notes: README 报告：LAFAN1 严格按论文设置得分 0.56（论文 0.82），BONES-SEED（约 13 万段）得分 0.93、46 段失败；G1 实机完整跳完约 46 秒舞蹈，最大倾角偏差 16.3°。MIT 许可；数据集不随仓库分发。与 SuperMimic 原作者无关。

### tanmay2002/unitree-g1-whole-body-control
- Link: https://github.com/tanmay2002/unitree-g1-whole-body-control
- Category: MPC / 全身控制 / 轨迹规划 / 工具框架
- Robot Type: 人形机器人 — Unitree G1（23 个受控关节）
- Simulator: MuJoCo / Pinocchio / TSID
- Deploy: 仿真
- Summary: 建立从 Herdt/LIPM 在线 MPC 质心与落足规划到 2 ms TSID 逆动力学 QP 控制的闭环框架，支持步行期间同步执行手臂操作任务。
- Notes: 波恩大学学生研究工程；作者报告仿真中以 0.2 m/s 完成 12 步、特定测试中 QP 失败为零。没有证实真实机器人部署。

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

### 白辰甲 — 中国电信人工智能研究院（TeleAI）
- Institution: 中国电信人工智能研究院（TeleAI）
- Homepage: https://baichenjia.github.io/
- GitHub: https://github.com/Gamma-Robot
- Lab / Department: TeleAI 具身智能研究中心
- Key Topics: 人形 / 全身控制 / 遥操作 / 感知 / 强化学习
- Notes: NEXUS 共同通讯作者（另一位为上海交大张伟楠），官方代码和 G1 模型于 2026-10-23 发布。学生及代表作待核实，暂不列出。

### 张力 — 复旦大学 Logos Intelligence Lab
- Institution: 复旦大学 / 上海创智学院
- Homepage: https://lzrobots.github.io/
- GitHub: https://github.com/LogosIntelligenceLab
- Lab / Department: 大数据学院 Logos Intelligence Lab
- Key Topics: 人形 / 动作重定向 / 物理智能
- Notes: SMR（arXiv:2610.29169，2026-10-21）的来源团队：由语义条件物理专家蒸馏得到的流式人形重定向器；代码尚未发布（https://github.com/LogosIntelligenceLab/SMR 仅有项目 README）。

### 黄思远 — 北京大学 / BIGAI（已有条目更新）
- Institution: 北京大学 / 北京通用人工智能研究院
- Homepage: https://siyuanhuang.com/
- Key Topics: 人形 / 视频到人形控制 / 动作生成
- Notes: 已有条目更新：与朱毅鑫共同参与 ViT-H（arXiv:2610.32966）。

### 陈广团队 — SII PI Lab / 同济（草稿信号更新）
- Institution: 同济大学 / 上海创智学院
- Lab / Department: Physical Intelligence Lab
- Key Topics: 人形 / 重定向 / 人-物交互 / 多人形协作
- Notes: 一周内第二篇重定向论文（继 STR 之后的 CoCarry）；Hugging Face 组织 https://huggingface.co/sii-pi-lab 托管 CoCarry 数据。

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
