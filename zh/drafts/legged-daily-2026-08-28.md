[English](../../drafts/legged-daily-2026-08-28.md) | **中文**
# 腿足机器人日报 - 2026-08-28

## 摘要
- `SOLO` 针对长时程人形行走中不断累积的感知—控制误差，报告仅依赖胸前深度相机和本体感觉、零样本完成 1.5 公里户外连续部署。
- `LAC` 学习人形机器人在上身外部力/力矩作用下的可指令线性与角向全身柔顺，并包含真机遥操作移动操作演示。
- `RAEM` 将局部层析/三维可通行地图与考虑楼层高度的全局拓扑图结合，实现四足机器人连续探索五层楼梯间。
- 三个新代码发布值得检查：带实测分析的 Unitree H1-2 经典控制/RL 平衡栈、G1 在 MuJoCo 中的受保护多策略切换，以及默认禁用硬件输出的 Go2W ROS 2 导航工作区。
- 已核验 Inria Bordeaux / LAAS-CNRS 的柔顺全身四足协同设计博士职位，2026-08-31 截止；官方页面列出的开始日期为 2026-10-01，税前月薪 2,300 欧元。

<details>
<summary><strong>新论文</strong></summary>

### SOLO: Stable Omni-terrain Long-Horizon Perceptive Humanoid Locomotion
- 链接：[arXiv](https://arxiv.org/abs/2608.26583) · [项目页](https://sunpihai-up.github.io/solo/)
- 来源：arXiv
- 日期：2026-08-27
- 作者：Pihai Sun、Gang Han、Jingkai Sun、Jiahao Ma、Zeran Su、Zelin Tao、Peiran Liu、Shuai Shi、Wei Cui、Zifan Wang、Jialin Yu、Wen Zhao、Kangning Yin、Jiaxu Wang、Jiahang Cao、Lingfeng Zhang、Hao Cheng、Jian Tang、Yijie Guo、Qiang Zhang
- 主题：humanoid / perceptive locomotion / long-horizon deployment / terrain reconstruction / teacher-student reinforcement learning
- 摘要：把针对动作关键地形几何的查询式重建与轨迹感知蒸馏结合，将未来教师—学生分歧通过 PPO 目标反向归因到先前动作。
- 备注：论文报告压力测试地形平均成功率 97.5%，踏石成功率 96%。同一策略以 50 Hz 零样本部署，只使用一个胸前深度相机和本体感觉，在无外部地图或状态系统情况下连续完成 1.5 公里户外路线。今日未核验到公开代码。

### LAC: Linear and Angular Compliance for Humanoid Whole-body Control
- 链接：[arXiv](https://arxiv.org/abs/2608.25405) · [项目页](https://lac-humanoid.github.io/)
- 来源：arXiv
- 日期：2026-08-26
- 作者：Yang Liu、Zhongkai Gu、Wei Zhu、Mitsuhiro Hayashibe
- 主题：humanoid / whole-body control / linear compliance / angular compliance / reinforcement learning / loco-manipulation
- 摘要：训练单一教师—学生策略，使人形机器人面对上身外部力/力矩时实现可指令的线性与角向全身柔顺，而非把所有交互力都当作扰动排斥。
- 备注：方法从人类交互数据的接触帧合成全身柔顺响应，并在 Isaac Lab 中大规模训练。论文报告刚度指令范围内的单调调节、真机外力响应实验和遥操作移动操作演示。今日未核验到公开代码。

### RAEM: Robust Autonomous Exploration for Multi-Floor Environments with a Quadruped Robot
- 链接：https://arxiv.org/abs/2608.25366
- 来源：arXiv
- 日期：2026-08-26
- 作者：Zikang Yuan、Yuan Ren、Yian Wang、Yixue Wang、Enze Fang、Xuewei Zhang、Junda Cheng、Chi Chen、Chin-Pang Ho、Lijun Zhu、Shaohang Xu、Kwang-Ting Cheng、Xin Yang
- 主题：quadruped / autonomous exploration / multi-floor navigation / traversability mapping / topological planning / stair climbing
- 摘要：使用局部层析地图和分类三维可通行地图进行地形分析，同时增量构建考虑楼层高度的全局拓扑图，以高效规划跨楼层探索。
- 备注：楼梯中心对齐策略用于减少攀爬时突发偏航，双路径搜索则在局部拓扑断连时恢复引导路径。仿真与真机结果包括连续自主探索五层楼梯间。今日未核验到官方项目页或代码发布。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### FERBIN12/humanoid-balance-locomotion
- 链接：https://github.com/FERBIN12/humanoid-balance-locomotion
- 类别：control / reinforcement learning / toolkit
- 机器人类型：humanoid — Unitree H1-2
- 仿真器：MuJoCo / Gazebo with ROS 2
- 部署：仿真 / sim-to-sim
- 摘要：围绕 51 执行器 H1-2 模型，从 CoM/CoP 估计逐层构建力矩控制、踝策略、上身动量、迈步、LIPM 行走、全身 QP，并与 RL 策略进行同条件对比。
- 备注：2026-08-26 创建，MIT 许可。仓库包含 90 个 Python 模块、记录轨迹、扰动测试、地形失败案例和 400 Hz ROS 2 力控制移植。README 报告配套预训练 RL 策略在对比中 30 秒行走 12.9 米；所有演示结果仍仅限仿真。

### Nikerane/g1-switchstep
- 链接：https://github.com/Nikerane/g1-switchstep
- 类别：control / policy integration / toolkit
- 机器人类型：humanoid — Unitree G1 29-DoF
- 仿真器：MuJoCo
- 部署：仿真
- 摘要：在预训练 G1 行走与旋转踢腿 ONNX 策略间实现受保护切换，使用唯一指令所有者、基于测量状态的转换、终端稳定检查、混合过渡和故障被动阻尼。
- 备注：2026-08-28 创建。仓库包含张量/时序/哈希契约、确定性测试、执行指标与公开演示，但不包含策略二进制，用户需从固定上游获取资产。维护者明确说明这只是跨仿真器证据，不构成真机安全验证；今日 GitHub 未检测到仓库级许可证。

### zhuaoyuRobo/Go2W-navigate-project
- 链接：https://github.com/zhuaoyuRobo/Go2W-navigate-project
- 类别：navigation / perception / systems integration
- 机器人类型：quadruped / wheel-legged — Unitree Go2W 类平台
- 仿真器：ROS 2 集成，需外部仿真器或传感器源
- 部署：仿真与硬件接口兼具，但公开配置默认禁用硬件输出
- 摘要：发布 ROS 2 Humble 工作区，集成 FAST-LIO、点云定位、Nav2、机器人描述、速度指令限制，以及可选的学习型运动控制器接口。
- 备注：2026-08-27 创建，集成包采用 Apache-2.0，内含第三方组件保留各自许可证。地图、标定参数、策略权重、厂商 SDK 和真机 launch 文件被有意排除；公开 action scale 默认为零，Go2W bridge 需在本地完成启用与标定后才会输出。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### X-Humanoid / 北京人形机器人创新中心
- 机构：北京人形机器人创新中心
- 主页：https://sunpihai-up.github.io/solo/
- arXiv：https://arxiv.org/abs/2608.26583
- 实验室 / 院系：X-Humanoid
- 关键主题：humanoid / perceptive locomotion / long-horizon deployment / rough terrain / teacher-student reinforcement learning
- 备注：X-Humanoid 是 SOLO 新论文作者团队中反复出现的主要单位。项目报告 1.5 公里零样本感知行走，并称相关技术用于天工 Omni 的比赛和公开复杂地形演示，因此该团队应列为长时程人形移动能力的高优先级信号源。

### Mitsuhiro Hayashibe / Neuro-Robotics Laboratory
- 机构：Tohoku University
- 主页：https://lac-humanoid.github.io/
- arXiv：https://arxiv.org/abs/2608.25405
- 实验室 / 院系：Neuro-Robotics Laboratory
- 关键主题：humanoid / whole-body compliance / physical interaction / reinforcement learning / teleoperated loco-manipulation
- 备注：LAC 论文注明全部作者来自东北大学 Neuro-Robotics Laboratory，并为上身多接触位置的可指令线性与角向柔顺补充了真机证据。该团队是超越单纯扰动抑制、关注接触丰富型人形交互的有用信号源。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### Inria Auctus / LAAS-CNRS Gepetto
- 类型：博士
- 地点：法国 Talence / Bordeaux，计划赴 Toulouse 交流
- 来源：[Inria 官方职位页](https://jobs.inria.fr/public/classic/en/offres/2026-10319)
- 截止时间：2026-08-31；计划开始时间 2026-10-01
- 主题：quadruped / mechatronic co-design / local compliance / loco-manipulation / reinforcement learning / real-to-sim calibration / prototyping
- 状态：开放中 — 即将截止
- 备注：项目联合研究新型全身四足机器人的机械架构、驱动、柔顺分布与控制策略，实验目标包括户外高速奔跑和接取飞行物。官方要求机械设计、原型制造、机器人建模/控制以及 C++ 或 Python 能力；税前月薪为 2,300 欧元。

</details>
