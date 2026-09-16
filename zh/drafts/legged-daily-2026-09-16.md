[English](../../drafts/legged-daily-2026-09-16.md) | **中文**
# 腿足机器人日报 - 2026-09-16

## 摘要
- Weave 从人—物交互捕捉数据学习 Unitree G1 全身灵巧移动操作，用单一的接触与几何感知策略控制全身，并开放训练代码及约 23 小时的实体执行机器人—物体轨迹。
- WholeBodyWAM 通过面向异构全身控制器的统一语义接口和协调感知注意力，将预训练世界—动作先验扩展到人形移动操作。
- FZI 优化的可行力旋量多面体方法将任意多接触构型的稳定性分析提升至约 49–50 Hz，并在六足机器人 LAURON VI 上完成验证。
- 三个近期仓库提供互补资源：Weave 的 Isaac Lab 训练栈、SPOT 的 Unity/OpenXR 遥操作界面，以及针对类 Go2 四足机器人主动/被动脊柱偏航的可复现 Isaac Lab 研究。
- General Robotics 正在雷德蒙招聘全职人形机器人工程师，重点包括 RL/IL、全身控制、移动操作、sim-to-real 与真实部署。

<details>
<summary><strong>新论文</strong></summary>

### Weave: Learning Whole-Body Dexterous Loco-Manipulation from Human–Object Interactions
- 链接：https://arxiv.org/abs/2609.16683
- 来源：arXiv
- 日期：2026-09-15
- 作者：Liu Cao、Xingze Wu、Jingzhi Cui、Botian Xu、Mingzhi Pei、Ruoqu Chen、Mengdi Xu
- 主题：人形移动操作 / 灵巧手 / 人—物交互 / 接触感知重定向 / 强化学习
- 摘要：先将捕捉到的人—物交互转化为机器人可执行的机器人—物体参考轨迹，再训练单一的接触与几何感知策略，在九类物体和多段交互序列上联合控制 29 个身体关节与 12 个主动手指关节。
- 备注：作者报告在训练交互上达到 92.5% 成功率，并在不追加训练的未见序列上达到 65.0% 成功率。项目开放约 9,000 条、总计约 23 小时的实体执行轨迹以及 Isaac Lab 训练代码；本次未独立复现结果。

### WholeBodyWAM: Generalizing Pre-trained World–Action Priors to Humanoid Loco-Manipulation via WBC-Grounded Coordination
- 链接：https://arxiv.org/abs/2609.16644
- 来源：arXiv
- 日期：2026-09-15
- 作者：Zhuo Li、Yiming Yao、Jim Tan、Mengjie Jing、Zhipeng Dong、Fei Chen
- 主题：人形移动操作 / 世界—动作模型 / 全身控制 / 扩散 Transformer / 跨控制器泛化
- 摘要：保留预训练视觉—操作通路，同时加入统一全身控制器接口与协调感知自注意力，使同一世界—动作模型可联合预测未来视觉动态、操作动作和经过控制器语义落地的全身控制意图。
- 备注：评测覆盖六个仿真任务、八个真实任务以及 SONIC、AMO、GEAR 三种控制器接口。作者报告总体仿真成功率 91.9%、更强的真实环境分布外任务进展和更低的跨控制器成功率方差；本次未找到公开代码仓库，也未独立复现结果。

### Optimized Wrench Polytope Analysis for Real-Time Stability Control of Legged Robots in Complex Multi-Contact Configurations
- 链接：https://arxiv.org/abs/2609.17405
- 来源：arXiv；已投稿 IEEE ROBIO 2026
- 日期：2026-09-15
- 作者：Friedrich Graaf、Elias Birkefeld、Christian Eichmann、Elias Hofele、Tristan Schnell、Georg Heppner、Arne Roennau、Rüdiger Dillmann
- 主题：腿足机器人稳定性 / 多接触控制 / 可行力旋量多面体 / 力矩控制 / 六足机器人
- 摘要：加速任意三维接触构型下完整可驱动力旋量多面体的计算，使基于该分析的姿态稳定控制器能够进入常规控制回路，而非只作为离线分析工具。
- 备注：论文报告在六接触场景达到约 49–50 Hz，并完成仿真及 LAURON VI 实机验证，包括借助倾斜墙面的复杂支撑姿态。文中“其他控制器目前无法实现这些场景”的比较性表述属于作者主张，本次未独立核验。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### xiaohu-art/Weave
- 链接：https://github.com/xiaohu-art/Weave
- 类别：强化学习 / 模仿学习 / 人形—物体交互 / 数据集 / 工具链
- 机器人类型：人形机器人 / 搭载 Inspire 灵巧手的 Unitree G1
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真训练、评测、策略导出及实体执行轨迹数据；公开 README 尚未给出完整实机部署流程
- 摘要：开放 Weave 多物体全身灵巧移动操作训练栈，包括基于 Hydra 配置的 RSL-RL/PPO 训练、评测与回放工具、九类物体动作数据，以及 TorchScript/ONNX 导出。
- 备注：仓库创建于 2026-09-10，检查时最近推送为 2026-09-16。工作区约需 30 GB 并使用 Git LFS；本次检查时 GitHub 元数据未声明许可证。

### UMass-Embodied-AGI/SPOT-Unity
- 链接：https://github.com/UMass-Embodied-AGI/SPOT-Unity
- 类别：遥操作 / VR 界面 / 数据采集 / 可视化
- 机器人类型：人形机器人
- 仿真器：Unity 6；机器人训练与遥操作由相关 Genesis-Humanoid 栈承担
- 部署：VR/头显界面及硬件遥操作支持；通过 UDP 流式发送 OpenXR 头显/控制器位姿，也可在本地录制位姿序列
- 摘要：提供 SPOT 长时程人形遥操作的 Unity/OpenXR 操作端，包括双目鱼眼穹顶显示、相机 IMU 稳像、120 Hz 位姿流送/录制和独立 Python 接收器。
- 备注：检查时仓库创建并推送于 2026-09-15；GitHub 元数据未声明许可证。单独运行接收器不会控制机器人，完整机器人流程需与 Genesis-Humanoid 集成。

### sxngt/spine-quadruped-rl
- 链接：https://github.com/sxngt/spine-quadruped-rl
- 类别：强化学习 / 机器人形态 / 运动基准 / 研究工具链
- 机器人类型：四足机器人 / 类 Go2 刚性、主动脊柱和被动脊柱版本
- 仿真器：Isaac Lab 2.1 / Isaac Sim 4.5
- 部署：仅仿真与分析；未提供实体机器人部署证据
- 摘要：一套可复现的硕士论文代码库，在机器人几何和质量匹配的前提下，对比刚性躯干、主动驱动脊柱和被动扭簧脊柱在步行、奔跑、扰动恢复、蛇形转向和高速切向转弯中的表现。
- 备注：检查时仓库创建并推送于 2026-09-15；MIT 许可。包含参数化 URDF 生成、RSL-RL PPO 实验、确定性评测协议、多随机种子统计分析、测试、完整结论和奖励投机失败记录；原始实验数据未随仓库托管。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 清华 IIIS 主导的 Weave 合作
- 机构：清华大学 / 大连理工大学 / 香港中文大学
- 主页：https://xiaohu-art.github.io/Weave/
- arXiv：https://arxiv.org/abs/2609.16683
- GitHub：https://github.com/xiaohu-art/Weave
- 关键主题：灵巧人形移动操作 / 人—物交互 / 接触感知重定向 / 强化学习 / 交互数据集
- 更新：Liu Cao、Ruoqu Chen、Mengdi Xu 等合作者围绕 Unitree G1 与灵巧手发布了较完整的论文—项目页—代码—数据组合。可执行重定向、多物体策略学习和实体执行接触标注轨迹的结合，使这一合作网络值得持续关注。

### 香港中文大学—香港大学—北京大学—Phi-Institute WholeBodyWAM 合作
- 机构：香港中文大学 / 香港大学 / 北京大学 / Phi-Institute
- 主页：https://wholebodywam.github.io/
- arXiv：https://arxiv.org/abs/2609.16644
- 关键主题：人形移动操作 / 世界—动作模型 / 异构全身控制器 / 视觉语言条件 / sim-to-real
- 更新：Zhuo Li、Yiming Yao、Jim Tan、Mengjie Jing、Zhipeng Dong 与 Fei Chen 将预训练世界—动作建模连接到 SONIC、AMO、GEAR 三种全身控制器接口。这是面向控制器无关全身基础策略研究的强信号，但本次检查时尚无公开代码。

### FZI 腿足机器人与 KIT MaiRo 合作
- 机构：FZI Research Center for Information Technology / Karlsruhe Institute of Technology
- 主页：https://www.fzi.de/en/research/research-divisions/intelligent-systems-and-production-engineering/
- arXiv：https://arxiv.org/abs/2609.17405
- 关键主题：多足机器人 / 稳定性分析 / 多接触控制 / 力旋量多面体 / 野外机器人
- 更新：Friedrich Graaf、Elias Birkefeld、Christian Eichmann、Elias Hofele、Tristan Schnell、Georg Heppner、Arne Roennau 与 Rüdiger Dillmann 在 LAURON VI 上报告实时力旋量稳定控制。这是人形之外、面向复杂三维接触的显式模型稳定控制的重要信号。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### General Robotics — Robotics Engineer, Humanoids Focus
- 类型：Research Engineer / Robotics Engineer
- 地点：美国华盛顿州雷德蒙
- 来源：官方 Ashby 招聘页 — https://jobs.ashbyhq.com/generalrobotics/1acc15e9-f249-49c8-a0bb-5453da71327d
- 截止时间：滚动招聘 / 未注明
- 主题：人形移动操作 / 强化学习 / 模仿学习 / 全身控制 / 仿真 / sim-to-real / 部署
- 状态：active
- 备注：全职岗位发布于 2026-09-09。职责包括训练并部署面向真实移动操作的 RL/IL 策略、建设高保真仿真环境、发表及开源研究成果，并负责从研究到客户现场部署的完整链路。2026-09-16 检查时页面仍处于公开列出并可申请状态。

</details>
