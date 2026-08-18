[English](../../drafts/legged-daily-2026-08-18.md) | **中文**
# 腿足机器人日报 - 2026-08-18

## 摘要
- `HAF` 通过分阶段生成移动/头部、腰部和操作动作，并在紧凑频谱潜变量中进行 offline-to-online RL，将通用 flow-matching VLA 适配到类人机器人全身移动操作；项目报告了 7 项真机任务。
- `TACL` 用策略条件化的轨迹难度估计与自动任务采样替代手工地形课程，直接在原始非结构化地图上生成训练轨迹；相对无课程直接训练，报告成功率提升 56.3%。
- `RB-TRG` 为轮腿机器人稀疏地形图规划加入考虑朝向和转弯的机体风险；配对 MuJoCo 测试将端到端成功率从 51.5% 提高到 68.5%，并发布了 Apache-2.0 核心规划器。
- 新发布的 DroidUp E1 仓库基于 MJLab 提供 AMP、动作模仿任务和 MuJoCo ONNX sim-to-sim runner，但目前属于仿真阶段，且仓库未声明许可证。
- 上海科技大学 Mobile Autonomous Robotic Systems Lab 是轮腿自主、建图、规划与全栈真机部署方向的新来源网络信号；今日未选入新的可操作招聘机会。

<details>
<summary><strong>新论文</strong></summary>

### HAF: Adapting Generalist VLAs to Humanoid Whole-Body Loco-manipulation via Hierarchical Action Flow and Spectral Latent RL
- 链接：[arXiv](https://arxiv.org/abs/2608.16837) · [项目页](https://grange007.github.io/HAF/)
- 来源：arXiv
- 日期：2026-08-17
- 作者：Langzhe Gu、Chengkai Hou、Meng Li、Xinhua Wang、Jiaming Liu 等
- 主题：类人机器人 / 全身移动操作 / VLA / flow matching / offline-to-online RL
- 摘要：提出由两部分组成的类人机器人适配框架：HAF-VLA 通过三阶段层级去噪生成相互依赖的移动、腰部和双臂动作；HAF-Steer 则冻结 VLA 主干，在 DCT 压缩的 flow-noise 潜空间中使用 SAC 做策略优化。
- 备注：官方项目报告了 7 项长时程真机移动操作任务；在其基准上，HAF-VLA 平均成功率为 70.5%，pi0.5 为 53.3%。今日未核验到官方代码仓库。

### Trajectory-Level Automatic Curriculum Learning for Legged Locomotion on Unstructured Terrain
- 链接：https://arxiv.org/abs/2608.16164
- 来源：arXiv
- 日期：2026-08-17
- 作者：Rocky Liu、Tengyu Liu、Baoxiong Jia、Fangwei Zhong、Xinyi Tong、Hongzhao Xie、Siyuan Huang
- 主题：腿足运动 / 强化学习 / 自动课程 / 非结构化地形 / sim-to-real
- 摘要：提出 TACL 闭环课程框架，从 rollout 结果学习策略条件化的轨迹难度，并通过 evaluator 引导的 MH-MCMC，直接在非结构化高度图上采样与当前能力匹配的 waypoint 任务。
- 备注：论文报告相对无课程直接训练，轨迹成功率提升 56.3%；在最难任务上比手工课程提高 18.5%，面对同类障碍的不同接近方向时最高提升 39.74%。今日未核验到官方代码发布。

### Robot-Body-Aware Traversal Risk Graph Planning for Wheeled-Legged Robots in Complex Terrain
- 链接：[arXiv](https://arxiv.org/abs/2608.16433) · [代码](https://github.com/ZhiqiaoGuo/RB-TRG)
- 来源：arXiv
- 日期：2026-08-17
- 作者：Zhiqiao Guo、Bichi Zhang、Sören Schwertfeger
- 主题：轮腿机器人 / 地形规划 / 通行风险 / A* / LiDAR 导航
- 摘要：在稀疏 Traversal Risk Graph 规划中加入沿图边和转向 yaw sweep 评估的有朝向矩形机体 footprint，将前后支撑变化、侧向倾斜、地形干涉和未知地图暴露纳入考虑航向的 A* 转移代价。
- 备注：配对 MuJoCo 实验将端到端成功率从 51.5% 提升到 68.5%，平均路径长度仅增加 2.3%。论文还报告了 Go2-W 全栈 LiDAR 部署，并在 IEEE ICRA 2026 Legged Robot Challenges 获得 Best Autonomy 和 Best Mobility。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### RB-TRG
- 链接：https://github.com/ZhiqiaoGuo/RB-TRG
- 类别：运动规划 / 工具包
- 机器人类型：轮腿
- 仿真器：发布内容不含仿真器
- 部署：软件 / 论文含真机方法验证
- 摘要：采用 Apache-2.0 许可证的 Python 实现，在已有地形图和高度栅格上完成 robot-body-aware Traversal Risk Graph 评分与确定性的 ordered-pair A* 搜索。
- 备注：仓库创建于 2026-08-16，并由论文直接链接。当前发布包含 NumPy 核心规划器、合成示例、测试和预印本，但明确不包含地形图构建、仿真与执行流水线、控制器、数据集、场景资产、评测脚本及对比框架。

### DroidUpE1_mjlab
- 链接：https://github.com/Anwei-Saw/DroidUpE1_mjlab
- 类别：强化学习 / 模仿学习 / 控制 / 工具包
- 机器人类型：类人 — DroidUp E1 21-DOF
- 仿真器：MJLab / MuJoCo
- 部署：仿真
- 摘要：新发布的 DroidUp E1 运动训练工作区，包含速度指令 walk/run AMP、全身 mimic tracking、动作数据转换与回放工具、训练产物、ONNX 策略，以及 MuJoCo sim-to-sim runner。
- 备注：仓库创建于 2026-08-18。README 记录了 4096 环境训练与键盘控制 MuJoCo 评测，但未声称真机部署，GitHub 也未显示仓库许可证；复用其中数据、权重、机器人资产和本地 `rsl_rl` 副本前，应分别核查来源与授权。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Sören Schwertfeger / Mobile Autonomous Robotic Systems Lab
- 机构：上海科技大学
- 主页：https://robotics.shanghaitech.edu.cn/
- Google Scholar：https://scholar.google.com/citations?user=Y2olJ9kAAAAJ&hl=en
- 实验室 / 院系：Mobile Autonomous Robotic Systems Lab，信息科学与技术学院 / STAR Center
- 重点方向：移动机器人 / 建图 / 自主导航 / 地形规划 / 搜索救援 / 轮腿机器人
- 备注：RB-TRG 为该实验室已有的建图与自主导航研究增加了强腿足机器人信号：论文结合机体感知地形图规划、MuJoCo 评测和 Go2-W 全栈 LiDAR 真机部署。实验室官方主页目前明确写明 2026 年研究生名额已满。
- 学生及代表工作：
  - [Zhiqiao Guo](https://github.com/ZhiqiaoGuo) — [Robot-Body-Aware Traversal Risk Graph Planning for Wheeled-Legged Robots in Complex Terrain](https://arxiv.org/abs/2608.16433)

</details>

<details>
<summary><strong>招聘信号</strong></summary>

今日未选入新的高置信、直接相关招聘信号。官方与定向检查未发现新发布、信息足够新且具体、可独立核验，并能优于 `jobs.md` 现有活跃机会的腿足机器人岗位。

上海科技大学 MARS Lab 官方主页明确表示 2026 年研究生名额已满，因此仅作为来源状态记录，不视为可操作机会。

今日未发现需要提出删除的过期条目。

</details>
