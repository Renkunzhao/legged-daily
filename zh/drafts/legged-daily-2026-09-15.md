[English](../../drafts/legged-daily-2026-09-15.md) | **中文**
# 腿足机器人日报 - 2026-09-15

## 摘要
- JEPLO 提出无显式建图的 LiDAR 腿足运动方案，联合学习本体/外感预测表示与运动策略，并在 Unitree Go2 上展示楼梯、箱体、黑暗环境及感知退化条件下的仿真到现实迁移。
- ResSafe 将人形机器人的任务策略与残差安全修正策略分离，在无需在线模型优化的情况下，报告了仿真和负载实机测试中的平衡鲁棒性提升。
- JEPLO 完整开源 Isaac Lab 训练、MuJoCo 验证、Go2/Jetson 部署、数据集、预训练策略支持和硬件搭建资料，采用 GPL-3.0。
- HimLoco-AMP-Lab 是紧凑的 BSD 许可 Go2 PPO/AMP 框架，包含历史观测、专家动作回放、策略导出与 MuJoCo sim-to-sim；专家轨迹有意不随仓库分发。
- 今日未选出新的高置信、可执行招聘机会。Flexion Robotics 的人形运动生成岗位仍在官方招聘页可见，但已在更早草稿记录，因此不重复收录。

<details>
<summary><strong>新论文</strong></summary>

### JEPLO: Joint-Embedding Predictive Learning for LiDAR-Based Legged Locomotion
- 链接：https://arxiv.org/abs/2609.15770
- 来源：arXiv
- 日期：2026-09-14
- 作者：Qihao Yuan、Yixuan Qiu、Ziyu Cao、Ming Cao、Kailai Li
- 主题：四足运动 / LiDAR 感知 / JEPA 世界模型 / 强化学习 / 仿真到现实
- 摘要：用 PE-JEPA 世界模型学习本体感觉和 LiDAR 地形的预测表示，再通过并发 JEPA 教师—学生流程联合训练可部署运动策略，全程不依赖显式地形地图。
- 备注：作者报告了 Unitree Go2 在长楼梯和高箱体上的仿真到现实穿越、黑暗环境运行，以及在 LiDAR 遮挡、稀疏和噪声条件下相对更强的鲁棒性。代码、数据、部署工具和硬件设计均已公开；本次未独立复现结果。

### ResSafe: Learning Safety Filtering with Residual Reinforcement Learning for Humanoids
- 链接：https://arxiv.org/abs/2609.15988
- 来源：arXiv
- 日期：2026-09-14
- 作者：Gechen Qu、Tong Zhang、Bike Zhang、Yen-Jen Wang、Koushil Sreenath、Claire Tomlin、Jason Jangho Choi
- 主题：人形全身控制 / 安全过滤 / 残差强化学习 / 极限平衡 / 仿真到现实
- 摘要：冻结专注任务性能的名义运动策略，再训练独立残差策略叠加安全修正，从而解耦动作跟踪性能与鲁棒性、跌倒规避目标。
- 备注：论文将学习残差与最小范数安全过滤修正联系起来，并报告仿真及随机负载下的实机平衡测试。项目页展示的四组实机动作中，该方法相对名义基线通常减少跌倒，但与经过域随机化的基线及判别超平面基线相比并非每项指标都占优；本次未独立复现。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### ASIG-X/JEPLO
- 链接：https://github.com/ASIG-X/JEPLO
- 类别：强化学习 / 感知运动 / 世界模型 / 部署工具链
- 机器人类型：四足机器人 / Unitree Go2
- 仿真器：Isaac Lab / Isaac Sim 用于训练；定制 Unitree MuJoCo 用于 sim-to-sim
- 部署：仿真与实机；在搭载 Livox Mid-360 和 Jetson AGX Orin 的 Go2 上使用 ONNX/TensorRT 部署
- 摘要：发布 JEPLO 无地图 LiDAR 运动完整栈，包括训练、预训练策略回放、MuJoCo 验证、ROS 2 深度生成、Go2 部署代码、数据集链接和硬件搭建说明。
- 备注：仓库创建于 2026-09-12，检查时最近推送为 2026-09-15；GPL-3.0。README 明确提醒训练可能不稳定，且导出的 TensorRT 模型在控制机器人前应使用录制输入/输出进行一致性验证。

### JF-Li5266/HimLoco-AMP-Lab
- 链接：https://github.com/JF-Li5266/HimLoco-AMP-Lab
- 类别：强化学习 / 模仿学习 / 运动工具链
- 机器人类型：四足机器人 / Unitree Go2
- 仿真器：Isaac Lab / Isaac Sim 用于训练；MuJoCo 用于 sim-to-sim
- 部署：仿真与模型导出；包含 TorchScript/ONNX 导出，但未提供实体机器人部署证据
- 摘要：提供 Go2 的 PPO 与对抗运动先验速度控制任务，包含六帧历史观测、地形课程、域随机化、专家动作回放、检查点回放/导出和 MuJoCo sim-to-sim runner。
- 备注：仓库创建于 2026-07-02，检查时最近推送为 2026-09-12；BSD-3-Clause。AMP 所需的授权专家轨迹需用户在本地提供且不随仓库分发，因此仅凭公开仓库无法完整复现 AMP 路径；纯 PPO 不需要这些数据。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 格罗宁根大学—林雪平大学 ASIG 合作
- 机构：University of Groningen / Linköping University
- 主页：https://asig-x.github.io/jeplo_web/
- GitHub：https://github.com/ASIG-X/JEPLO
- 关键主题：感知腿足运动 / LiDAR / 预测世界模型 / 强化学习 / 仿真到现实
- 更新：Qihao Yuan、Yixuan Qiu、Ziyu Cao、Ming Cao 与 Kailai Li 联合发布 JEPLO，同时开放代码、数据、硬件设计和 Go2 实机演示。这一跨机构信号尤其值得关注其在无显式建图条件下的鲁棒机载感知与地形自适应运动研究。

### 加州大学伯克利分校—UCLA 安全人形控制合作
- 机构：University of California, Berkeley / University of California, Los Angeles
- 主页：https://sciautonomy.github.io/ResSafe_Web/
- arXiv：https://arxiv.org/abs/2609.15988
- 关键主题：人形全身控制 / 安全强化学习 / 安全过滤 / 平衡鲁棒性
- 更新：Gechen Qu 与包括 Koushil Sreenath、Claire Tomlin、Jason Jangho Choi 在内的合作者发布 ResSafe，并给出实机平衡测试。这是学习型全身控制与控制理论安全过滤交叉方向的强信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次未新增高置信、可执行的腿足机器人或人形机器人岗位。Flexion Robotics 位于苏黎世的生成式人形运动研究工程师及实习岗位仍在官方招聘页可见，但二者已在 2026-08-13 草稿记录，因此不重复加入。`jobs.md` 中已有机会在申请前仍应回到官方来源核验状态。

</details>
