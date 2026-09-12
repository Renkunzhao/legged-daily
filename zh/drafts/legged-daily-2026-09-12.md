[English](../../drafts/legged-daily-2026-09-12.md) | **中文**
# 腿足机器人日报 - 2026-09-12

## 摘要
- Georgia Tech 的颗粒地形研究将基于物理的三维阻力理论接触模型与教师—学生强化学习结合，并在 Unitree G1 上展示玄武岩碎料、干沙和海滩沙地奔跑。
- SwingBot 将人形机器人移动能力扩展到地面运动之外：关键帧引导探索与循环特权状态估计器支持采用被动腕钩的连续实机臂荡运动。
- ViBe 使用预训练视觉编码器和低秩适配器，对既有人形运动跟踪器进行感知式全身控制后训练，并跨运动与移动操作任务展示零样本仿真到现实迁移。
- 新仓库信号包括面向实机的 VITA 人形 Python SDK、带强化学习行走策略的完整 ROBOTIS OP3 仿真陪伴机器人栈，以及新的人形感知运动整理索引。
- 今日检查的官方来源中，未筛选到信息足够具体且可核验为仍在招聘的新腿足机器人岗位。

<details>
<summary><strong>新论文</strong></summary>

### Learning Terrain-Adaptive Humanoid Locomotion on Granular Terrain
- 链接：https://arxiv.org/abs/2609.10286
- 来源：arXiv
- 日期：2026-09-09
- 作者：Junnosuke Kamohara、Feiyang Wu、Andy Ningan Zong、Daniel I. Goldman、Yashwanth Nakka、Seth Hutchinson、Ye Zhao
- 主题：人形运动 / 颗粒地形 / 接触建模 / 强化学习 / 仿真到现实
- 摘要：将基于物理的三维阻力理论接触模型集成到强化学习训练中，并把以地形条件为输入的教师策略蒸馏为仅凭本体感知历史在线估计地形性质的学生策略，用于可变形地面运动。
- 备注：[项目主页](https://humanoid-gm-locomotion.github.io/HUMANOID-GM/)。作者报告了 Unitree G1 在玄武岩碎料、干沙、海滩沙以及不同地形过渡场景中的实机实验；代码标注为即将发布，本次未独立复现论文性能结论。

### SwingBot: Learning Whole-Body Brachiation for Humanoid Robots
- 链接：https://arxiv.org/abs/2609.10283
- 来源：arXiv / CoRL 2026
- 日期：2026-09-09
- 作者：Yujie Xiong、Peng Zhai、Taixian Hou、Quancheng Qian、Cunwang Liu、Kangmai Hu、Long Yang、Zhiyan Dong、Lihua Zhang
- 主题：人形运动 / 臂荡 / 全身控制 / 强化学习 / 接触切换
- 摘要：通过仿生关键帧为稀疏的“释放—摆荡—抓取”探索提供支架，并用循环特权信息模型估计位置与腕钩接触隐变量，实现人形机器人的连续臂荡运动。
- 备注：[项目主页](https://ttbray.github.io/SwingBot/)。实机实验报告了采用被动腕钩的连续高空横移，以及对负载、外部扰动和不同横杆间距的鲁棒性；当地面路径受阻时，该能力可补充步行运动。

### ViBe: Visual Behavior Adaptation for Perceptive Humanoid Whole-Body Control
- 链接：https://arxiv.org/abs/2609.09918
- 来源：arXiv
- 日期：2026-09-09
- 作者：Lokesh Krishna、Sarvesh Venkatesan、An Zhang、Quan Nguyen
- 主题：人形感知控制 / 运动跟踪 / 视觉适配 / 参数高效微调 / 移动操作
- 摘要：从预训练视觉编码器提取任务相关反馈，并通过低秩适配器接入既有策略，从而利用策略优化直接将人形运动跟踪器后训练为面向感知任务的控制器。
- 备注：[项目主页](https://lok-i.github.io/vibe-control/)。作者报告了路缘行走、跑酷、立方体翻转、全向物体移动操作和躲避球任务的零样本仿真到现实结果，并测试室外、低照度和视觉干扰条件；论文与项目页目前未链接代码。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### VitaDynamics/humanoid-sdk
- 链接：https://github.com/VitaDynamics/humanoid-sdk
- 类别：实机 SDK / 控制接口 / 示例
- 机器人类型：人形机器人 / VITA
- 仿真器：未记录
- 部署：面向实机的 Linux 客户端；本次未独立核验实机验收
- 摘要：提供 Python SDK 和示例，使外部 Linux 计算机通过 Aorta 消息栈连接 VITA 人形机器人，包含只读状态订阅和需要明确安全授权的全身控制示例。
- 备注：创建于 2026-09-10，更新于 2026-09-12。README 记录 Linux x86_64/aarch64 兼容性、离线包检查、对等连接配置要求和运动安全门控；但检查时仅 1 星、GitHub 未检测到许可证，也没有可查询的最新 GitHub Release，实际部署依赖厂商提供的匹配软件包与凭据。

### YauhenBichel/humanoid-companion
- 链接：https://github.com/YauhenBichel/humanoid-companion
- 类别：强化学习运动 / 人形交互 / 仿真系统栈
- 机器人类型：人形机器人 / ROBOTIS OP3
- 仿真器：MuJoCo / MuJoCo Playground（MJX）
- 部署：仿真；实机适配器仍在路线图中
- 摘要：把随仓库提供的 PPO 行走策略、50 Hz 安全检查控制环、动作手势、浏览器人脸、语音和本地大语言模型接口组合成端到端的小型人形陪伴机器人仿真系统。
- 备注：创建于 2026-09-11，更新于 2026-09-12，采用 Apache-2.0。仓库包含训练、评估、导出、策略一致性测试和域随机化，但当前演示使用仿真 OP3；`DynamixelRobotIO` 与实机行走被明确列为后续工作。

### yhx1203/awesome-perceptive-humanoid-locomotion
- 链接：https://github.com/yhx1203/awesome-perceptive-humanoid-locomotion
- 类别：论文与代码索引
- 机器人类型：人形机器人
- 仿真器：不适用
- 部署：文献 / 资源索引
- 摘要：整理人形感知运动相关论文、项目主页和已公开代码，覆盖视觉跑酷、地形重建、主动视线、触觉感知、世界模型控制与感知退化条件下运动。
- 备注：创建于 2026-09-11，检查时 2 星。它是小型人工整理阅读清单，不是可运行软件；目前以单一“感知运动”表格组织，且仓库未检测到许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Georgia Tech 颗粒地形运动合作团队
- 机构：Georgia Institute of Technology / Northeastern University
- 主页：https://humanoid-gm-locomotion.github.io/HUMANOID-GM/
- 实验室 / 部门：Institute for Robotics and Intelligent Machines / Georgia Tech School of Physics
- 关键主题：人形运动 / 颗粒介质 / 地形动力学 / 强化学习 / 仿真到现实
- 备注：Junnosuke Kamohara、Feiyang Wu、Andy Ningan Zong、Daniel I. Goldman、Yashwanth Nakka、Seth Hutchinson 和 Ye Zhao 在 Unitree G1 实机研究中连接腿足控制与颗粒接触物理。对于刚性地面仿真器难以覆盖的户外运动，这是值得持续跟踪的跨实验室信号。

### 复旦大学 SwingBot 团队
- 机构：复旦大学
- 主页：https://ttbray.github.io/SwingBot/
- 实验室 / 部门：智能机器人与先进制造创新学院
- 关键主题：人形全身控制 / 臂荡 / 强化学习 / 富接触运动
- 备注：SwingBot 团队展示高自由度人形机器人使用被动腕钩进行连续高空运动。这表明该团队的运动研究范围不只包括足—地步行，还覆盖空中接触切换与全身动量控制。

### USC 感知式全身控制团队
- 机构：University of Southern California
- 主页：https://lok-i.github.io/vibe-control/
- 关键主题：人形感知控制 / 运动跟踪 / 视觉表征学习 / 移动操作
- 备注：Lokesh Krishna、Sarvesh Venkatesan、An Zhang 和 Quan Nguyen 发布 ViBe，为既有人形跟踪器提供模块化视觉后训练路径。该项目通过同一参数高效适配机制，把感知运动和以物体为中心的全身任务连接起来。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日检查的官方招聘来源中，没有筛选到信息足够具体且当前可行动的新腿足机器人岗位。NVIDIA 当前可见一个“Research Scientist, Robotics Research — PhD New College Grad 2026”官方页面，但可访问页面只显示职位标题，无法核验其与腿足机器人的直接关联、地点或申请状态，因此本次不作推断、不予收录。今日也不提出过期条目删除建议。

</details>
