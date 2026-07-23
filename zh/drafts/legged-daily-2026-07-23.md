[English](../../drafts/legged-daily-2026-07-23.md) | **中文**
# 腿足机器人日报 - 2026-07-23

## 摘要
- YAHMP 围绕 Unitree G1 通用动作跟踪提供了受控实证研究与 Apache-2.0 模块化栈，区分了真正改善跟踪效果的设计选择，以及主要影响能耗、复杂度或交互能力的选择。
- Extreme-RGMT 用持续学习处理通才与专才能力之间的冲突：保留已掌握动作，同时把训练集中到稀有、困难的高动态片段；项目展示了 Unitree G1 高动态动作及在线惯性动捕跟踪。
- PGTT 的新版 arXiv 论文已标注被 IROS 2026 接收，并进一步支持形态无关的感知运动路线：通过奖励塑形而非振荡器或 IK 动作先验引入相位结构，完成 Go2 实机验证及初步 ANYmal-C 迁移。
- 两个官方代码库值得新增：YAHMP 用于 MuJoCo/MJLab 人形动作跟踪实验；PGTT 覆盖 MJX 训练、地形生成、评估、感知与有文档的 Go2 实机部署。
- Extreme-RGMT 的作者网络形成了北京理工大学与 Humanoid Robotics (Shanghai) / OpenLoong 团队之间的新信号，将学术控制研究与实体人形平台团队连接起来。

<details>
<summary><strong>新论文</strong></summary>

### 人形机器人通用动作跟踪中，什么真正重要？一项实证研究
- 链接：https://arxiv.org/abs/2607.19903
- 来源：arXiv
- 日期：2026-07-22
- 作者：Fabio Amadio, Enrico Mingo Hoffman
- 主题：人形机器人 / 全身动作跟踪 / 模仿学习 / 仿真到现实 / Unitree G1
- 摘要：一项受控实证研究，在开源 YAHMP 框架中比较动作指令表示、观测历史、动作表示、执行器配置、手部受力随机化和训练方法等通用人形动作跟踪设计因素。
- 备注：作者在同一重定向动作集上与 TWIST2 基线比较，并将策略零样本部署到真实 Unitree G1，展示多样动作跟踪、受扰恢复和用力交互。

### Extreme-RGMT：面向稳健通用人形控制的高动态技能持续学习
- 链接：https://arxiv.org/abs/2607.20110
- 来源：arXiv
- 日期：2026-07-22
- 作者：Yubiao Ma, Han Yu, Kai Guo, Changtai Lv, Zhengquan Mao, Boyang Xing, Xuemei Ren, Dongdong Zheng
- 主题：人形机器人 / 全身动作跟踪 / 持续学习 / 高动态技能 / 遥操作
- 摘要：一个两阶段框架，先训练通用动作跟踪策略，再在约束已掌握动作策略漂移的同时学习困难高动态技能。
- 备注：方法结合难度感知采样与优势优先轨迹重采样，聚焦稀疏的关键动作片段；论文及项目页展示 Unitree G1 侧空翻、后空翻、鲤鱼打挺等动作，以及基于惯性动捕的在线跟踪。本次未核验到训练代码。

### PGTT：用于感知型腿足运动的相位引导地形穿越
- 链接：https://arxiv.org/abs/2510.18348
- 来源：arXiv / IROS 2026
- 日期：2026-07-22
- 作者：Alexandros Ntagkas, Chairi Kiourt, Konstantinos Chatzilygeroudis
- 主题：四足机器人 / 感知运动 / 强化学习 / 地形适应 / 仿真到现实
- 摘要：一种感知深度强化学习运动方法，通过基于样条的奖励塑形编码各腿相位，同时保留直接关节空间动作，降低对形态特定振荡器或 IK 动作先验的依赖。
- 备注：这是 2025 年预印本的 v2 更新，现已标注被 IROS 2026 接收。论文报告其在受推扰动和离散障碍上的成功率优于所比较基线，并以 LiDAR 高程图管线完成 Unitree Go2 实机验证，还用相同超参数进行了初步 ANYmal-C 迁移。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### YAHMP
- 链接：https://github.com/fabio-amadio/yahmp
- 类别：强化学习 / 动作跟踪 / 评估 / 工具包
- 机器人类型：人形机器人 — Unitree G1
- 仿真器：MuJoCo / MJLab
- 部署：仿真与有文档的实机部署
- 摘要：一个采用 Apache-2.0 许可证的模块化框架，用于训练、评估、导出和部署 Unitree G1 通用动作跟踪策略，支持重定向 AMASS/OMOMO 数据及配套 ONNX 策略运行路径。
- 备注：仓库包含基础版、未来参考编码版和教师—学生版，以及数据转换、评估、ONNX 导出和部署工具；核验时为 13 stars。论文报告零样本真实 G1 部署，但本次未复现训练或实机结果。

### phase_guided_terrain_traversal
- 链接：https://github.com/NtagkasAlex/phase_guided_terrain_traversal
- 类别：强化学习 / 控制 / 感知 / 地形生成
- 机器人类型：四足机器人 — Unitree Go2 / ANYmal
- 仿真器：MuJoCo MJX
- 部署：仿真与 Unitree Go2 实机
- 摘要：PGTT 官方实现，覆盖程序化地形生成、JAX/MJX 训练、多轮评估、策略检查点、LiDAR 高程映射感知栈和基于 Unitree SDK 的硬件部署。
- 备注：共享的机器人无关模块支持 Go2 与 ANYmal 配置；实机文档路径使用 Unitree L1 LiDAR、Point-LIO、高程映射和 `unitree_sdk2py`。核验时为 66 stars，GitHub 元数据中未显示明确许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 郑冬冬 / Humanoid Robotics (Shanghai) — Extreme-RGMT 合作网络
- 机构：北京理工大学 / Humanoid Robotics (Shanghai) Co., Ltd.
- 主页：https://zeonsunlightyu.github.io/Extreme-RGMT.github.io/
- arXiv：https://arxiv.org/abs/2607.20110
- 实验室 / 院系：北京理工大学自动化学院；Humanoid Robotics (Shanghai) / OpenLoong 团队
- 关键主题：人形机器人 / 全身控制 / 动作跟踪 / 持续学习 / 遥操作
- 备注：Extreme-RGMT 是一条连接北京理工大学、Humanoid Robotics (Shanghai) 与山东大学的新合作信号，尤其适合跟踪通用学习控制、稀有高动态技能、在线惯性动捕输入和 Unitree G1 实体实验的结合。
- 学生与代表工作：
  - [马宇彪](https://arxiv.org/search/cs?searchtype=author&query=Ma,+Y) — [Extreme-RGMT](https://arxiv.org/abs/2607.20110)
  - [俞涵](https://zeonsunlightyu.github.io/Extreme-RGMT.github.io/) — [Extreme-RGMT](https://arxiv.org/abs/2607.20110)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

自上一轮运行后未发现新的高置信招聘或机会信号。此前已跟踪的滚动岗位，包括 `jobs.md` 中已有的 ETH Zurich RSL 与 EPFL BioRob 条目，今天不重复作为新增项收录。

</details>
