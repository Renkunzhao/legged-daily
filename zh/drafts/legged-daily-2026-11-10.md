[English](../../drafts/legged-daily-2026-11-10.md) | **中文**
# Legged Daily - 2026-11-10

## 摘要
- 按用户要求回溯补录，不将这些项目描述为今日新发布：优先提议补充正式仓库列表尚缺的 OpenTrack、HoloMotion、BFM-Zero。
- OpenTrack 提供特别相关的参考动作入口实现：带足部和质心约束的 QP/IK 跨步过渡，从默认站姿进入动作首帧。
- 蹦床模型标定、学习动力学、视频动作恢复见[完整补充评审](repo-additions-2026-11-10.md)，共 17 个独立仓库条目提案，并明确交叉引用已有论文/数据集。
- 本次未核验到公开可直接使用的蹦床专用世界模型。RWM/RWM-U 是通用腿足动力学基线；GVHMR/PromptHMR/WHAM 是人体动作估计器，不是动力学世界模型。
- GitHub API 发现项目后，因实际发生 HTTP 403 搜索限流而改用网页/项目页补查。可用性结论来自来源核验，不是本地执行结果。

<details>
<summary><strong>新论文</strong></summary>

本次聚焦仓库，不提议新增论文条目。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### GalaxyGeneralRobotics/OpenTrack (Any2Track)
- Link: https://github.com/GalaxyGeneralRobotics/OpenTrack
- Category: 动作跟踪 / RL / 蒸馏 / 动力学适应
- Robot Type: 人形（Unitree G1）
- Simulator: MuJoCo / JAX
- Deploy: both
- Summary: Any2Track 官方代码，包含专用 PPO 教师、DAgger 通用学生、AnyAdapter 动力学适应和真机部署流程。
- Notes: README 提供 LAFAN1 generalist v2 检查点链接与训练/导出命令；40/40 跟踪结果为作者自报。动作预处理包含从默认站姿到片段首帧的 QP/IK 跨步过渡，约束足部与质心，特别适合参考动作入口设计；不是蹦床迁移成功的证据。

### HorizonRobotics/HoloMotion
- Link: https://github.com/HorizonRobotics/HoloMotion
- Category: 动作跟踪 / 基础模型 / 遥操作
- Robot Type: 人形（Unitree G1）
- Simulator: Isaac / MuJoCo；SuperMimic 路线另支持 MuJoCo Warp
- Deploy: both
- Summary: 人形全身动作跟踪框架，提供预训练模型、训练、MuJoCo 评估以及 G1 遥操作/部署说明。
- Notes: README 链接 v2.0.0 模型包及 2026-10-24 加入的独立 SuperMimic 训练路线。各模式的发布和验证范围不同，不能假设 SuperMimic actor 与 HoloMotion 主模型共用部署接口。本次整合 2026-10-22 草稿条目。

### LeCAR-Lab/BFM-Zero
- Link: https://github.com/LeCAR-Lab/BFM-Zero
- Category: 无监督 RL / 行为基础模型 / 动作跟踪
- Robot Type: 人形
- Simulator: Isaac Sim / MuJoCo；另链接 MJLab 分布式训练
- Deploy: both
- Summary: 可提示的行为基础模型，通过推断潜表示支持动作跟踪、目标到达和奖励条件化行为。
- Notes: 主 README 将完整训练/评估、预训练模型和部署标为已发布；对应接口见 deploy、minimal_inference 分支。面向 RTX 4090 的精简训练实现仍未在路线图中勾选。CC BY-NC 4.0。与原始 BFM、ScaleBFM 研究线不是同一项目。

</details>

<details>
<summary><strong>新数据集</strong></summary>

不提议新增数据发布。datasets.md 已有蹦床标定和空翻数据，补充评审中进行了交叉引用；本次未重新下载或核验其数据文件。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

本次定向仓库检索未评审此类信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次定向仓库检索未评审招聘，不提议新增或删除岗位。

</details>
