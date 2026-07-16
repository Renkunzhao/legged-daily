[English](../../drafts/legged-daily-2026-07-16.md) | **中文**
# 腿足机器人日报 - 2026-07-16

## 摘要
- APT-RL 把轨迹优化预训练、Transformer 潜在技能、强化学习和机载感知蒸馏结合起来，在 KAIST HOUND 上用单一策略实现按地形自主选择步态的高速户外穿越。
- EgoHTR 发布场景对齐的 4D 人类复杂地形穿越数据集与重建流程，并在 Unitree G1 上展示基于重建参考动作的硬件部署。
- 今日没有仓库达到可复现性与成熟度门槛：两个最强项目均有项目页，但 APT-RL 未提供公开代码链接，EgoHTR 当前公开仓库主要是项目网站而非论文所述重建流程或数据发布。
- 今日未新增经过核验的招聘机会；已追踪的 LAAS-CNRS 人形机器人博士职位仍在开放，截止日期为 7 月 31 日。

<details>
<summary><strong>新论文</strong></summary>

### Agile perceptive multi-skill locomotion for quadrupedal robots in the wild
- 链接: https://arxiv.org/abs/2607.13579
- 来源: Science Robotics / arXiv
- 日期: 2026-07-15
- 作者: Jun-Gill Kang, Jaehyun Park, Tae-Gyu Song, Joon-Ha Kim, Seungwoo Hong, Hae-Won Park
- 主题: 四足机器人 / 感知运动 / 强化学习 / 步态切换 / sim-to-real
- 摘要: APT-RL 先用 18 万条轨迹优化样本预训练基于 Transformer 的潜在运动技能，再通过强化学习适配复杂地形并蒸馏感知模块，最终得到一个可在楼梯、障碍杆、踏脚石、沟隙、林地倒木等场景中自主选择和切换步态的机载策略。
- 备注: 论文于 2026-07-15 发表于 Science Robotics。项目报告机器人跨越 60 cm 台阶时达到 4.25 m/s、下落穿越三级台阶时瞬时峰值达到 6 m/s，并仅依赖机载感知与计算完成 1.1 km 城市场景和 0.34 km 林地路线。项目页: https://skillquadsr.github.io/。核验时未看到公开代码链接。

### EgoHTR: Egocentric 4D Demonstrations of Human Terrain Traversal
- 链接: https://arxiv.org/abs/2607.13472
- 来源: arXiv
- 日期: 2026-07-15
- 作者: Alex Brandes, Haig Conti Georges Sajelian, Manthan Patel, Dominik Hollidt, Chenhao Li, Matthias Heyrman, Oliver Hausdoerfer, Manuel Kaufmann, Xi Wang, Jonas Frey, Angela P. Schoellig, Christian Holz, Marc Pollefeys, Marco Hutter
- 主题: 人形机器人 / 地形穿越 / 人体动作数据集 / 4D 重建 / 模仿学习
- 摘要: EgoHTR 提出场景对齐的第一视角重建流程与数据集，包含 55 段人类复杂地形穿越序列和超过 15 万帧数据，把具有环境上下文的人体动作采集连接到感知运动策略，并在 Unitree G1 上部署重建参考动作。
- 备注: 项目页: https://egohtr.github.io/。论文称重建流程已开源且支持社区扩展，但今日检查到的公开项目站仓库主要暴露网站资源，尚未看到单独、文档完整的代码或数据发布；建议后续复查发布状态。

</details>

<details>
<summary><strong>新仓库</strong></summary>

今日未选入新仓库。新发现的候选项目仅提供报告、仅包含网站文件，或完整度不足以形成可信的复现路径，因此不凑数收录。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Hae-Won Park / Dynamic Robot Control and Design Lab
- 机构: KAIST
- 主页: https://skillquadsr.github.io/
- Google Scholar: https://scholar.google.com/citations?user=q7v_ewQAAAAJ&hl=en
- 实验室 / 系: 机械工程系
- 关键主题: 四足机器人 / 动态运动 / 感知控制 / 强化学习 / 机器人设计
- 备注: APT-RL 为该团队在自研 KAIST HOUND 平台上的高速、多技能、地形条件运动增加了很强的系统信号，覆盖机载感知、抗振传感器集成以及公里级户外实验。
- 学生与代表工作:
  - [Jun-Gill Kang](https://jgkang1210.github.io) — [Agile perceptive multi-skill locomotion for quadrupedal robots in the wild](https://skillquadsr.github.io/)

### Marco Hutter / Robotic Systems Lab
- 机构: ETH Zurich
- 主页: https://rsl.ethz.ch/
- 实验室 / 系: Robotic Systems Lab，机械与过程工程系
- 关键主题: 四足机器人 / 人形机器人 / 地形穿越 / 感知 / 机器人学习
- 备注: EgoHTR 把该实验室的地形运动研究推进到场景对齐的人体示范数据：结合第一视角穿戴传感器和便携式 3D 扫描，评测动作重建精度，并在 Unitree G1 硬件上部署重建参考动作。
- 学生与代表工作:
  - [Alex Brandes](https://arxiv.org/search/cs?searchtype=author&query=Brandes%2C+A) — [EgoHTR](https://egohtr.github.io/)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### LAAS-CNRS Gepetto Team — 人形机器人博士职位
- 类型: PhD
- 地点: 法国图卢兹
- 来源: 官方网站 — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- 截止时间: 2026-07-31 23:59
- 主题: 人形机器人 / 腿足运动 / 强化学习 / MPC / 全身控制 / 安全控制
- 状态: active
- 备注: 2026-07-16 复查时官方职位页仍可访问，截止日期仍为 7 月 31 日。该 36 个月项目用学习策略负责离散接触与步态决策，用在线 MPC 生成满足动力学约束的连续全身动作，计划在 PAL Robotics Kangaroo 和/或 Unitree 人形机器人上验证。

</details>
