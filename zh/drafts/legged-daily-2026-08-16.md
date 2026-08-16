[English](../../drafts/legged-daily-2026-08-16.md) | **中文**
# 腿足机器人日报 - 2026-08-16

## 摘要
- 今日未选入新的高信号腿足机器人论文。运行时相关 arXiv 监测源的最新记录仍停留在 8 月 13 日，符合周末投稿更新间隔。
- `RIMKit` 是今天最强的仓库信号：韩国高丽大学 Robot Intelligence Lab 发布的工具包，通过统一的接触感知 MuJoCo 流水线，将 SOMA 人体动作重定向到 11 种人形机器人平台。
- `atec_locomotion_checkpoint` 保存了 Unitree B2 搭载 Piper 机械臂的 Isaac Lab 粗糙地形运动训练谱系，包含检查点、导出模型、解析后的配置、来源哈希和验证脚本。
- 高丽大学 Robot Intelligence Lab 值得作为新的来源网络候选，重点覆盖人形/四足运动生成、动作重定向、机器人基础模型、人机交互和灵巧操作。
- NVIDIA Isaac Loco-Manipulation 团队在上海开放 2026 机器学习实习，方向包括人形移动操作、GR00T/Cosmos、Isaac Lab/Newton 工作流、仿真到现实迁移和真机验证。

<details>
<summary><strong>新论文</strong></summary>

今日未选入新论文。运行时，重点机器人 arXiv 监测源中没有晚于 2026-08-13 的腿足专项记录；更广泛的检索也未发现同时满足近期性、相关性和来源核验标准的论文。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### RIMKit
- 链接：https://github.com/tmjeong1103/RIMKit
- 类别：动作重定向 / 工具包 / 可视化
- 机器人类型：人形 — Unitree G1/H1/H2/R1、ROBOTIS K1、Apptronik Apollo、LimX Oli、Fourier N1、PNDbotics ADAM Lite、Booster T1、ENGINEAI PM01
- 仿真器：MuJoCo
- 部署：仿真 / 浏览器 / 数据
- 摘要：统一的动作重定向工具包，可将 Kimodo 或 GEM-X 的 SOMA 人体动作转换为 11 种人形机器人的接触感知全身动作，并提供 CLI、Python、浏览器演示、安全 NPZ 导出和渲染预览。
- 备注：创建于 2026-08-10，并持续更新至 2026-08-16；由高丽大学 Robot Intelligence Lab 开发。当前 CoRe 流水线包含碰撞细化与落地约束、带 Python 回退的 C++ 编译后端，以及 16 个示例动作；源码采用 Apache-2.0。生成动作在上真机前应先在仿真中验证。

### atec_locomotion_checkpoint
- 链接：https://github.com/JizhuoChen/atec_locomotion_checkpoint
- 类别：强化学习 / 控制 / 可复现快照
- 机器人类型：四足移动操作 — Unitree B2 + AgileX Piper
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真 / 数据
- 摘要：为 B2-Piper 平台保存的粗糙地形运动训练框架与检查点谱系，覆盖平地鲁棒预训练、航向感知粗糙地形迁移和细粒度全状态续训。
- 备注：创建于 2026-08-15，并于 2026-08-16 更新。仓库提供精确检查点哈希、TorchScript/ONNX 导出、解析后的 YAML 配置、TensorBoard 事件、来源清单、地形资产、验证工具，以及使用 2,048 个环境的 PPO 重启脚本。维护者明确说明，由于未保存全部仿真器与 GPU 随机数状态，随机续训不应被期待复现字节完全一致的最终权重。MIT 许可。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Robot Intelligence Lab — Sungjoon Choi、Kyungjae Lee
- 机构：高丽大学
- 主页：https://sites.google.com/view/sungjoon-choi/home
- GitHub：https://github.com/sjchoi86
- 实验室 / 院系：Robot Intelligence Lab；人工智能系、统计学系
- 关键主题：人形 / 四足 / 运动生成 / 动作重定向 / 机器人基础模型 / 人机交互 / 灵巧操作
- 备注：拟新增到来源网络。实验室官网明确列出人形与四足自然运动生成、社会与物理交互型陪伴机器人，以及灵巧机器人手等方向。今天新发现的 RIMKit 为其多平台人形动作重定向提供了具体且持续维护的信号。
- 学生与代表作：
  - [Taemoon Jeong](https://taemoon.notion.site/taemoon-page) — [RIMKit](https://github.com/tmjeong1103/RIMKit)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### NVIDIA — Isaac Loco-Manipulation 团队
- 类型：机器学习实习 — 人形机器人，2026
- 地点：中国上海
- 来源：官方招聘页 — https://jobs.nvidia.com/careers/job/893395444508
- 截止时间：未知
- 主题：人形移动操作 / 移动操作 / GR00T / Cosmos / Isaac Lab / Newton / 强化学习 / 模仿学习 / 仿真到现实 / 全身控制
- 状态：开放
- 备注：拟新增机会。岗位面向在读硕士或博士，覆盖从仿真与合成数据工作流、算法设计到 sim-to-real 和真机验证的完整链路。加分项包括人形机器人经验、真机测试、C++/Python、PyTorch/JAX/TensorFlow、Isaac Sim/Lab 或 MuJoCo、机器人基础模型、3D 感知，以及双手灵巧操作或全身控制研究。官方页面当前可访问，但未显示明确截止日期。

今日未发现拟删除的过期条目。

</details>
