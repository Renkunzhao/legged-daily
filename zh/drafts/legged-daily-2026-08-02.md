[English](../../drafts/legged-daily-2026-08-02.md) | **中文**
# 腿足机器人日报 - 2026-08-02

## 摘要
- 2026-08-01 日报之后，没有新论文达到腿足机器人收录标准。arXiv `cs.RO` feed 于 2026-08-02 刷新时，最新条目仍是上一期已覆盖、提交于 2026-07-30 的 PAC-MAN。
- 两个仓库达到实现质量门槛：Yanshi RL Lab 为三种人形机器人提供 robot profile 抽象和确定性的 Isaac Lab→MuJoCo 验收门；`quadruped-gait` 则在 MPC、全身控制和学习策略部署路径上出现实质更新。
- 今天没有从第一方来源核验到新的实验室或教授动态；仅凭仓库作者信息不足以新增机构来源网络条目。
- 没有新职位达到“新增信号”标准。ETH Zurich RSL 官方页面仍在滚动招聘腿足机器人方向的博士、博士后、研究/软件、机器人设计、嵌入式和电子工程岗位；已过期的 LAAS-CNRS 安全强化学习人形机器人博士职位继续列为待确认删除项。

<details>
<summary><strong>新论文</strong></summary>

今天没有达到收录标准的新论文。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### jeffliulab/yanshi-rl-lab
- 链接：https://github.com/jeffliulab/yanshi-rl-lab
- 类别：强化学习 / 多机器人基准 / sim-to-sim 验证 / 可复现性
- 机器人类型：人形机器人；Unitree G1、智元灵犀 X2、Berkeley Humanoid Lite
- 仿真器：NVIDIA Isaac Lab 2.3.2 用于训练；MuJoCo 用于确定性回放和验收门测试
- 部署：仅仿真和 sim-to-sim；未展示真机部署
- 摘要：一个新发布的 MIT 许可框架，将每种人形机器人表示为厂商 profile，在 Isaac Lab 中训练运动策略，导出 ONNX，并要求策略通过声明式 MuJoCo 验收门后才视为有效结果。
- 备注：仓库包含无需 GPU 的 profile、契约和验收门测试，固定版本的外部机器人资产引用、崎岖地形任务脚手架，以及三种结构差异明显的人形机器人的初始单随机种子基准。其最有价值的贡献不是新控制器，而是方法论：跨物理引擎回放和 YAML 阈值让可迁移性失败及评测标准变化都能被明确审计。维护者明确将多随机种子基准列为后续工作。

### takarakasai/quadruped-gait
- 链接：https://github.com/takarakasai/quadruped-gait
- 类别：模型控制 / 步态生成 / MPC / 全身控制 / 状态估计 / Rust 机器人软件
- 机器人类型：四足机器人；定位为可复用运动栈，并由作者的 Articara / Go2 工具链调用
- 仿真器：核心库与仿真器解耦；MuJoCo 行走回归测试位于关联的 `articara` 仓库
- 部署：包含策略运行时部署路径，但今天未核验到新的真机结果
- 摘要：一个 Apache-2.0 的 Rust 四足运动栈，组合 CHAMP 风格步态生成、SRBD/质心/完整质心 MPC、分层全身控制和腿足状态估计，并在 2026-08-02 出现实质性的控制与部署更新。
- 备注：今天的提交新增学习型 Bound 策略部署路径，修正 MPC 中偏航落脚力矩臂和预测时域内相位投影，并为指令支撑足加入可选最小法向力约束。仓库提供 CI 和覆盖率信号，而行为级 MuJoCo 回归测试按设计保留在下游调用仓库中。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今天没有从第一方来源核验到新的实验室或教授信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### ETH Zurich Robotic Systems Lab — 滚动研究与工程岗位
- 类型：博士 / 博士后 / 研究人员或软件工程师 / 机器人设计工程师 / 嵌入式系统工程师 / 电子工程师
- 地点：瑞士苏黎世
- 来源：官方网站 — https://rsl.ethz.ch/the-lab/open-positions.html
- 截止时间：滚动招聘 / 官方页面未注明统一截止日期
- 主题：腿足机器人 / 移动操作 / 运动规划 / 模型预测控制 / 强化学习 / 感知 / 导航 / 执行器 / 遥操作 / 嵌入式系统
- 状态：核验时仍有效；属于已跟踪机会，不是新的主列表候选
- 备注：官方页面仍提供申请链接，并列出覆盖研究与机器人系统工程的多个岗位。本次属于状态复核，而不是新职位发布。

### 拟删除 / 过期条目 — LAAS-CNRS Gepetto Team 人形机器人安全强化学习博士职位
- 当前状态：已过期 / 已超过所列申请截止时间
- 原因：官方招聘信息列出的 2026-07-31 23:59 截止时间已经过去。在正式确认删除对应 active 主列表条目前，继续保留该拟删除提示。
- 已检查来源：https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
