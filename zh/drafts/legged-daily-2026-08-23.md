[English](../../drafts/legged-daily-2026-08-23.md) | **中文**
# 腿足机器人日报 - 2026-08-23

## 摘要
- `GigaBrain-WBC-0.5` 将人形全身动作跟踪重构为行为世界模型，同时预测动作、下一状态与可行的后续行为；项目报告了较强的地形交互、不合理指令鲁棒性和跌倒恢复表现。
- `MILD` 为可屈服地面上的双足运动引入物理约束的离散元地形模型和地形感知强化学习控制器，并通过真机展示在线地面刚度辨识与适应。
- `AdaPT` 从转播视频学习职业网球动作风格，显式让规划器适应执行速度误差，并在 Unitree G1 和全尺寸 Dobot Atom 人形机器人上展示对打与发球。
- Apache-2.0 许可的官方仓库 `noitom-robotics/AdaPT` 是今日唯一达到收录质量门槛的新仓库；当前版本覆盖基于 MJLab/MuJoCo 的第一阶段自适应发球跟踪，并提供预训练 checkpoint。
- 今日未选入独立的新实验室/教授条目或可操作招聘机会；EPFL BioRob 的人形机器人神经力学 PhD/博士后职位已明确关闭。

<details>
<summary><strong>新论文</strong></summary>

### GigaBrain-WBC-0.5: A Behavior World Model for Robust Whole-Body Control with Environment Interaction
- 链接：[arXiv](https://arxiv.org/abs/2608.18234) · [项目页](https://shepherd1226.github.io/gigabrain-wbc-0.5/)
- 来源：arXiv / 官方项目页
- 日期：2026-08-18
- 作者：Ziyang Cheng、Tianshu Tang、Jinxin Lan、Xinze Chen、Yuhan Gong 等
- 主题：humanoid / whole-body control / behavior world model / terrain and object interaction / fall recovery
- 摘要：训练因果 Transformer 联合预测下一动作、本体感知状态和潜在行为指令分布，并在部署时用该分布把物理上不合理的指令在线投影到可行的 best-effort 行为。
- 备注：项目报告相对三种大规模动作跟踪基线取得 81.3% 地形交互成功率、83.1% 不合理指令下存活率和 99.3% 跌倒恢复率。真机实验使用 Unitree G1，论文还报告通过简单微调迁移到 Maker L01。今日未核验到官方代码或 checkpoint 发布。

### MILD: Tractable Terrain Modeling for Learning Improved Bipedal Locomotion on Deformable Surfaces
- 链接：https://arxiv.org/abs/2608.19955
- 来源：arXiv；期刊信息为 IEEE Robotics and Automation Letters (2025)
- 日期：2026-08-20
- 作者：Jiahui Zhang、Zhe Xu、Wanyue Li、Xinqi Li、Xuechao Chen、Zhangguo Yu、Annan Tang、Peng Lu
- 主题：bipedal locomotion / deformable terrain / contact modeling / reinforcement learning / sim-to-real
- 摘要：把用于空间变化可屈服地形的物理约束离散元接触求解器，与采用潜变量调制和本体感知估计的地形感知深度强化学习运动控制器结合。
- 备注：作者报告其训练接触场景比对比方法更多样、更贴近真实，并在真机上实现跨不同刚度表面的在线辨识和适应。工作来自香港大学 ArcLab，并与北京理工大学、东京大学合作；Peng Lu / ArcLab 已在追踪列表中，因此不重复作为新实验室条目。

### Towards Professional Tennis Styles for Humanoid Robots with Adaptive Motion Planning and Tracking
- 链接：[arXiv](https://arxiv.org/abs/2608.20087) · [项目页](https://humanoidtennis.github.io/AdaPT/) · [代码](https://github.com/noitom-robotics/AdaPT)
- 来源：arXiv / 官方项目页
- 日期：2026-08-20
- 作者：Tao Huang、Ruofei Liu、Xuchen Tang、Xinyin Zhang、Junli Ren 等
- 主题：humanoid / athletic skills / motion planning and tracking / imitation from video / sim-to-real
- 摘要：AdaPT 将风格化动作规划与底层跟踪解耦，在 tracker 训练中随机化执行速度，并让 planner 以学习到的 motion-speed adapter 为条件，从而减轻长期 sim-to-real 误差累积。
- 备注：官方材料展示了从转播视频和动作捕捉学习职业风格，在 Unitree G1 与全尺寸 Dobot Atom 上完成对打和发球，包括无需动作捕捉的野外发球。项目报告数据集包含 21.5 小时动作、6 种运动员风格和 7 类击球/发球动作。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### noitom-robotics/AdaPT
- 链接：https://github.com/noitom-robotics/AdaPT
- 类别：humanoid motion learning / reinforcement learning / toolkit
- 机器人类型：humanoid — 已发布训练配置使用 Unitree G1；论文还评测 Dobot Atom
- 仿真器：MJLab / MuJoCo
- 部署：支持仿真训练与回放；论文/项目页记录了真机结果，但当前 README 未说明硬件部署代码
- 摘要：AdaPT 的 Apache-2.0 官方 PyTorch 实现，当前发布第一阶段自适应网球发球跟踪环境、训练/回放命令、动作样例和预训练 Unitree G1 checkpoint。
- 备注：创建于 2026-08-20；核验时 55 stars。发布版使用 4,096 个环境训练，并构建于 `mjlab` 和 AdaMimic 之上。论文描述的完整对打/规划栈尚未全部开放，因此应视为部分但有实质内容的首版发布。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今日未选入足够独立的新实验室或教授条目。MILD 进一步强化了已追踪的 Peng Lu / 香港大学 Adaptive Robotic Controls Lab 信号；AdaPT 则是 Noitom Robotics、上海人工智能实验室、Dobot Robotics 与上海交通大学的新合作，但其本身尚不足以在所选论文和仓库之外构成独立实验室/教授更新。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日未选入新的高置信度、可操作腿足机器人招聘机会。

EPFL BioRob [官方职位页面](https://www.epfl.ch/labs/biorob/openings/)列出一个面向 2026 年秋季的人类运动神经力学、生物启发控制、强化学习和人形机器人 PhD/博士后项目，但页面已将两个职位明确标记为 **CLOSED**。因此这里只将其记录为已关闭的来源检查，不作为活跃机会。

今日未发现 tracked jobs 列表中需要移除的过期条目。

</details>
