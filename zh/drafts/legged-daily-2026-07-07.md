[English](../../drafts/legged-daily-2026-07-07.md) | **中文**
# 腿足机器人日报 - 2026-07-07

## 摘要
- 今天 arXiv 上明确属于腿足机器人方向的新条目不多；最强论文信号是 X-Morph：把人类运动先验迁移到四足、六足和带机械臂四足等不同构型。
- MPX 是高信号 JAX MPC / 轨迹优化工具栈，面向腿足机器人，并给出 Talos、H1、Aliengo、Go2 等示例。
- Teleopit 值得跟踪：它围绕 Unitree G1 做全身遥操作，覆盖 BVH / Pico 4 重定向、MuJoCo 仿真、sim-to-real 和 HDF5 数据记录。
- NJU-RLC 的 quadrupedal-agility 把 2025 论文和 Go2 敏捷行为的训练、部署、重定向、动捕资产连接起来，适合加入长期仓库候选。
- EPFL BioRob 有 Fall 2026 人形机器人步态 / 神经力学方向 PhD 和博后信号；RAI Institute 继续列出 Cambridge 与 Zurich 的 Research Scientist 岗位。

<details>
<summary><strong>新论文</strong></summary>

### Human Motion Priors for Scalable Robot Learning Across Morphologies
- 链接: https://arxiv.org/abs/2606.30290
- 来源: arXiv
- 日期: 2026-06-29
- 作者: Guillaume Sartoretti et al.
- 主题: 跨构型重定向、运动控制、移动操作、机器人学习、人类运动先验
- 摘要: X-Morph 将人类运动转换为可部署的非人形腿足机器人运动 / 移动操作策略，覆盖四足、六足和带机械臂四足平台。
- 备注: 项目页为 https://maker-rat.github.io/morph/。它很适合作为“人形运动数据规模化”与“更广腿足构型行为学习”之间的桥梁条目。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### iit-DLSLab/mpx
- 链接: https://github.com/iit-DLSLab/mpx
- 类别: MPC / 轨迹优化 / 工具库
- 机器人类型: 人形 / 四足
- 仿真器: MuJoCo MJX
- 部署: 仿真
- 摘要: 面向腿足机器人的 JAX MPC 与轨迹优化库，强调 GPU 并行 KKT 求解、自动微分 / 向量化，以及 MJX whole-body 示例。
- 备注: README 列出 Talos、H1、Aliengo、Go2、四足 trot / barrel roll、人形跳跃等示例；是 MPC / 工具库主列表的强候选。

### BotRunner64/Teleopit
- 链接: https://github.com/BotRunner64/Teleopit
- 类别: 重定向 / 遥操作 / 数据集 / 工具库
- 机器人类型: 人形
- 仿真器: MuJoCo
- 部署: 仿真与硬件
- 摘要: 面向 Unitree G1 的轻量全身遥操作框架，支持 BVH 与 Pico 4 VR 重定向、sim2sim、sim2real、训练数据记录和 ONNX 策略回放。
- 备注: 近期 README 更新提到 Pico 实时控制、LinkerHand sim2real 控制、手动 HDF5 记录，以及 sim / sim2real reference buffering 的统一。

### NJU-RLC/quadrupedal-agility
- 链接: https://github.com/NJU-RLC/quadrupedal-agility
- 类别: 强化学习 / 部署 / 重定向 / 数据集
- 机器人类型: 四足
- 仿真器: Isaac Gym
- 部署: 仿真与硬件
- 摘要: “Learning Diverse Natural Behaviors for Enhancing the Agility of Quadrupedal Robots”的官方实现，包含 BBC/TSC/EASI 训练流水线与 Go2 部署资产。
- 备注: 仓库引用 arXiv:2505.09979，并包含动捕、训练、部署和运动重定向相关组件。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### EPFL BioRob / Biorobotics Laboratory
- 机构: EPFL
- 主页: https://www.epfl.ch/labs/biorob/
- 实验室 / 院系: Biorobotics Laboratory
- 关键主题: 人形机器人步态 / 仿生控制 / 强化学习 / 神经力学
- 备注: Openings 页面列出 Fall 2026 的 PhD 与博后项目，主题是用人形机器人研究并利用人类步态神经力学，结合数值仿真、脊髓 / 高级中枢控制思想和强化学习。

### IIT Dynamic Legged Systems Lab
- 机构: Istituto Italiano di Tecnologia
- GitHub: https://github.com/iit-DLSLab
- 关键主题: 腿足 MPC / whole-body control / 人形与四足运动 / JAX 优化
- 备注: MPX 仓库是该实验室在 GPU 并行 MPC 和 whole-body MJX 示例方面的强信号，覆盖 Talos、H1、Aliengo 和 Go2。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### EPFL BioRob / Biorobotics Laboratory
- 类型: PhD / 博后
- 地点: 瑞士洛桑
- 来源: 官方实验室页面
- 截止时间: 未知；页面标注 Fall 2026
- 主题: 人形机器人步态 / 神经力学 / 强化学习 / 仿生控制
- 状态: active
- 备注: 一个 PhD 和一个博后岗位，项目围绕“用人形机器人研究并利用人类步态神经力学”。

### RAI Institute
- 类型: Research Scientist
- 地点: Cambridge, MA / Zurich, Switzerland
- 来源: 官方 careers 页面
- 截止时间: rolling / unknown
- 主题: robotics / AI / machine learning / machine perception / robot systems
- 状态: active
- 备注: Careers 页面列出 Research Scientist 与 Research Scientist (Zurich Location) 岗位；属于广义机器人研究信号，并非明确腿足限定。

</details>
