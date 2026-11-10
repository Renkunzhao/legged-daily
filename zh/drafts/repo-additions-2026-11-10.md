[English](../../drafts/repo-additions-2026-11-10.md) | **中文**
# 通用控制器、蹦床动力学与视频动作项目补录评审 — 2026-11-10

## 评审范围与去重

这是用户要求的完整补充清单，不是定时日报。[日报预览](legged-daily-2026-11-10.md)精选三个仓库；本清单保留其余明确要求的项目供评审。条目沿用规范模板的仓库字段。尚未修改正式主列表。

- SONIC / GR00T-WholeBodyControl、TWIST2、zita-ch/supermimic_vibed、GMR 已在 [repos.md](../repos.md) 有独立条目，不重复添加。
- HoloMotion 已出现在已提交的 2026-10-22 草稿，MOSAIC 出现在 2026-10-26 草稿，但均无正式仓库条目。本次整合提案，不将其描述为新发布项目。
- ScaleBFM 已在 [papers.md](../papers.md) 出现。CuboiLeo 和 Motphys 的 SuperMimic 复现已在 supermimic_vibed 条目的 Notes 中链接；下方拟提升为便于检索的独立条目。
- Jules_toile_A2022、MuJoCo flex 示例、OnDynamicsForSomersaults 已由 [datasets.md](../datasets.md) 引用。下方单独索引代码，保留已有数据条目。
- RWM 已由 papers.md、backup.md 引用，但尚无独立 repos.md 条目。
- 发现项目和读取 README 时优先使用 GitHub API。后续搜索遭遇 HTTP 403 限流，对受影响的查询改用网页搜索及上游项目页/原始源码。本次未安装项目或独立复现实验。下方发布状态来自当日核验的上游说明，不代表已逐一验证全部外部下载。

## 通用人形控制器 — 拟新增独立条目

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

### zengweishuai/ScaleBFM
- Link: https://github.com/zengweishuai/ScaleBFM
- Category: 基础模型 / 动作跟踪 / 重定向 / 部署
- Robot Type: 人形（Unitree G1）
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: ScaleBFM 官方实现，整合 ScaleRetarget 动作准备、ScaleTrack 预训练与 ScaleBridge sim2sim/sim2real 部署。
- Notes: README 提供单/多 GPU 训练、回放和导出说明；本次未确认可直接下载的预训练检查点。交叉引用已有论文条目。原始 BFM 项目页代码链接仍标为“In Coming”，不应将其视为另一个已发布代码库：https://bfm4humanoid.github.io/。

### zixuan417/humanoid-general-motion-tracking (GMT)
- Link: https://github.com/zixuan417/humanoid-general-motion-tracking
- Category: 通用动作跟踪 / 推理
- Robot Type: 人形（Unitree G1）
- Simulator: MuJoCo
- Deploy: sim
- Summary: 轻量 GMT 官方发布，可在 MuJoCo 中使用预训练通用人形跟踪器执行示例动作。
- Notes: README 提供检查点和 sim2sim 命令；本次未确认完整训练管线和真机部署栈，数据处理/重定向仍标为后续发布。适合作为推理基线，不应默认它是完整训练框架。

### BAAI-Humanoid/MOSAIC
- Link: https://github.com/BAAI-Humanoid/MOSAIC
- Category: 通用动作跟踪 / 遥操作 / 适应
- Robot Type: 人形（G1 / H1-2 / Adam）
- Simulator: Isaac Lab；通过配套 RobotBridge 做 sim2sim
- Deploy: 仿真 / 通过配套项目真机部署
- Summary: 面向通用人形动作跟踪和遥操作适配的训练框架，包含多动作训练、蒸馏与残差适应配置。
- Notes: 部署说明位于单独链接的 RobotBridge 项目；本次未确认预训练权重获取情况。本次整合已提交的 2026-10-26 草稿，而非重复计作新发现。

### CuboiLeo/SuperMimic-Reproduced
- Link: https://github.com/CuboiLeo/SuperMimic-Reproduced
- Category: 世界模型 / 基于模型的 RL / 动作跟踪
- Robot Type: 人形（Unitree G1）
- Simulator: mjlab / MuJoCo Warp
- Deploy: sim
- Summary: 独立 SuperMimic 复现，包含可微动力学模型、BPTT actor 更新、多 GPU 训练和全动作库评估。
- Notes: README 链接 BONES-SEED 检查点 release，并明确列出 ONNX 导出、真机部署尚未完成。MIT。将原 Notes 中的链接提升为独立条目；最新 README 区分了论文观测实验和早期额外观测实验，不应沿用旧版对其最佳结果的一概描述。

### Motphys/Uni-SuperMimic
- Link: https://github.com/Motphys/Uni-SuperMimic
- Category: 世界模型 / 基于模型的 RL / 动作跟踪
- Robot Type: 人形（Unitree G1）
- Simulator: UniLab，支持 mjwarp / MuJoCo / Motrix
- Deploy: sim
- Summary: 独立 SuperMimic 复现，提供可切换仿真后端、LAFAN1/BONES-SEED 数据准备、训练与确定性全库评估。
- Notes: README 链接已发布的 LAFAN1、BONES-SEED 检查点及 EMA/no-sync 版本。Apache-2.0。将原 Notes 中的链接提升为独立条目；本次未独立复现其速度或跟踪结果。公开代码不代表已经具备 G1 蹦床部署能力。

## 蹦床力学与空翻动力学 — 代码交叉引用

### EveCharbie/Jules_toile_A2022
- Link: https://github.com/EveCharbie/Jules_toile_A2022
- Category: 物理建模 / 系统辨识 / 优化
- Robot Type: 通用（腿足系统的蹦床环境）
- Simulator: 自定义弹簧网模型 / CasADi
- Deploy: sim
- Summary: 使用动捕与测力台试验拟合蹦床模型，包含静态弹簧系数优化及拟议的动态阻尼辨识流程。
- Notes: 派生自 Julo0/Jules_toile_A2022。README 描述 pygmo/gaco 全局搜索与 CasADi/IPOPT 精化，但部分动态/局部精化和验证链接仍是占位。应视为研究代码，不是已完成标定的机器人仿真器。核验的项目页未声明许可。相关拟合数据已在 datasets.md 收录。

### MuJoCo flex trampoline example
- Link: https://github.com/google-deepmind/mujoco/blob/main/model/flex/trampoline.xml
- Category: 仿真器 / 弹性表面建模
- Robot Type: 通用（柔顺环境）
- Simulator: MuJoCo
- Deploy: sim
- Summary: 官方二维弹性 flexcomp 蹦床 MJCF 示例，包含下落球体，可作为柔顺接触场景的可检查起点。
- Notes: 核验 XML 为 16×16 网格、间距 0.1 m、四角固定、mass=10、杨氏模量 75000、厚度 0.01、边阻尼 10，步长 0.001 s。Apache-2.0。这些是示例参数，并非实验辨识的竞技蹦床参数。交叉引用已有 datasets.md 条目；该模型不同于只有中心节点可动的蹦床。

### Ipuch/OnDynamicsForSomersaults
- Link: https://github.com/Ipuch/OnDynamicsForSomersaults
- Category: 生物力学 / 动力学 / 轨迹优化
- Robot Type: 通用（为人形机器人提供参考的人体空翻）
- Simulator: biorbd / bioptim
- Deploy: sim
- Summary: 可复现的蹦床 Miller 空翻最优控制研究，比较自由浮动基座/全身动力学及显式/隐式形式。
- Notes: MIT。建模对象是空中阶段，不是床面接触模型。适合角动量和参考轨迹研究；代码依赖 biorbd 1.8.4、bioptim 2.2.1。仿真数据已作为 Miller Somersault Optimal Control Solutions 在 datasets.md 收录。

## 学习动力学 / 世界模型

### leggedrobotics/robotic_world_model
- Link: https://github.com/leggedrobotics/robotic_world_model
- Category: 学习动力学 / 世界模型 / 基于模型的 RL
- Robot Type: 四足（ANYmal D 参考管线）
- Simulator: Isaac Lab；离线想象训练可不启动仿真器
- Deploy: sim
- Summary: RWM/RWM-U 官方实现，支持联合学习动力学与策略、自回归预测可视化，以及在线/离线基于模型的策略优化。
- Notes: 参考实现提供可配置的状态、动作、接触、终止预测头和集成不确定性设置，README 链接预训练动力学及初始状态数据。可借鉴用于机器人—床耦合动力学，但不提供蹦床专用模型。GitHub 许可面板与 README 许可徽章不一致，复用前应检查 LICENCE，不能只据徽章判断。

### leggedrobotics/robotic_world_model_lite
- Link: https://github.com/leggedrobotics/robotic_world_model_lite
- Category: 学习动力学 / 离线基于模型的 RL / 工具包
- Robot Type: 四足（ANYmal D 示例）
- Simulator: 离线模型/策略训练无需仿真器
- Deploy: 离线训练 / 外部仿真器评估
- Summary: 轻量 RWM/RWM-U 管线，从离线数据学习循环网络集成动力学，再在学习动力学中训练策略，无需安装完整机器人仿真器。
- Notes: README 链接预训练 RWM-U 模型、初始状态数据与 Colab；评估使用完整 Isaac Lab 扩展或其他兼容环境。这是方法基线，不是已发布的蹦床世界模型。此处同样有许可面板/徽章不一致问题，应直接检查 LICENCE。

## 视频 → 人体动作 → 机器人参考

### zju3dv/GVHMR
- Link: https://github.com/zju3dv/GVHMR
- Category: 单目动作恢复 / 视频到动作
- Robot Type: 通用（人形重定向上游的人体动作）
- Simulator: none
- Deploy: 离线推理 / 数据
- Summary: 基于重力—视角坐标的单目世界坐标人体动作恢复官方实现，提供视频示例、预训练检查点引用、评估和训练命令。
- Notes: 静态相机模式可跳过视觉里程计，README 说明较新默认路径采用 SimpleVO。可接已有 GMR 条目，再接机器人 tracker。核验来源未证明其能可靠重建倒置、遮挡或动态床面接触下的蹦床空翻。

### yufu-wang/PromptHMR
- Link: https://github.com/yufu-wang/PromptHMR
- Category: 人体网格恢复 / 视频到动作
- Robot Type: 通用（人体到人形动作管线）
- Simulator: none
- Deploy: 离线推理 / 数据
- Summary: 可提示的人体网格恢复方法，提供世界坐标视频重建、静态/运动相机模式和模型下载脚本，可作为重定向管线的人体动作前端。
- Notes: README 明确说明受许可协议限制，不计划发布训练代码。SMPL 系列资产需要注册。链接的 video2robot 管线声明其非商业科研限制，不应视作端到端宽松许可工具包。

### AIM-Intelligence/video2robot
- Link: https://github.com/AIM-Intelligence/video2robot
- Category: 视频到动作 / 重定向 / 管线
- Robot Type: 人形（G1 / H1 / Booster T1）
- Simulator: 不含闭环控制器；提供动作可视化
- Deploy: 数据 / 浏览器可视化
- Summary: 整合已有视频或生成视频的处理流程：PromptHMR 人体恢复 → SMPL-X → GMR → 机器人参考动作，带 CLI 与浏览器可视化。
- Notes: 输出包含根姿态和关节位置的 robot_motion.pkl，属于运动学动作生成，不代表动态可执行性或已训练控制策略。已有视频无需经过可选的视频生成步骤。核心代码 MIT；端到端管线继承 PromptHMR 的非商业科研限制。

### yohanshin/WHAM
- Link: https://github.com/yohanshin/WHAM
- Category: 单目动作恢复 / 视频到动作
- Robot Type: 通用（人形重定向上游的人体动作）
- Simulator: none
- Deploy: 离线推理 / 数据
- Summary: 世界坐标人体动作恢复官方实现，支持自定义视频推理、相机运动估计、可选 Temporal SMPLify 精化及两阶段训练命令。
- Notes: 提供预训练模型下载脚本；SMPL 资产需要注册。可作为人体动作估计替代方案，随后仍需单独重定向到机器人。README 仍将数据预处理标为未完成；仅相机坐标输出选项不等同于世界坐标重建。

## 研究解读

- 物理模型路线：先用实验弹簧网辨识标定床面响应，再用实测下陷与回弹验证所选 MuJoCo 模型。datasets.md 已有 FIG/Qian 参数条目可作标定参考，但不能将这些量当作可直接互换的材料常数。
- 学习模型路线：用 SuperMimic 做策略学习，用 RWM/RWM-U 做离线动力学/不确定性基线。本次未核验到公开、可直接使用的蹦床专用世界模型；这是检索结果，不是“不存在”的断言。
- 视频路线：视频 → GVHMR 或 PromptHMR → GMR → 参考/接触/相位检查 → 动作 tracker。video2robot 封装了其中一条路线。人体恢复、机器人重定向、闭环执行是三项不同能力。
- 世界坐标动作估计器不等于动力学世界模型。蹦床动作还需单独检查相机尺度、腾空高度、倒置姿态、接触时序及床面相对高度；这些仓库中没有任何一个单独证明了柔性床上的端到端成功。
