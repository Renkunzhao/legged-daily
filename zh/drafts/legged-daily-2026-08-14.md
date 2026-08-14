[English](../../drafts/legged-daily-2026-08-14.md) | **中文**
# 腿足机器人日报 - 2026-08-14

状态：仅草稿；等待确认后正式发布并合并主列表。

## 摘要
- HumanTracker 新增约 153 小时的人形机器人运动跟踪基准，并提出偏好对齐的 HumanScore，用于发现逐帧运动学误差容易漏掉的接触、支撑与稳定性问题。
- HumanoidVLN 在 Isaac Sim 中让四种人形机器人通过真实双足动力学执行视觉语言导航，并报告了一个小规模 Unitree G1 仿真到现实试验。
- 新的 Unitree H1 鲁棒性仓库围绕 Isaac Lab 提供冻结策略评估、受控物理失配扫描、多随机种子统计、回归阈值和可在 CPU 上测试的 CI。
- RobotUniversityGiar 是面向教学的 G1 策略训练与切换栈，支持 Genesis CPU / Apple Silicon；Torq-MPC 目前则只是 ROBIO 2026 四足跳跃项目的早期占位仓库。
- Li Yi 官方论文页已将 HumanTracker 列为 ECCV 2026 工作；USC Dynamic Robotics and Control Lab 参与 HumanoidVLN，并持续公开腿足机器人相关学生机会。
- 此前跟踪的 LAAS-CNRS 人形机器人安全强化学习博士职位已过截止日期，确认后应从活跃列表移除。

<details>
<summary><strong>新论文</strong></summary>

### HumanTracker: Towards Comprehensive and Human-Aligned Motion Tracking Benchmark
- 链接：[arXiv](https://arxiv.org/abs/2608.13555) · [Li Yi 论文页](https://ericyi.github.io/)
- 来源：arXiv / ECCV 2026
- 日期：2026-08-13
- 作者：Dairu Liu, Zekun Qi, Jiayu Zeng, Ruixi Yu, Yu Guan, Yintianrun Zhang, Xuchuan Chen, Sikai Liang, Zekai Li, Chenghuai Lin, Xinqiang Yu, Wenyao Zhang, He Wang, Li Yi
- 主题：人形机器人 / 运动跟踪 / 基准 / 接触质量 / 偏好对齐评估
- 摘要：提出一个人形机器人运动跟踪基准，包含约 153 小时、由多位专业表演者采集并划分为四类动作的光学运动轨迹；同时提出在 12,000 对动作、共 24,000 段运动上训练的 HumanScore，以更好识别支撑不稳、接触错误、脚底打滑和落脚时机不准等问题。
- 备注：论文已被 ECCV 2026 接收。arXiv 与 Li Yi 官方论文页可相互核验，但本轮未发现公开代码或基准下载链接。

### HumanoidVLN: A Physics-Grounded Simulator and Benchmark for Vision-Language Navigation Across Diverse Humanoid Embodiments
- 链接：[arXiv](https://arxiv.org/abs/2608.12860) · [项目页](https://humanoid-vln.github.io/)
- 来源：arXiv
- 日期：2026-08-13
- 作者：Quan-Dung Pham, Anh Dao, The-Anh Nguyen, Minh Nguyen-Dinh, Phuong Nam Dang, Tri Pham, Hung Tran, Bach Dao, Tuyen P. Le, Truong Nguyen, Quan Nguyen
- 主题：人形机器人 / 视觉语言导航 / Isaac Sim / 运动控制 / MPC / 仿真到现实
- 摘要：构建 Isaac Sim 物理视觉语言导航基准，让 Unitree G1、Unitree H1 和两款内部人形平台通过分层强化学习运动策略，以及可替换的 PD 或 MPC 路径跟踪器真实执行导航，而不是以运动学方式“瞬移”。
- 备注：论文报告 933 个避碰参考 episode，在四种机器人形态上测试四类 VLN 模型，并包含 20 个 episode 的 Unitree G1 仿真到现实试验。项目正在 Humanoids 2026 双盲评审中；代码、基准和数据承诺在录用后发布，目前尚未公开。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### 22kashaf-khan/humanoid-simulation-robustness-benchmark
- 链接：https://github.com/22kashaf-khan/humanoid-simulation-robustness-benchmark
- 类别：基准 / 强化学习 / 验证 / 工具包
- 机器人类型：人形机器人
- 仿真器：Isaac Lab
- 部署：仿真
- 摘要：一个可复现的 Unitree H1 运动控制验证框架，冻结项目内训练的 PPO 策略，在受控的接触摩擦、整机质量和执行器力矩能力失配下，以存活率、速度跟踪、基座倾斜和关节限位等指标进行评估。
- 备注：创建于 2026-08-12；Python，本轮检查时 0 star，未检测到许可证。仓库报告 11 个条件、5 个随机种子下共 55 次运行和 5,500 个 episode，包含检查点、配置、结果、43 项 CPU 测试、回归检查和 GitHub Actions CI；它是工程验证基准，不是新的运动算法，也未提供硬件验证。

### GIAR-UTN/RobotUniversityGiar
- 链接：https://github.com/GIAR-UTN/RobotUniversityGiar
- 类别：强化学习 / 控制 / 教学 / 工具包
- 机器人类型：人形机器人
- 仿真器：Genesis / Isaac Gym / Isaac Sim
- 部署：仿真与硬件接口
- 摘要：面向课程与入门实践的 Unitree G1 栈，整合本地或云端 PPO 训练、检查点操作、与后端无关的策略管理、安全门控在线策略切换、Web 控制和仿真/真机适配器，尤其强调 CPU 与 Apple Silicon 上的 Genesis 工作流。
- 备注：创建于 2026-08-13；Python，BSD-3-Clause，本轮检查时 0 star。它建立在 legged_gym、unitree_rl_gym 与 LeggedGym-Ex 之上；真机适配器明确尚未测试，因此当前价值主要是教学、仿真和控制管线，而不是已验证的 G1 真机部署。

### lab-sun/Torq-MPC
- 链接：https://github.com/lab-sun/Torq-MPC
- 类别：MPC / 控制 / 项目页
- 机器人类型：四足机器人
- 仿真器：未披露
- 部署：硬件演示 / 代码未发布
- 摘要：ROBIO 2026 项目的官方占位仓库，研究面向重载四足机器人跳跃的速度相关扭矩约束模型预测控制，目前仅链接到演示视频。
- 备注：创建于 2026-08-14；MIT，本轮检查时 0 star。仓库当前只有 README 和许可证，尚无论文、实现、机器人细节或复现实验说明，应作为早期项目动态而不是可用代码发布跟踪。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Li Yi / Human-Centered 3D Vision and Robotics 团队
- 机构：清华大学
- 主页：https://ericyi.github.io/
- arXiv：https://arxiv.org/abs/2608.13555
- 实验室 / 院系：交叉信息研究院
- 关键主题：人形机器人 / 运动跟踪 / 人类偏好对齐评估 / 3D 感知 / 机器人学习
- 备注：Li Yi 官方论文页现已将 HumanTracker 列为 ECCV 2026 论文。结合该团队此前的 Humanoid-GPT、LIMMT、Any2Track 和运动型人形机器人工作，这进一步强化了其作为人形运动跟踪、数据与评估高信号来源的价值。
- 学生与代表工作：
  - [Zekun Qi](https://qizekun.github.io/) — [HumanTracker](https://arxiv.org/abs/2608.13555) / [Humanoid-GPT](https://qizekun.github.io/humanoid-gpt/)

### Quan Nguyen / Dynamic Robotics and Control Laboratory
- 机构：南加州大学
- 主页：https://sites.usc.edu/quann/
- arXiv：https://arxiv.org/abs/2608.12860
- 实验室 / 院系：Viterbi School of Engineering / Aerospace and Mechanical Engineering
- 关键主题：人形机器人 / 四足机器人 / 轮腿机器人 / 运动控制 / 非线性控制 / 轨迹优化 / 强化学习
- 备注：HumanoidVLN 为这一来源网络增加了一个贯穿强化学习运动控制与 PD/MPC 跟踪的物理导航基准。实验室官网继续将敏捷、鲁棒的腿足运动控制列为核心方向，并公开招募研究方向匹配的学生。
- 学生与代表工作：
  - [Quan-Dung Pham](https://arxiv.org/search/cs?searchtype=author&query=Pham,+Q) — [HumanoidVLN](https://humanoid-vln.github.io/)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### USC Dynamic Robotics and Control Laboratory
- 类型：博士 / 本科生或硕士研究志愿者
- 地点：美国加利福尼亚州洛杉矶
- 来源：[实验室官网](https://sites.usc.edu/quann/)
- 截止时间：未知 / 随研究生申请周期
- 主题：腿足机器人 / 四足 / 人形 / 轮腿机器人 / 控制 / 优化 / 规划 / 强化学习
- 状态：观察中
- 备注：实验室表示持续寻找研究方向匹配、自驱的学生。南加州大学现有本科生和硕士生可联系 Quan Nguyen 申请研究志愿者机会；博士申请人需通过 USC AME 正式申请并在材料中提及他。由于未核验到具体资助项目或独立截止日期，应将其视为实验室层面的机会信号，而不是已确认的职位空缺。

### 拟删除 / 过期条目
- 当前状态：已过期 / 不再可操作
- 原因：此前跟踪的 LAAS-CNRS Gepetto 人形机器人安全强化学习博士职位所列申请截止时间为 2026-07-31 23:59，现已过期；除非官方团队发布延期或替代职位，否则不应继续标为活跃。
- 已检查来源：https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN

</details>
