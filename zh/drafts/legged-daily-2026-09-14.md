[English](../../drafts/legged-daily-2026-09-14.md) | **中文**
# 腿足机器人日报 - 2026-09-14

## 摘要
- DWMP 分别用 Koopman 世界模型和循环状态空间世界模型编码人形机器人的本体感觉与第一视角深度信息，再融合两种潜在表示用于 Unitree G1 障碍穿越。
- CLAW 将测试时世界模型适应摊销到预训练阶段：超网络利用数秒交互数据生成 LoRA 适配器，并在运动与操作环境族上评估。
- 多模型全局规划器把面向可通行性的 Heading-Aware A* 与可切换运动学模型的 Pure Pursuit 控制器结合，并在 Artaban 四足机器人上进行仿真验证。
- 两个新建仓库提供互补的四足资源：面向 Unitree Go2 的接触/滑移风险门控 Isaac Gym 训练，以及包含 SLAM、Nav2 和程序化办公室场景的 ROS 2 Jazzy/Gazebo Harmonic 室内导航栈。
- 今日未选出新的高置信、可执行招聘机会；已有跟踪机会仍保存在 `jobs.md`，申请前应在官方来源复核状态。

<details>
<summary><strong>新论文</strong></summary>

### DWMP: Leveraging Dual World Models for Humanoid Obstacle Traversal
- 链接：https://arxiv.org/abs/2609.12347
- 来源：arXiv
- 日期：2026-09-11
- 作者：Rongjun Jin、Jianming Ma、Yue Gao
- 主题：人形机器人运动 / 障碍穿越 / 世界模型 / 深度感知 / 教师—学生学习
- 摘要：分别用基于 Koopman 的动力学世界模型和基于 RSSM 的视觉世界模型处理本体动力学与第一视角深度信息，再将融合后的潜在表示输入学生策略以生成避障动作。
- 备注：作者报告其仿真成功率较强教师—学生基线提高约 10%，并在 Unitree G1 上完成随机化顶部障碍、横杆和狭窄通道布局的实机部署。这些是作者报告结果，本次未独立复现。

### Amortized Low-Rank Adaptation for Model-Based Reinforcement Learning
- 链接：https://arxiv.org/abs/2609.12278
- 来源：arXiv
- 日期：2026-09-11
- 作者：Fernando Palafox、David Fridovich-Keil
- 主题：基于模型的强化学习 / 世界模型 / 测试时适应 / LoRA / 运动任务
- 摘要：提出 CLAW：通过上下文条件超网络，把少量测试时转移样本转换为冻结世界模型的 LoRA 适配器，尝试兼顾上下文推理的速度与权重空间适应的表达能力。
- 备注：实验覆盖动力学、形态和奖励发生变化的运动与操作环境族。作者报告仅用数秒测试时数据即可优于梯度适应和上下文学习基线；该论文对腿足适应具有广泛方法价值，但不是专门的腿足实机研究。

### Global Path Planner with Multi-Model Switching
- 链接：https://arxiv.org/abs/2609.13015
- 来源：arXiv / IFAC 已接收论文
- 日期：2026-09-11
- 作者：Pietro Gori、Francesco Iotti、Eduard Zelenay、Rastislav Marko、Michele Pierallini、Franco Angelini、Gabriele Pannocchia、Manolo Garabini
- 主题：四足导航 / 全局路径规划 / 可通行性 / 运动学模型切换 / Pure Pursuit
- 摘要：构建可通行性图，用考虑朝向代价的 A* 规划路径，再由 Pure Pursuit 控制器根据地形、机器人状态和平台约束切换不同运动学模型进行跟踪。
- 备注：摘要明确报告了在 Artaban 四足机器人和 X3 四旋翼上的仿真验证；论文还讨论更广泛实验，但本日报保守地将明确的四足证据视为仿真结果。结果未独立复现。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### lilaojiu182-star/CRG-SLR
- 链接：https://github.com/lilaojiu182-star/CRG-SLR
- 类别：强化学习 / 运动控制 / 接触风险建模
- 机器人类型：四足机器人 / Unitree Go2
- 仿真器：NVIDIA Isaac Gym Preview 4
- 部署：仅训练代码；未包含评估项目、检查点或实机部署流程
- 摘要：发布一个聚焦的 PPO 训练任务，在仅本体感知的运动策略上增加自监督足端接触与滑移风险预测，并根据预测风险对各腿动作更新进行门控。
- 备注：创建于 2026-09-14。仓库包含 Go2 环境和资产、策略、runner、粗糙地形课程、动力学随机化及 4096 个并行环境的复现配置。由于继承 SLR 材料，项目采用 CC BY-NC 4.0，仅限非商业研究用途，不属于 OSI 认可开源；检查时尚无公开论文编号或冻结论文检查点。

### btxviny/go2_nav
- 链接：https://github.com/btxviny/go2_nav
- 类别：导航 / 仿真环境 / ROS 2 集成
- 机器人类型：四足机器人 / Unitree Go2
- 仿真器：Gazebo Harmonic 与程序化生成的 Blender 办公室
- 部署：仿真；提供包含 SLAM、Nav2、KISS-ICP、ros2_control 和遥操作的 ROS 2 Jazzy 栈，未见实体 Go2 部署证据
- 摘要：为 Go2 打包可重复的室内导航环境，组合 Blender 构建的办公室、Gazebo 仿真、激光雷达与相机感知、建图/定位、Nav2 点到点导航及完整启动文档。
- 备注：创建于 2026-09-13。项目提供 Docker 构建，用于在干净 Ubuntu 24.04 环境验证依赖安装和 colcon 编译；本次未独立测试 GUI 与运行时行为。其原创 `go2_office_sim` 包、Blender 脚本和文档采用 MIT 许可证，供应商代码与子模块沿用各自许可证。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 得州大学奥斯汀分校学习与自适应机器人系统信号
- 机构：The University of Texas at Austin
- 主页：https://arxiv.org/abs/2609.12278
- 关键主题：基于模型的强化学习 / 测试时适应 / 世界模型 / 运动任务 / 机器人学习
- 备注：Fernando Palafox 与 David Fridovich-Keil 发布 CLAW，将该团队的适应与决策研究推进到通过生成低秩适配器实现近即时世界模型专门化。运动实验覆盖动力学、形态和奖励变化，值得作为腿足仿真到现实适应方法的持续信号跟踪。

### 比萨大学—Panza Robotics—布拉迪斯拉发斯洛伐克理工大学规划合作
- 机构：University of Pisa / Panza Robotics, National Center of Robotics / Slovak University of Technology in Bratislava
- 主页：https://arxiv.org/abs/2609.13015
- 关键主题：四足自主性 / 可通行性 / 全局规划 / 自适应运动学模型 / 控制
- 备注：跨机构团队发布已获 IFAC 接收的规划器，把地形分析、考虑朝向的图搜索与模型切换轨迹跟踪连接起来，并以 Artaban 四足机器人作为验证平台之一。这是地形感知自主性方面的具体合作信号，而非新的招聘公告。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次未选出新的高置信、可执行腿足机器人或人形机器人岗位。搜索结果噪声较高，或与 `jobs.md` 中已有机构重复，因此未加入未经核验的职位。已有观察名单机会仍保存在 `jobs.md`；申请前请在官方招聘页面确认岗位状态与截止时间。

</details>
