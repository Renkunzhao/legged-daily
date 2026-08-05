[English](../../drafts/legged-daily-2026-08-05.md) | **中文**
# Legged Daily - 2026-08-05

## 摘要
- 3 篇新论文达到收录门槛，主题集中在人形动作学习与接触丰富控制：动力学可行的接触隐式动作重定向、上下文感知动作先验，以及从无序姿态训练的可复用流匹配先验。
- Shooting for Contact 是今天最强的系统工作：其直接仿真多重打靶方法在优化内部处理接触，并支持 Unitree G1 零样本爬行和 180 度跳转，同时展示了向四足机器人的形态迁移。
- CMP 与 PFM-HR 分别补足动作先验学习的不同短板：CMP 无需人工标签即可选择与任务相关的动作监督，PFM-HR 则从无序姿态集合中提取可复用的状态转移引导。
- 今天没有仓库达到实现质量门槛。CMP 表示后续将公开代码，另外两篇入选论文尚未核验到官方公开实现；低信号或主题不相关的新建仓库未收录。
- Caltech AMBER Lab 通过 Shooting for Contact 再次提供高信号 G1 真机控制更新。此前跟踪的 Amazon Robotics Compass 安全运动岗位在官方招聘页仍有效，继续等待确认是否加入 master list。

<details>
<summary><strong>新论文</strong></summary>

### Shooting for Contact: Contact-Implicit Multiple Shooting for Dynamic Motion Retargeting
- 链接: https://arxiv.org/abs/2608.03116
- 来源: arXiv
- 日期: 2026-08-04
- 作者: Sergio A. Esteban, Jason H. K. Siu, Derrick Mach, Junheng Li, Vince Kurtz, Joel W. Burdick, Aaron D. Ames
- 主题: 人形控制 / 动作重定向 / 接触隐式优化 / 可微仿真 / 动作模仿强化学习 / sim-to-real
- 摘要: 该方法将可微仿真器嵌入直接仿真多重打靶优化，在无需预先指定接触模式的情况下把运动学参考转化为动力学可行的全身轨迹，再用优化后的动作加速模仿策略训练并实现 Unitree G1 零样本部署。
- 备注: 官方项目页展示了手、肘、膝和脚多部位接触的指令条件爬行、真机 180 度跳转，以及向四足跳转动作的形态迁移。接触、摩擦、冲击、自碰撞、关节限位和驱动约束均由仿真器内部处理；性能结果仍属于作者报告的预印本结论。

### Learning Context-Aware Motion Priors for Humanoid Control
- 链接: https://arxiv.org/abs/2608.03234
- 来源: arXiv
- 日期: 2026-08-04
- 作者: Yunyang Mo, Yi Gu, Yangchen Zhou, Hanyang Cao, Renjing Xu
- 主题: 人形控制 / 动作先验 / 强化学习 / 模仿学习 / 上下文适配 / 样本效率
- 摘要: 上下文感知动作先验从高优势策略 rollout 中学习任务与动作的相关性，据此把通用动作先验适配到当前任务，无需人工技能标签、数据集切分或独立的技能发现阶段。
- 备注: 作者分别结合对抗式动作先验和分数匹配动作先验实现该方法，并报告其在 5 个人形控制任务中持续改善任务性能与样本效率，对动作数据分布不均衡也保持稳健。论文表示代码将公开，但今天尚未核验到官方仓库。

### Pose Flow Matching for Humanoid Robots
- 链接: https://arxiv.org/abs/2608.03227
- 来源: arXiv
- 日期: 2026-08-04
- 作者: Yukang Gao, Yi Gu, Yangchen Zhou, Xingyu Chen, Zhaorui Wang, Fanghai Zhang, Hanyang Cao, Zhengyang Shen, Ji Ma, Runhan Zhang, Lei Han, Renjing Xu
- 主题: 人形动作跟踪 / 流匹配 / 动作先验 / 强化学习 / 姿态几何 / 高动态动作
- 摘要: PFM-HR 直接从大规模无序姿态数据训练冻结且可复用的流匹配先验，再以姿态几何分数奖励与人类姿态局部变化几何一致的策略状态转移。
- 备注: 与时间序列先验相比，该方法不需要有序动作片段；与传统姿态先验相比，它显式引导策略产生的姿态转移。作者报告其可改善单动作和通用动作跟踪，尤其对高动态动作更明显；今天尚未核验到官方公开代码仓库。

</details>

<details>
<summary><strong>新仓库</strong></summary>

今天没有新仓库同时达到实现质量与主题相关性门槛。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Caltech AMBER Lab / Aaron D. Ames 及合作者
- 机构: California Institute of Technology；与 DePaul University 合作
- 主页: http://www.bipedalrobotics.com/
- arXiv: https://arxiv.org/abs/2608.03116
- 关键主题: 人形控制 / 接触隐式优化 / 动作重定向 / 强化学习 / sim-to-real / 腿足运动
- 备注: Shooting for Contact 是已跟踪 AMBER 来源网络的新更新。其官方项目页（https://shooting-for-contact.github.io/）展示 Unitree G1 零样本爬行与跳转真机部署，并包含四足迁移示例，进一步强化该实验室在动力学感知人形控制和物理验证方面的持续信号。本条应视为现有实验室条目的更新，而不是新增实验室。
- 学生及代表工作:
  - [Sergio A. Esteban](https://arxiv.org/search/cs?searchtype=author&query=Esteban%2C+S+A) — [Shooting for Contact](https://arxiv.org/abs/2608.03116)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Amazon Robotics Compass — Senior Applied Scientist, Safe Locomotion
- 类型: Senior Applied Scientist
- 地点: 美国加利福尼亚州帕萨迪纳
- 来源: 官方招聘页 — https://www.amazon.jobs/en/jobs/10454065/senior-applied-scientist-safe-locomotion-compass
- 截止时间: rolling / 未知
- 主题: 安全腿足运动 / 强化学习 / 控制屏障函数 / 全身控制 / sim-to-real / 四足机器人 / 人形机器人 / 真机部署
- 状态: 2026-08-05 复核仍有效；已于 2026-07-27 提议，继续等待确认是否加入 master list
- 备注: 该岗位负责在真实四足和人形平台上开发步行、跑步、爬楼和跌倒恢复学习控制器，明确结合强化学习、sim-to-real、形式化安全机制与基于模型的全身控制，并要求进行严格的仿真、硬件和失效模式评估。

</details>
