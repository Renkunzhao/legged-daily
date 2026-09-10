[English](../../drafts/legged-daily-2026-09-10.md) | **中文**
# 腿足机器人日报 - 2026-09-10

## 摘要
- 一项基于物理的颗粒接触仿真方法让人形机器人运动策略在实机实验中迁移至玄武岩颗粒、干沙和海滩沙地。
- ViBe 通过参数高效的后训练，将预训练运动跟踪器改造成视觉感知式全身控制器，并在四类任务上展示零样本仿真到现实迁移。
- TANGO 将杂乱环境中的人形导航建模为连续全身控制问题，从语言和第一视角 RGB 直接预测 29 自由度动作，并零样本迁移到 Unitree G1。
- DEEP Robotics 近期集中更新了一套连贯的开源工具链，覆盖动作重定向、模仿策略训练，以及更通用的 Isaac Lab 强化学习与部署流程。
- 今日检查的官方来源中，未筛选到信息足够具体、置信度高的新腿足机器人招聘岗位。

<details>
<summary><strong>新论文</strong></summary>

### Learning Terrain-Adaptive Humanoid Locomotion on Granular Terrain
- 链接：https://arxiv.org/abs/2609.10286
- 来源：arXiv
- 日期：2026-09-09
- 作者：Junnosuke Kamohara、Feiyang Wu、Andy Ningan Zong、Daniel I. Goldman、Yashwanth Nakka、Seth Hutchinson、Ye Zhao
- 主题：人形运动 / 颗粒地形 / 强化学习 / 仿真到现实 / 地形适应
- 摘要：提出基于三维阻力理论的高效颗粒接触模型，以及能够识别并适应地形条件的教师—学生运动控制器，并在玄武岩颗粒、干沙和海滩沙地上完成实机验证。
- 备注：[项目主页](https://humanoid-gm-locomotion.github.io/HUMANOID-GM/)。项目主页目前将代码标为“Coming Soon”，不能视为已经开源。

### ViBe: Visual Behavior Adaptation for Perceptive Humanoid Whole-Body Control
- 链接：https://arxiv.org/abs/2609.09918
- 来源：arXiv
- 日期：2026-09-09
- 作者：Lokesh Krishna、Sarvesh Venkatesan、An Zhang、Quan Nguyen
- 主题：人形机器人 / 感知式全身控制 / 运动跟踪 / 视觉适配 / 仿真到现实
- 摘要：提出一种后训练框架，利用预训练视觉特征、多查询提取器和低秩策略适配器，将运动跟踪器转化为感知控制器，并在地形穿越、跑酷、物体操作和躲避球任务上展示零样本实机迁移。
- 备注：[项目主页](https://lok-i.github.io/vibe-control/)。

### TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body Vision-Language-Action Model
- 链接：https://arxiv.org/abs/2609.09158
- 来源：arXiv / CoRL 2026
- 日期：2026-09-08
- 作者：Anqi Li、Yuxin Chen、Zhaobo Li、Zhuo Cao、Junli Ren、Masayoshi Tomizuka、Dhruv Shah
- 主题：人形导航 / 视觉—语言—动作模型 / 全身控制 / 障碍穿越 / 仿真到现实
- 摘要：提出从语言和第一视角 RGB 预测 29 自由度动作的全身 VLA 系统，使用仿真生成的穿越监督数据，并在真实杂乱环境中的 Unitree G1 上实现零样本部署。
- 备注：[项目主页](https://tango-vla.github.io/)。部署系统将服务器上的低频 VLA 推理与机器人本体上的高频运动跟踪器分离。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### DeepRoboticsLab/deep-robotics-mimic
- 链接：https://github.com/DeepRoboticsLab/deep-robotics-mimic
- 类别：强化学习 / 模仿学习 / 工具包
- 机器人类型：人形机器人
- 仿真器：Isaac Lab / Isaac Sim / MuJoCo 查看器
- 部署：仿真与硬件
- 摘要：面向 DR02 Pro，以 DeepMimic 风格奖励训练 PPO 运动跟踪策略，支持重定向动作转换、单卡与多卡训练、评估、ONNX 导出及通过 DEEP Robotics SDK 部署。
- 备注：BSD-3-Clause；2026-09-09 更新。其数据流水线明确接收 `deep-robotics-retarget` 的输出。

### DeepRoboticsLab/deep-robotics-retarget
- 链接：https://github.com/DeepRoboticsLab/deep-robotics-retarget
- 类别：动作重定向 / 工具包 / 查看器
- 机器人类型：人形机器人
- 仿真器：MuJoCo
- 部署：数据处理
- 摘要：通过两阶段逆运动学，将 SMPL-X、BVH 等人体动作源重定向为 DR02 Pro 关节轨迹，并支持可选碰撞规避、批处理和实时可视化。
- 备注：BSD-3-Clause，修改自 GMR；2026-09-08 更新，并作为 `deep-robotics-mimic` 的上游动作数据环节。

### DeepRoboticsLab/rl_training
- 链接：https://github.com/DeepRoboticsLab/rl_training
- 类别：强化学习 / 工具包
- 机器人类型：人形机器人 / 四足机器人
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真与硬件
- 摘要：为 Lite3、M20 四足机器人和 DR02 人形机器人提供基于 RSL-RL 的训练环境及面向部署的工具，包括多 GPU 训练、检查点对比、教程和 ONNX 导出。
- 备注：BSD-3-Clause；2026-09-08 更新。仓库说明仿真和实机策略应配合相应的独立部署仓库使用。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### DEEP Robotics Lab
- 机构：DEEP Robotics
- 主页：https://www.deeprobotics.cn/
- GitHub：https://github.com/DeepRoboticsLab
- 实验室 / 部门：官方开源工程组织
- 关键主题：人形机器人 / 四足机器人 / 运动控制 / 强化学习 / 模仿学习 / 部署
- 备注：近期协调更新展示了更清晰的 DR02 Pro 工作流：用 `deep-robotics-retarget` 完成人体动作重定向，用 `deep-robotics-mimic` 训练 PPO 参考动作跟踪策略，再通过 `rl_training` 覆盖 DR02、Lite3 和 M20 的更通用 Isaac Lab 训练流程。这应视为一个连贯的工具链信号，而非三条相互独立的实验室动态。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日检查的官方招聘来源中，没有筛选到信息足够具体且当前可行动的新腿足机器人岗位。对于无法核验具体职位、地点或在招状态的通用招聘页面，本次选择不作推断、不予收录。

</details>
