[English](../../drafts/legged-daily-2026-07-15.md) | **中文**
# 腿足机器人日报 - 2026-07-15

## 摘要
- GaitSpan 将预训练的人形机器人行走策略扩展为一个由指令调节、同时覆盖行走、慢跑和跑步的策略，核心包括节律生成、步幅塑形和残差适应。
- 一篇新的人形足球视觉带球论文从时序深度观测中学习对手感知的带球能力，但目前证据仅来自仿真，面对主动进攻者时性能明显下降。
- RoboParty 发布 UFO：一个支持 MJLab 训练、动作数据导入、ONNX 导出，并通过独立分支支持 Unitree G1 部署的人形机器人无监督控制框架。
- LAAS-CNRS 开放一个人形机器人博士职位，研究用强化学习和在线 MPC 联合处理接触模式决策与全身动态运动；申请截止 2026 年 7 月 31 日。

<details>
<summary><strong>新论文</strong></summary>

### GaitSpan：从行走生长出人形机器人的跑步能力
- 链接：https://arxiv.org/abs/2607.12114
- 来源：arXiv
- 日期：2026-07-13
- 作者：Kwan-Yee Lin、Zilin Wang、Janelle J. Liu、Stella X. Yu
- 主题：人形机器人运动 / 强化学习 / 步态转换 / 仿真到现实
- 摘要：GaitSpan 复用冻结的行走策略结构，通过组合学习得到的内部节律、塑造适合高速运动的动态步幅并加入残差修正，将预训练行走策略扩展为连续速度范围内的行走、慢跑和跑步式运动；作者还报告了跨形态迁移，以及在未见过的仿真和真实地形上的零样本部署。
- 备注：项目页：https://gaitspan2026.github.io/。检查时项目页的代码按钮指向 https://github.com/LeCAR-Lab/GaitSpan/，但该仓库当时尚无法公开访问。

### 基于特权表征学习的人形足球视觉带球
- 链接：https://arxiv.org/abs/2607.12702
- 来源：arXiv
- 日期：2026-07-14
- 作者：Flavio Maiorana、Valerio Spagnoli、Eugenio Bugli、Flavio Volpi、Daniele Affinita、Vincenzo Suriani、Daniele Nardi、Luca Iocchi
- 主题：人形机器人 / 移动操作 / 强化学习 / 视觉控制 / 足球
- 摘要：该方法先用特权状态训练带球策略，再训练时序深度编码器复现策略使用的任务潜变量，使仿真中的 Booster T1 能直接依靠类似机载传感器的深度观测带球，而不需要显式估计场景状态。
- 备注：项目报告无障碍时成功率为 100%，单个静态障碍时为 96%，面对主动抢球对手时为 46%；目前全部实验均在仿真中完成。项目页：https://lab-rococo-sapienza.github.io/learning-to-dribble/。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### UFO
- 链接：https://github.com/Roboparty/UFO
- 类别：强化学习 / 动作学习 / 部署工具链
- 机器人类型：人形机器人
- 仿真器：MJLab / MuJoCo
- 部署：仿真与实机
- 摘要：一个人形机器人无监督强化学习框架，支持 FB 与 TeCH 训练、机器人感知的动作数据导入、跟踪/目标/奖励推理和 ONNX 导出；Unitree G1 是目前测试最充分的路径，实机部署与遥操作位于独立的 deploy 分支。
- 备注：仓库创建于 2026-07-13，检查时有 43 个 GitHub star。文档明确说明新机器人适配仍属实验功能，需要预先完成重定向的机器人动作数据，且不支持自动动作重定向或跨形态直接复用检查点。

### DribbleMaster
- 链接：https://github.com/Zhuoheng0910/DribbleMaster
- 类别：强化学习 / 运动控制 / 仿真到仿真
- 机器人类型：人形机器人
- 仿真器：Isaac Gym / MuJoCo
- 部署：仿真
- 摘要：新公开的 ICRA 2026 论文“Dribble Master”训练与评估代码，包含 Isaac Gym 人形带球任务、PPO 训练、策略回放和 MuJoCo 仿真到仿真验证。
- 备注：仓库创建于 2026-07-14，采用 MIT 许可证；它对应较早发布的 arXiv:2505.12679，并非本周的新论文。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### RoboParty Lab
- 主页：https://github.com/Roboparty
- GitHub：https://github.com/Roboparty
- 实验室 / 院系：RoboParty Lab
- 关键主题：人形机器人 / 动作重定向 / 模仿学习 / 无监督强化学习 / 部署 / 遥操作
- 备注：该实验室发布 UFO，同时在 https://github.com/Roboparty/Party_OS 公布 Party OS 路线图，将动作数据生成、人体到人形机器人的动作重定向、MimicLite 模仿学习、UFO 无监督学习，以及未来的交互与 VLA 层串联起来，是值得持续关注的新开源人形控制基础设施来源。

### RoCoCo Lab
- 机构：罗马第一大学（Sapienza University of Rome）
- 主页：https://lab-rococo-sapienza.github.io/learning-to-dribble/
- GitHub：https://github.com/Lab-RoCoCo-Sapienza
- 实验室 / 院系：RoCoCo Lab，计算机、控制与管理工程系
- 关键主题：人形机器人 / 机器人足球 / 强化学习 / 视觉控制 / 移动操作
- 备注：实验室的新时序深度带球项目将感知直接接入人形控制策略，并把主动移动对手下的鲁棒控制和 Booster T1 仿真到现实迁移列为主要下一步。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### LAAS-CNRS Gepetto 团队 — 人形机器人博士
- 类型：博士
- 地点：法国图卢兹
- 来源：官方页面 — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止时间：2026-07-31 23:59
- 主题：人形机器人 / 腿足运动 / 强化学习 / MPC / 全身控制 / 安全控制
- 状态：招聘中
- 备注：36 个月博士职位，计划于 2026 年 10 月 1 日开始，由 LAAS-CNRS 的 Olivier Stasse 指导，并由 CNRS-AIST JRL 的 Mehdi Benallegue 联合指导。项目让强化学习负责离散的接触、落脚点、步态和行为转换决策，由在线参数化 MPC 强制满足物理约束并生成连续全身运动，计划在 PAL Robotics Kangaroo 和/或 Unitree 人形机器人上验证。

</details>
