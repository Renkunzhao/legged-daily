[English](../../drafts/legged-daily-2026-09-17.md) | **中文**
# 腿足机器人日报 - 2026-09-17

## 摘要
- PASSAGE 将场景对齐的人形穿越学习扩展到 1,500 个杂乱场景、100 小时数据，并将规划、建图和 50 Hz 全身执行完整部署到机器人本体。
- RecMorph 以拓扑顺序双向循环网络实现跨形态单策略控制，覆盖 UNIMAL、四种标准四足平台及作者报告的 Go1/Go2 无跌倒实机试验。
- ETH Zürich 的 KINO 用全身与物体关键帧作为 VLM 规划和 RL 控制之间的紧凑接口；作者评测中，稀疏关键帧条件下的端到端成功率由 44% 提升至 92%。
- 今日只收录一个高信号官方仓库：RecMorph 提供可复现的 MuJoCo/UNIMAL 与 Isaac Lab 两条实验链路，而不是只放论文占位代码。
- 此前追踪的 LAAS-CNRS 安全强化学习人形机器人博士岗位已在官方门户明确显示不可申请，建议从活跃招聘列表移除。

<details>
<summary><strong>新论文</strong></summary>

### PASSAGE: Scaling Scene-Aligned Motion Learning for Perceptive Humanoid Traversal in Cluttered Environments
- 链接：https://arxiv.org/abs/2609.18732
- 来源：arXiv
- 日期：2026-09-16
- 作者：Yuxuan Ma、Zicheng Zeng、Chunlin Peng、Zhoujian Li、Zetong Zhao、Zhikai Zhang、Yunrui Lian、Han Xue、Sikai Liang、Weiyi Zhu、Mulin Chen、Chenghuai Lin、Jiayu Zeng、Yanwei An、Songan Zhang、Jiayuan Gu、Jilong Wang、Jingbo Wang、He Wang、Li Yi
- 主题：感知人形穿越 / 场景对齐动作数据 / 流匹配 / 全身跟踪 / 本体建图
- 摘要：从场景对齐示范中学习单一的感知条件规划器—跟踪器，使机器人无需技能标签或障碍物专用策略，即可选择并组合跨越、侧身穿过和低头钻过等行为。
- 备注：项目报告采集了 1,500 个杂乱场景中的 100 小时 VR/IMU 动作数据；数据规模从 6 小时增至 100 小时时，平均无接触成功率从 48.1% 提升到 68.9%，最终加入经验证场景增强的模型达到 70.3%。部署系统在 Jetson AGX Orin 上集成本体 3D LiDAR、在线建图、6.25 Hz 规划与 50 Hz 跟踪，并在 50 个未见实体布局中测试。以上为作者报告结果，本次未独立复现。

### RecMorph: Topology-Guided Spatial Recurrence for Generalized Morphology Control
- 链接：https://arxiv.org/abs/2609.18359
- 来源：arXiv
- 日期：2026-09-16
- 作者：Quanrui Rao、Yong Liu、Xueming Xiao、Yingbo Luo、Kun Wu、Zhenyu Xu、Meibao Yao
- 主题：通用形态控制 / 四足运动 / 循环策略 / 拓扑感知学习 / sim-to-real
- 摘要：通过深度优先遍历将机器人的运动学树序列化，再用共享双向循环网络变换和传递肢体信息，使单一策略在固定宽度与深度下以线性 token 复杂度适配不同身体结构。
- 备注：评测覆盖五个 UNIMAL 任务，以及 Go1、Go2、ANYmal-B、ANYmal-C 的共享策略基准。作者报告其标称速度 RMSE 比专用 MLP 低 43.5%，并完成 40 次无跌倒的 Go1/Go2 实机试验；代码已公开，但本次未独立复现结果。

### A Keyframe Interface for VLM Planning and Whole-Body Control in Humanoid Loco-Manipulation
- 链接：https://arxiv.org/abs/2609.18869
- 来源：arXiv
- 日期：2026-09-16
- 作者：Fatemeh Zargarbashi、Jin Cheng、Tianxu An、Stelian Coros
- 主题：人形移动操作 / 视觉语言规划 / 关键帧 / 强化学习 / 全身控制
- 摘要：提出 KINO 分层框架：VLM 选择任务相关的全身与物体关键帧，经场景重定向后，由关键帧条件 RL 策略在 Unitree G1 上生成关节级动作。
- 备注：面向语义关键操作阶段的显著性采样，将作者报告的稀疏关键帧端到端成功率从 44% 提升到 92%。评测包括仿真与实机的一手/双手拾取、搬运和放置；本次未发现公开代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### quanruirao/RecMorph
- 链接：https://github.com/quanruirao/RecMorph
- 类别：强化学习 / 通用控制 / 运动基准 / 研究工具链
- 机器人类型：通用形态 / 四足机器人，包括 Go1、Go2、ANYmal-B、ANYmal-C
- 仿真器：MuJoCo / UNIMAL；Isaac Lab 0.41.3 / Isaac Sim 4.5
- 部署：仿真训练与评测，以及论文报告的 Go1/Go2 单一共享策略实机部署
- 摘要：RecMorph 官方实现包含两条可复现实验链路：五个跨形态 UNIMAL 任务，以及在四种标准四足机器人之间共享的 Isaac Lab 控制器，并附专用策略基线与摩擦扫描评测。
- 备注：仓库创建于 2026-09-13，检查时最近推送为 2026-09-15。文档给出精确环境、启动脚本、随机种子、训练预算、冒烟测试、确定性评测和零样本套件；生成的检查点与日志未托管，且本次检查时 GitHub 元数据未声明仓库许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Galbot 主导的 PASSAGE 合作
- 机构：Galbot / 上海期智研究院 / 上海科技大学 / 中关村学院 / 上海交通大学 / 新加坡国立大学 / 清华大学 / 北京大学
- 主页：https://galaxygeneralrobotics.github.io/PASSAGE/
- arXiv：https://arxiv.org/abs/2609.18732
- 关键主题：感知人形穿越 / 场景对齐动作捕捉 / 生成式规划 / 全身控制 / 本体自主系统
- 更新：该合作将大规模场景对齐人体动作采集链路连接到完整本体部署的人形穿越系统。数据规模实验与 50 个未见实体布局测试，使其成为数据驱动感知运动和集成部署方向的强信号。

### 吉林大学主导的 RecMorph 合作
- 机构：吉林大学 / 特种车辆设计制造集成技术全国重点实验室 / 长春理工大学
- arXiv：https://arxiv.org/abs/2609.18359
- GitHub：https://github.com/quanruirao/RecMorph
- 关键主题：通用形态控制 / 跨平台四足运动 / 拓扑感知策略 / 循环架构 / 实机迁移
- 更新：Quanrui Rao、Meibao Yao 等合作者将程序化身体基准连接到标准四足平台的共享控制，并开放两条实验链路。该团队值得用于追踪跨形态策略架构与可复现跨机器人控制。

### ETH Zürich Computational Robotics Lab — KINO
- 机构：ETH Zürich
- 主页：https://crl.ethz.ch/
- arXiv：https://arxiv.org/abs/2609.18869
- 实验室 / 院系：Computational Robotics Lab
- 关键主题：人形移动操作 / VLM 规划 / 强化学习 / 全身控制 / 关键帧接口
- 更新：Fatemeh Zargarbashi、Jin Cheng、Tianxu An 与 Stelian Coros 用稀疏动作关键帧分离语义规划和高频人形控制。其特点是将 VLM 限制为结构化选择，同时保留经过动力学训练的低层策略。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 拟移除 / 过期条目 — LAAS-CNRS Gepetto Team，PhD in Humanoid Robotics: Safe Reinforcement Learning
- 当前状态：已过期 / 不再可申请
- 原因：申请截止时间为 2026-07-31，CNRS 官方门户现已明确显示该岗位不再可用。
- 核验来源：https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 备注：确认后应从活跃招聘列表移除此项。本次未从官方来源核验到信号强度相当的新腿足机器人活跃岗位；现有观察列表机会保持不变。

</details>
