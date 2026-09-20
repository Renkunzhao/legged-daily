[English](../../drafts/legged-daily-2026-09-20.md) | **中文**
# Legged Daily - 2026-09-20

## 摘要
- RoM-Nav 将约化阶动力学上学到的导航知识迁移到完整 Unitree G1 策略，并加入 Poisson 安全滤波器；实机展示了无地图多楼层导航，路径超过 100 米、垂直位移超过 10 米。
- ViLoMan 将不完整的人—物交互示范转换为可执行全身轨迹，再蒸馏出仅依赖机载深度与本体感知的单一 G1 自主关门策略。
- 一项面向建筑施工的场景落地方法把屋面工动作与度量屋顶几何对齐，并报告了 G1 上坡行走、钉枪、锤击和弯腰动作的实机执行。
- LP-NavOA 发布了较完整的 MuJoCo/mjlab 研究分支，用于短距感知条件下无需外部规划器的 G1 局部导航；WholeBodyWAM 的新仓库则是项目与演示网站，而非模型训练代码。
- 今日未核验到新的高置信度腿足机器人招聘；已过期的 LAAS-CNRS 安全强化学习博士职位仍等待确认删除。

<details>
<summary><strong>新论文</strong></summary>

### Learning Safe Humanoid Navigation from Reduced Order Models
- Link: https://arxiv.org/abs/2609.19272
- Source: arXiv；正在投稿 ICRA 2027
- Date: 2026-09-16
- Authors: William D. Compton, Zachary Olkin, Ryan Bena, Aaron D. Ames
- Topics: 人形机器人导航 / 约化阶模型 / 强化学习 / 安全滤波 / 多楼层自主移动
- Summary: RoM-Nav 先在约化阶动力学上学习基于 LiDAR 的导航，再将知识迁移到带冻结运动控制器的完整 Unitree G1 策略，并用 Poisson 安全滤波器处理分布外障碍物。
- Notes: 作者展示了路径长度超过 100 米、垂直位移超过 10 米的无地图多楼层实机试验。项目页提供硬件视频，但本次未发现官方训练代码仓库；结果未经独立复现。

### ViLoMan: Learning Visual-Proprioceptive Whole-Body Loco-Manipulation Skills for Humanoid Robots
- Link: https://arxiv.org/abs/2609.19340
- Source: arXiv
- Date: 2026-09-16
- Authors: Zejie Tian, Ruibing Hou, Bingpeng Ma, Börje F. Karlsson, Shiguang Shan
- Topics: 人形移动操作 / 第一视角深度 / 教师—学生蒸馏 / 动作重定向 / 仿真到现实
- Summary: ViLoMan 将部分运动学人—物示范转换为物理可执行的机器人轨迹，再蒸馏为一个部署时只使用机载深度和本体感知、直接输出关节级全身动作的策略。
- Notes: 论文在不同门配置和机器人初始状态下，于仿真和 Unitree G1 实机评估自主关门。补充项目页公开了详细训练、奖励信息和视频，但今日未发现公开的策略训练仓库。

### Learning Slope-Adaptive Whole-Body Locomotion for Humanoid Robots in Roofing Construction
- Link: https://arxiv.org/abs/2609.20558
- Source: arXiv
- Date: 2026-09-17
- Authors: Songyang Liu, Shuai Li
- Topics: 人形建筑施工 / 坡面自适应运动 / 场景落地动作重定向 / 强化学习 / 全身控制
- Summary: 使用轨迹级优化，将重定向的屋面工示范与度量屋顶模型对齐，再训练执行感知策略，使机器人在跟踪误差下保持支撑接触、作业关系、间隙与非穿透约束。
- Notes: 作者报告钉枪、锤击和侧向推动任务均取得 3/3 次成功，作业间隙误差为 0.256–0.531 厘米；G1 实机动作的基座坐标系平均运动误差低于 80 毫米。本次未发现官方代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### shenqiqishi/LP-NavOA-code
- Link: https://github.com/shenqiqishi/LP-NavOA-code
- Category: 强化学习 / 导航 / 避障 / 工具包
- Robot Type: 人形 / Unitree G1
- Simulator: MuJoCo / mjlab
- Deploy: 仿真训练与基准评测 / ONNX 策略导出 / 相关硬件演示
- Summary: mjlab 的研究分支，实现感知—动作 PPO 运动骨干与仅改写航向命令的循环局部规划器，使 G1 仅凭本体感知、短距测距和机体坐标系目标方向完成无外部规划器的局部导航。
- Notes: Apache-2.0 仓库记录了 7 个任务、三阶段运动课程、开放墙体与室内规划器蒸馏、评测脚本、消融实验、测试和 ONNX 导出。仓库创建于 2026-09-19；关联项目页有实机绕障视频，但公开 README 未提供完整硬件部署流程。

### zbzyjya/WholeBodyWAM
- Link: https://github.com/zbzyjya/WholeBodyWAM
- Category: 可视化 / 项目页
- Robot Type: 人形 / 天工 3.0
- Simulator: 无
- Deploy: 浏览器 / 硬件演示
- Summary: Apache-2.0 项目网站仓库，展示采用动作预训练的 Video-Motion-Action 模型，以及天工 3.0 的实机全身操作与移动操作演示。
- Notes: 网站介绍了来自异构来源、总时长超过 4,100 小时的 UniMotion-4K 动作语料，并报告六项实机任务的平均归一化得分为 72.2%。该仓库托管项目页和媒体，不包含模型训练代码、检查点或动作语料；最近更新于 2026-09-17。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Aaron D. Ames / AMBER Lab — RoM-Nav 合作
- Institution: 加州理工学院
- Homepage: https://www.ames.caltech.edu/
- arXiv: https://arxiv.org/abs/2609.19272
- GitHub: https://github.com/wdc3iii
- Lab / Department: AMBER Lab / Mechanical and Civil Engineering and Control and Dynamical Systems
- Key Topics: 人形运动 / 自主导航 / 安全关键控制 / 强化学习 / 约化阶模型
- Notes: William D. Compton、Zachary Olkin、Ryan Bena 与 Aaron D. Ames 将该团队的运动和安全控制研究推进到长时程、无地图、多楼层 G1 导航。约化阶到完整阶的知识迁移与输出安全滤波，使这一合作成为可扩展安全人形自主系统的高价值来源网络。
- Students and Representative Works:
  - [William D. Compton](https://github.com/wdc3iii) — [RoM-Nav](https://wdc3iii.github.io/rom-nav/)

### 北京人形机器人创新中心 — WholeBodyWAM 合作
- Institution: 北京人形机器人创新中心 / 南开大学 / 北京理工大学 / 清华大学
- Homepage: https://zbzyjya.github.io/WholeBodyWAM/
- arXiv: https://arxiv.org/abs/2609.18197
- GitHub: https://github.com/zbzyjya/WholeBodyWAM
- Key Topics: 人形世界—动作模型 / 动作预训练 / 移动操作 / 全身控制 / 天工
- Notes: Bowei Zhang、Qiyao Zhang、Shuanghao Bai、Xinhua Wang、Meng Li 等将异构人类与人形动作预训练连接到天工 3.0 实机控制。该工作不同于 2026-09-16 已追踪的控制器落地版 WholeBodyWAM；后续检索需谨慎处理两个项目重名问题。
- Students and Representative Works:
  - [Bowei Zhang](https://arxiv.org/abs/2609.18197) — [Learning Whole-Body World Action Models with Scalable Motion Priors](https://zbzyjya.github.io/WholeBodyWAM/)

### Correll Lab — Unitree G1 与 Dex3-1 平台信号
- Institution: 圣母大学
- Homepage: https://correlllab.github.io/
- GitHub: https://github.com/correlllab/leprechaun_g1
- Lab / Department: Correll Lab
- Key Topics: 人形硬件 / 灵巧操作 / Unitree G1 / 机器人学习
- Notes: 该实验室于 2026-09-18 新建了一个 MIT 许可的公开硬件参考仓库，记录其 Unitree G1 与 Dex3-1 灵巧手平台。目前仓库只是最小化的平台标记而非软件发布，但可作为圣母大学后续人形机器人工作的早期观察信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 本期无新核验职位
- Type: 博士 / RA / 实习 / 研究工程师 / 博士后
- Source: 官方来源复核
- Deadline: 未知
- Topics: 人形 / 四足 / 运动控制 / 机器人学习
- Status: 持续观察
- Notes: 本次未发现官方信息足够完整、可高置信核验的新腿足机器人机会。现有 active/watching 条目保持不变，等待正常复核周期。

### 拟删除 / 过期条目 — LAAS-CNRS Gepetto Team，人形机器人安全强化学习博士
- Current Status: 已过期 / 不再可申请
- Reason: 申请截止日期为 2026-07-31，CNRS 官方页面已注明该职位不再开放。该删除建议仍等待确认。
- Source Checked: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
