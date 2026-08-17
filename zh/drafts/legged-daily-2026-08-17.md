[English](../../drafts/legged-daily-2026-08-17.md) | **中文**
# 腿足机器人日报 - 2026-08-17

## 摘要
- `HiPHI` 是今日最强信号：官方发布 617.5 小时、2.001 亿帧的类人机器人学习光学动作捕捉数据，其中包含 245.7 小时同步人-物交互数据，并报告了 Unitree G1 真机验证。
- `G1-MOTION` 打包了一条完整的 Unitree G1 视频到真机动作模仿流程，覆盖姿态提取、重定向、数据转换、Isaac Lab 训练、MuJoCo 验证、模型导出和部署。
- 今日未选入新论文。当前 arXiv 批次中相关性最强的 loco-manipulation 论文已经收录于 8 月 13 日草稿，其余新 listing 未达到直接腿足机器人相关性的收录门槛。
- 今日没有新增足够新且可独立核验的实验室/教授或招聘信号；与本轮搜索中的噪声结果相比，现有已追踪机会仍更具可操作性。

<details>
<summary><strong>新论文</strong></summary>

今日未选入新论文。筛选中相关性最强的论文 “Learning Loco-Manipulation From SMPC Demonstrations With Sparse Offline-to-Online RL”（arXiv:2608.12063）已在 2026-08-13 草稿中收录。机器人学新 listing 中的其他记录要么超出腿足机器人范围，要么直接相关性不足，不宜为凑数而收录。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### HiPHI
- 链接：[GitHub](https://github.com/noitom-robotics/hiphi) · [项目页](https://noitom-robotics.github.io/hiphi/) · [数据集](https://huggingface.co/datasets/noitomrobotics/HiPHI)
- 类别：数据集 / 基准 / 查看器
- 机器人类型：类人 / 通用
- 仿真器：无
- 部署：数据 / 浏览器 / 真机验证
- 摘要：大规模光学动作捕捉基准，发布 617.5 小时、2.001 亿帧的标准化 55 关节 BVH 动作，其中包含 245.7 小时同步人-物交互、物体轨迹和高分辨率网格，可用于类人机器人模仿学习、重定向、动作生成与全身控制。
- 备注：Noitom Robotics 官方仓库和项目页于 2026-08-17 发布。数据以 90 Hz 覆盖 132 名表演者、22 个 FrameNet frame、214 个 Frame-LU 标签和 40 个标准物体网格；项目报告了动作跟踪的数据规模实验和 Unitree G1 真机部署。数据采用 ModalityNet Open Research License v1.0，仅限非商业科研、教育和评测；BVH 动作仍需针对目标机器人重定向并验证。

### G1-MOTION
- 链接：https://github.com/tangweixing/G1-MOTION
- 类别：重定向 / 强化学习 / 控制 / 工具包
- 机器人类型：类人 — Unitree G1
- 仿真器：Isaac Lab / Isaac Sim / MuJoCo
- 部署：仿真与真机
- 摘要：集成式工作流，将人类动作视频依次经过 GVHMR 姿态恢复、GMR 重定向、动作数据转换、Isaac Lab 全身跟踪训练、ONNX/MNN 导出、仿真验证，最终部署到 Unitree G1 真机。
- 备注：仓库创建于 2026-08-17，根目录采用 MIT 许可证。它打包了 7 个上游项目、训练与推理产物、CSV/NPZ 转换工具、部署模板，以及中英文分步文档。仓库体积较大且聚合了第三方组件，复用前应分别核查各子项目的原始文档、许可证、模型权重条款和机器相关路径假设。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

今日未选入足够新的实验室或教授信号。HiPHI 提供了 Noitom Robotics 及其高校合作者这一有价值的新产业研究来源，但现有发布材料尚不足以构成应与数据集条目分开收录的独立实验室/教授更新。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日未选入新的高置信招聘信号。官方与定向搜索未发现新发布、直接面向腿足机器人且细节足够具体可核验、能优于 `jobs.md` 现有活跃机会的岗位。

今日未发现需要提出删除的过期条目。

</details>
