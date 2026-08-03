[English](../../drafts/legged-daily-2026-08-03.md) | **中文**
# Legged Daily - 2026-08-03

## 摘要
- 3 篇高信号论文进入评审队列：Science Robotics 对腿足机器人领域的整体展望、面向托管式人形机器人基础模型闭环适配的 CLIFT，以及携带物体举升时人形机器人平衡能力的动力学分析与控制。
- 3 个新发布仓库达到实现质量门槛：腿足移动操作开门系统 TheDoorGym、横跨 Isaac Lab 与 MuJoCo 的 Berkeley 四足机器人颠球项目，以及带 checkpoint 和确定性评估的 Isaac Lab H1 足球绕杆任务。
- 今天最突出的主题是接触丰富腿足技能的可复现性：入选仓库不仅有演示，还公开任务代码、保留权重、测试或评估工具，并明确说明局限。
- 今天没有从第一方来源核验到新的实验室或教授动态；已检查论文作者机构和仓库来源，但没有把它们单独视为机构层面的新更新。
- ETH Zurich RSL 的滚动岗位仍有效。CNRS 官方页面现已明确显示 LAAS-CNRS 安全强化学习人形机器人博士职位“不再可用”，进一步支持待确认的过期条目删除建议。

<details>
<summary><strong>新论文</strong></summary>

### Advances, challenges, and opportunities for legged robots
- 链接: https://arxiv.org/abs/2607.28952
- 来源: Science Robotics / arXiv 作者稿
- 日期: 2026-07-29
- 作者: Jonas Frey, Matías Mattamala, Hae-Won Park, Mayank Mittal, Georg Martius, Maike Osborne, Robert Sparrow, Marco Hutter
- 主题: 人形机器人 / 四足机器人 / 硬件 / 运动控制 / 自主性 / 数据 / 应用 / 政策与社会影响
- 摘要: 从领域全局评估人形与四足机器人的现有能力、关键技术瓶颈和应用前景，并讨论更广泛部署伴随的伦理、经济与政策问题。
- 备注: 正式版本发表于 Science Robotics 第 11 卷第 116 期，DOI 为 `10.1126/scirobotics.aee0787`；arXiv 页面是作者稿，适合作为可访问的检索链接。

### CLIFT: Turning Gemini Robotics On-Device into Humanoid Specialists via Non-Invasive Closed-Loop Iterative Fine-Tuning
- 链接: https://arxiv.org/abs/2607.29172
- 来源: arXiv
- 日期: 2026-07-31
- 作者: Yuxin Chen, Hari Srikanth, Nathan Jew, Menglin Wu, Pengcheng Wang, Junli Ren, Masayoshi Tomizuka, Peng Xu, Jinyu Xie, Thomas Tian
- 主题: 人形机器人操作 / 机器人基础模型 / VLA / 闭环适配 / 监督微调 / 真实机器人学习
- 摘要: CLIFT 将部署阶段的奖励反馈转成 API 可接受的监督数据，使闭源 Gemini Robotics On-Device 策略无需访问权重、梯度或损失，也能在敏捷、接触丰富的人形机器人任务上迭代进行闭环改进。
- 备注: 论文报告了较早的一批托管式微调 API 真实人形机器人实证研究，并称两轮数据飞轮后，所选任务接近完美成功率；结果针对通过官方接口适配专有模型，并不意味着基础模型已经开放或可复现。

### Balancing of Humanoid with Object Mass: Trade-off Analyses and Lifting Control
- 链接: https://arxiv.org/abs/2607.29625
- 来源: arXiv
- 日期: 2026-07-31
- 作者: Hyunjong Song, William Z. Peng, Joo H. Kim
- 主题: 人形机器人平衡 / 移动操作 / 全身动力学 / 轨迹优化 / 举升 / 接触约束
- 摘要: 该工作把物体质量纳入全身动力学与平衡状态域约束，刻画临界质量和转换质量，并将所得阈值用于稳定的人形机器人举起保持与举起释放轨迹优化。
- 备注: 论文将分析性的权衡研究与仿真、实验演示结合，为主要依赖启发式或学习方法的人形机器人举升控制提供了一个值得跟踪的模型方法补充。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### DeerYoyo/TheDoorGym
- 链接: https://github.com/DeerYoyo/TheDoorGym
- 类别: 强化学习 / 分层控制 / 腿足操作 / benchmark
- 机器人类型: 四足移动操作机器人；包含 B1Z1 与 B2Z1 资产，发布的最终任务使用 B1Z1
- 仿真器: NVIDIA Isaac Gym Preview 4
- 部署: 仅仿真；未声称完成真实机器人部署
- 摘要: 一个采用 BSD-3-Clause 许可证的可复现项目，利用分层腿足操作流水线完成接近门把手、抓握和按压、推门、松手并穿过门洞的完整流程。
- 备注: 仓库包含高低层训练代码、保留 checkpoint、资产、固定环境配置、校验和与实验历史。最终 Exp68 明确采用混合系统：学习到的高层策略处理接近和接触行为，确定性的物理阶段负责维持抓握、推门、释放和穿越。

### frankwsq242/hierarchical-quadrupedal-juggling
- 链接: https://github.com/frankwsq242/hierarchical-quadrupedal-juggling
- 类别: 强化学习 / 分层控制 / 腿足操作 / sim-to-sim 验证
- 机器人类型: 四足机器人；背部安装球拍的 Unitree Go1
- 仿真器: NVIDIA Isaac Lab 2.3.2 与 MuJoCo
- 部署: 仿真与 sim-to-sim；未声称完成硬件运行
- 摘要: UC Berkeley MEng 毕业项目，将可解释的镜面反射定律或学习型高层规划器与 PPO 躯干跟踪策略结合，使 Go1 在移动时用背部球拍连续颠乒乓球。
- 备注: MIT 许可证仓库包含 Isaac Lab 训练与回放、已提交的 Pi2 checkpoint 和 ONNX 导出、MuJoCo smoke test 与演示，以及详细的跨仿真器诊断。作者明确说明学习型高层 Pi1 尚未收敛，感知原型也未接入部署策略。

### kingjameschan/isaaclab-h1-dribble-slalom
- 链接: https://github.com/kingjameschan/isaaclab-h1-dribble-slalom
- 类别: 强化学习 / 人形机器人运动与操作 / 评估工具
- 机器人类型: 人形机器人；具有 19 个主动关节的 Unitree H1
- 仿真器: NVIDIA Isaac Lab 5.1.0，采用 RSL-RL PPO
- 部署: 仅仿真；未展示真实机器人部署
- 摘要: 一个 GPU 并行 H1 任务，要求机器人把足球保持在近处，按交替方向绕过 4 根可碰撞杆，并最终射门得分。
- 备注: 采用 MIT 许可证的一次性发布仓库包含环境、PPO 配置、几何逻辑测试、评估与录制脚本、最终 checkpoint 和评估 JSON。项目报告在 4,096 个确定性仿真回合中达到 97.97% 进球率，并记录了通过视频检查发现的奖励漏洞；这些数字只适用于其声明的仿真分布。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有从第一方来源核验到新的实验室或教授动态。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab — 滚动研究与工程岗位
- 类型: PhD / PostDoc / 研究人员或软件工程师 / 机器人设计工程师 / 嵌入式系统工程师 / 电子工程师
- 地点: 瑞士苏黎世
- 来源: 官方网站 — https://rsl.ethz.ch/the-lab/open-positions.html
- 截止时间: rolling / 官方页面未注明
- 主题: 腿足机器人 / 移动操作 / 运动规划 / 模型预测控制 / 强化学习 / 感知 / 导航 / 执行器 / 遥操作 / 嵌入式系统
- 状态: 2026-08-03 复核仍有效；此前已跟踪，不是新的 master-list 条目
- 备注: 官方页面仍提供申请链接，并继续列出滚动 PhD、PostDoc，以及研究、软件、机器人设计、嵌入式和电子工程岗位，工作与腿足机器人和真实场景部署直接相关。

### 拟删除 / 过期条目 — LAAS-CNRS Gepetto Team 人形机器人安全强化学习博士职位
- 当前状态: 已过期 / 官方职位不再可用
- 原因: 所列 2026-07-31 23:59 截止时间已经过去，CNRS 官方页面现已明确显示“The requested offer is no longer available”。确认后应从 active master list 删除或标记为过期。
- 已检查来源: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
