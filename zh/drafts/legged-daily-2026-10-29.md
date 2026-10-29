[English](../../drafts/legged-daily-2026-10-29.md) | **中文**
# 腿足机器人研究日报 - 2026-10-29

## 摘要
- **HumanoidNDM（CoRL 2026）**：通过真实机器人本体感知数据、历史神经动力学模型和可微正向运动学，在无外部动作捕捉系统的条件下在线微调 G1 Motion Tracking 策略。
- **随机运动令牌化（Humanoids 2026）**：将复杂全身动作编码成高层可生成的紧凑离散令牌，作者在真实 G1 上展示 16.8 秒动作以及 35 秒跨技能衔接。
- **LSMM 空间记忆**：用位置索引记忆单元解决腿足机器人长时探索中的历史信息丢失；迷宫布局重建误差约降为原来的三分之一，但尚未核实实机运动实验。
- **新代码工程**：Menlo Research 公开 Asimov-1 AMP 训练扩展；独立 SuperMimic 工程开始覆盖肌肉驱动人体模型；Go2 工程提供带多随机种子及负面消融结论的抗推扰评测。
- **数据与机会**：EPFL MuscleMimic 的 GMR 动作数据采用带 AMASS 非商业约束的门控访问；ETH Soft Robotics Lab 有博士及博后岗位，申请滚动审核至 11 月 30 日。

<details>
<summary><strong>新论文</strong></summary>

### HumanoidNDM: Closing the Training-Deployment Gap of Motion Tracking via Humanoid Neural Dynamics Model
- Link: https://arxiv.org/abs/2610.34126
- Source: CoRL 2026（已接收；同时提供 arXiv 预印本）
- Date: 2026-10-25
- Authors: Chao Chen, Zhenrong Wang, Jilong Wang, Yusen Feng, Jiangran Lyu, Li Yi, He Wang
- Topics: 人形机器人 / Motion Tracking / 神经动力学 / 模型梯度微调 / Sim-to-Real / Unitree G1
- Summary: FENCE 对参考动作添加自适应低频扰动来采集适合实机执行的数据；随后基于历史本体感知训练神经动力学模型，利用可微正向运动学提供连杆空间监督，最终通过模型梯度直接微调跟踪策略。
- Notes: 作者在真实 G1 上展示对额外负载等动力学偏差的在线适应，无需外部 MoCap。CoRL 2026 接收状态可由作者主页 https://shenbiachao.github.io/publications/ 核实；暂未确认完整训练代码开放。

### Whole-Body Humanoid Control via Stochastic Motion Tokenization
- Link: https://arxiv.org/abs/2610.36452
- Source: Humanoids 2026（已接收；同时提供 arXiv 预印本）
- Date: 2026-10-27
- Authors: Michael Drolet, Oleg Arenz, Jan Peters
- Topics: 人形机器人 / 全身运动 / 随机运动令牌 / 技能衔接 / Motion Tracking / Unitree G1
- Summary: 使用随机运动 Tokenizer 为高层行为标签或文本条件运动生成提供紧凑离散接口，向底层跟踪控制器提供结构化的未来参考动作，突破仅使用速度指令的控制方式。
- Notes: 作者展示真实 G1 执行各 16.8 秒的舞蹈、格斗、行走动作，以及 35 秒格斗到舞蹈的转换；与 FSQ、VQ-VAE 的比较基于相同 Tokenizer 容量。arXiv 备注注明已接收 IEEE-RAS Humanoids 2026。

### Remember Where You Walk: Learning Spatial Memory for End-to-End Legged Robot Exploration
- Link: https://arxiv.org/abs/2610.37203
- Source: arXiv 预印本（尚未确认会议或期刊接收）
- Date: 2026-10-27
- Authors: Leon Magnus, Nico Bohlinger, Jan Peters, Oleg Arenz
- Topics: 腿足机器人 / 自主探索 / 长期记忆 / 强化学习 / 空间表征
- Summary: Local Spatial Matrix Memory（LSMM）基于 Hadamard Memory，将任务相关信息写入与空间位置对应的记忆单元，使策略能够在观测目标离开视野后仍保留局部环境结构。
- Notes: 在迷宫探索评测中，与循环网络及固定历史基线具有相近覆盖表现，地图布局重建误差约降低三倍；目前主要是导航仿真实验，不能当作已验证的实机腿足 Locomotion 成果。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### menloresearch/asimov-1-amp
- Link: https://github.com/menloresearch/asimov-1-amp
- Category: 强化学习 / AMP / Locomotion / 训练工具
- Robot Type: 人形机器人（Menlo Asimov-1）
- Simulator: Isaac Lab 3.0 / Isaac Sim PhysX
- Deploy: 仿真
- Summary: Menlo Research 官方 AMP 扩展，在 Asimov-1 速度跟踪任务上增加对抗动作先验判别器与 PPO 训练流程，包含 49 秒、50 Hz 的专家行走动作，以及可复现训练指令。
- Notes: BSD-3-Clause；上游基础任务尚待并入 Isaac Lab（PR #7071），暂不支持 Newton / OvPhysX。仓库没有证明实机部署。

### kaibohex/muscle-supermimic
- Link: https://github.com/kaibohex/muscle-supermimic
- Category: Motion Tracking / 可微世界模型 / 强化学习 / 工具
- Robot Type: 肌肉骨骼人形（MS-Human-700 / MyoFullBody）
- Simulator: mjlab / MuJoCo-Warp
- Deploy: 仿真
- Summary: 将 SuperMimic 的可微世界模型训练方法独立移植至肌肉驱动人体模型，通过肌肉与肌腱可微计算学习 100 Hz 的肌肉激励控制，实现全身动作跟踪。
- Notes: 支持 700 肌肉和 354 肌肉模型，作者提供训练权重及独立测试动作评测，但结果仍持续更新且只在仿真验证。代码 Apache-2.0；AMASS 衍生动作数据需门控获取，并受非商业、不得再分发条款限制。不是 SuperMimic 作者的官方实现。

### lbm23/go2-rl-isaacsim
- Link: https://github.com/lbm23/go2-rl-isaacsim
- Category: 强化学习 / 鲁棒性评测 / Sim-to-Sim / 工具
- Robot Type: 四足机器人（Unitree Go2）
- Simulator: Isaac Lab（Newton/MJWarp）/ Isaac Sim PhysX
- Deploy: 仿真
- Summary: 提供 Go2 速度跟踪和多方向推扰恢复的工程复现、随机种子分组评测、冻结模型、统计消融，以及同一策略在两个物理后端之间的迁移。
- Notes: 作者报告特定左向推扰 Checkpoint 比较中跌倒率从 53.81% 降到 16.31%，但八个训练种子的严格消融在多重比较校正后未达到主要统计显著性。没有实机结果；项目自身代码许可尚未明确。

</details>

<details>
<summary><strong>新数据集</strong></summary>

### MuscleMimic GMR Retargeted Motions（全身数据）
- Link: https://huggingface.co/datasets/amathislab/musclemimic-retargeted
- Category: 人体动作捕捉 / 机器人可用动作 / 动作重定向
- Subject: 人体 / MyoFullBody 肌肉骨骼人形模型
- Content: KIT 运动训练 972 段、测试 108 段、AMASS 过渡动作 110 段；公开元数据显示仓库总文件量约 5.64 GB。
- Format: npz（关节位置与速度、连杆位置姿态、速度及元数据）
- Access: gated（须同意数据条款后下载，已核实公开文件目录存在）
- License: other — 限非商业研究用途，受 AMASS 衍生数据条款约束；未经额外授权不可再分发原始或衍生数据。
- Summary: 为 MuscleMimic 全身肌肉驱动控制器准备的 GMR 重定向动作，具备明确的训练/测试划分，可避免反复离线拟合。
- Notes: 这是今日新发现的既有数据资源，并非 10 月 29 日首次发布。Hugging Face 页面可公开浏览不代表匿名用户可以直接下载；项目 https://github.com/amathislab/musclemimic 。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### He Wang / 北京大学人形机器人研究网络
- Institution: 北京大学
- Homepage: https://hughw19.github.io/
- Lab / Department: 计算机科学 / 人形机器人研究合作网络
- Key Topics: 人形机器人 / Motion Tracking / 真实动力学学习 / 策略微调 / Sim-to-Real
- Notes: CoRL 2026 的 HumanoidNDM 在 G1 上实现无需 MoCap 的实机策略适应，体现将真实机器人动力学学习与全身跟踪结合的新方向。作者 Chao Chen 的主页亦确认该工作发表信息：https://shenbiachao.github.io/ 。

### Jan Peters / Oleg Arenz — TU Darmstadt / DFKI 研究网络
- Institution: 达姆施塔特工业大学 / DFKI / Robotics Institute Germany
- Homepage: https://www.ias.informatik.tu-darmstadt.de/
- Lab / Department: Intelligent Autonomous Systems
- Key Topics: 人形机器人 / 全身运动 / 动作表征 / 强化学习 / 空间记忆
- Notes: 该研究合作网络同期出现两项成果：已接收 Humanoids 2026 的随机运动 Tokenization，以及面向长时间腿足探索的 LSMM 空间记忆；可继续关注代码发布和实机导航验证。

### Alexander Mathis / EPFL Mathis Group（数据与方法更新）
- Institution: EPFL
- Homepage: https://cnai.epfl.ch/mm-blog/
- GitHub: https://github.com/amathislab/musclemimic
- Lab / Department: Mathis Group
- Key Topics: 肌肉骨骼机器人 / 动作模仿 / 重定向 / GPU 仿真
- Notes: MuscleMimic 的 GMR 全身动作数据在接受 AMASS 衍生条款后可以访问；新的第三方 muscle-supermimic 项目进一步探索肌肉驱动模型的世界模型跟踪，但后者不是实验室官方发布。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich / Soft Robotics Lab — 机器人学习与软体、肌肉骨骼、生物混合机器人博士岗位（拟新增）
- Type: PhD
- Location: 瑞士苏黎世
- Source: ETH 官方招聘 — https://jobs.ethz.ch/job/view/JOPG_ethz_d3lDgHgDI4ewDFQ1Fb
- Deadline: 2026-11-30（滚动审核至该日）
- Topics: 机器人学习 / 肌肉骨骼驱动 / 柔顺机器人 / Sim-to-Real / 具身智能 / 实机强化学习
- Status: active
- Notes: Robert Katzschmann 团队公开多个全职带薪博士岗位，包含机器人机构设计和实机策略学习两个方向。与腿足驱动、柔顺控制及机器人学习相关，但不是专门的四足 Locomotion 岗位。官方要求将申请材料合并成一个 PDF 在线提交。

### ETH Zurich / Soft Robotics Lab — 机器人学习与软体、肌肉骨骼、生物混合机器人博士后岗位（拟新增）
- Type: Postdoc
- Location: 瑞士苏黎世
- Source: ETH 官方招聘 — https://jobs.ethz.ch/job/view/JOPG_ethz_0Dk3rwrfGt0kHlu7Rh
- Deadline: 2026-11-30（滚动审核至该日）
- Topics: 软体机器人 / 机器人学习 / 肌肉骨骼系统 / 接触丰富控制 / Physical AI
- Status: active
- Notes: 同一实验室的独立博后招聘，官方页面表示有多个岗位，须通过 ETH 在线系统申请。研究方向侧重真实机器人的柔顺驱动与学习控制。

</details>
