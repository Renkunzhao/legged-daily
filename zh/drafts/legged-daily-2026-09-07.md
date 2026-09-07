[English](../../drafts/legged-daily-2026-09-07.md) | **中文**
# 腿足机器人日报 - 2026-09-07

## 摘要
- MulDP 用扩散策略融合深度图历史、本体感知和目标信息，实现 Unitree Go1 自主跑酷导航，并配套新的 QPND 数据集：31 公里、6,400 条轨迹。
- FWBC-VLA 为带机械臂的轮腿四足提供 200 Hz 无力传感器接触估计，同时服务 VLA 动作生成和全身补偿；项目报告持续负载下补偿平均提升 24.5 个百分点。
- BRIDGE 将人形机器人形态与控制联合设计，落地为 88 cm、21 主动自由度、报告成本约 1,500 美元的平台，但完整 CAD、BOM、装配、训练和部署资料仍须等待论文接收后发布。
- EngineAI 发布 Apache-2.0 的 PM01 人形自主导航栈，覆盖 Isaac Lab 训练、Gazebo 仿真、ROS 2 部署、LiDAR 距离图策略，以及 PM01 + Livox Mid-360 真机验证。
- 新论文形成了复旦大学，以及浙江大学、上海人工智能实验室、清华大学、中关村学院、云深处科技、华中科技大学、JoyIn AI 和 CMU 等值得追踪的来源网络；本次未核验到足够新且明确在招的职位。

<details>
<summary><strong>新论文</strong></summary>

### MulDP：面向复杂地形自主四足跑酷导航的多模态扩散策略
- 链接：https://arxiv.org/abs/2609.03984
- 来源：arXiv
- 日期：2026-09-03
- 作者：Kangmai Hu、Yueqi Zhang、Peng Zhai、Xiaoyi Wei、Jiabin Hu、Zhixiang Liu、Quancheng Qian、Lihua Zhang
- 主题：四足机器人 / 自主跑酷 / 扩散策略 / 视觉导航 / 仿真到现实
- 摘要：利用历史与当前深度观测、本体感知和目标信息构建多模态扩散策略，为 Unitree Go1 生成时间连贯、具预判性的速度指令序列，实现自主跑酷导航。
- 备注：配套 QPND 数据集包含 6,400 条轨迹、约 25 万张深度图和 31 公里导航数据，覆盖沟槽、栏杆、楼梯、碎石、箱体、平地和不可通行障碍。论文报告了 Isaac Sim 与真机实验，但本次未核验到公开代码或数据集链接。

### FWBC-VLA：面向接触丰富型移动操作的力感知全身补偿
- 链接：https://arxiv.org/abs/2609.03889
- 来源：arXiv
- 日期：2026-09-03
- 作者：Yutian Zhang、Siyuan Ma、Liwen Yang、Yang Li、Ce Hao、Haozhen Chi、Dong Wei、Qiaojun Yu、Dibo Hou
- 主题：轮腿四足 / 移动操作 / VLA / 全身控制 / 无传感器力估计
- 摘要：提出无需专用力/力矩传感器的力感知接口，从本体感知估计接触，将力历史编码为 VLA 动作解码的 token，并在接触丰富型操作中为下游全身控制器生成修正动作。
- 备注：HSR-Force 以 200 Hz 运行，WL&Arm 数据集包含 5,000 多段遥操作轨迹。开门和擦白板真机实验显示，身体补偿平均贡献 24.5 个百分点，其中带闭门器推门提升 52 点、擦板提升 44 点；本次未核验到代码发布。

### BRIDGE：通过形态—控制协同设计构建面向物理 AI 的开源人形平台
- 链接：https://arxiv.org/abs/2609.03497
- 来源：arXiv
- 日期：2026-09-03
- 作者：Jianren Wang、Letian Qian、Zikai Wang、Weiwei Wu、Junjie Zong、Abhinav Gupta、Deepak Pathak
- 主题：人形机器人 / 形态—控制协同设计 / 动作重定向 / 全身控制 / 开源硬件
- 摘要：以解剖约束、人类动作重定向误差、执行器可行性和闭环动态跟踪共同优化人形形态，并实现为支持行走、平衡及高动态全身动作的 88 cm、21 主动自由度平台。
- 备注：项目页报告整机重 12.5 kg、成本约 1,500 美元，并声明开放代码和设计；但完整 CAD、BOM、装配教程、电气规格以及训练/部署代码需等论文接收后发布，因此当前开源材料尚不完整。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### engineai_navigation
- 链接：https://github.com/engineai-robotics/engineai_navigation
- 类别：强化学习
- 机器人类型：人形机器人
- 仿真器：Isaac Lab / Gazebo
- 部署：仿真与真机
- 摘要：面向 EngineAI PM01 的端到端 PPO 导航栈，将有序 LiDAR 距离图转换为速度指令，并由底层行走策略执行，提供训练、ONNX 导出、ROS 2 仿真和真机部署路径。
- 备注：仓库创建于 2026-09-03，EngineAI 原创代码采用 Apache-2.0，第三方组件许可证单独列明。内容包括 PM01 URDF、SRU 改版 rsl_rl、迷宫地形、Super-LIO 集成，并已在 PM01 + Livox Mid-360 上验证；仿真与真机 ROS 2 包有意使用独立安装树。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### 复旦大学自主四足跑酷团队
- 机构：复旦大学
- arXiv：https://arxiv.org/abs/2609.03984
- 实验室 / 院系：智能机器人与先进制造创新学院
- 关键主题：四足机器人 / 自主跑酷 / 扩散策略 / 视觉导航 / 机器人学习
- 备注：MulDP 展示了一个由通讯作者 Lihua Zhang 牵头的集中型复旦来源网络，方向覆盖多模态导航策略、Isaac Sim 数据生成和 Unitree Go1 真机跑酷。

### 浙江大学牵头的力感知移动操作协作网络
- 机构：浙江大学 / 上海人工智能实验室 / 清华大学 / 中关村学院 / 云深处科技 / 浙江科技大学
- 主页：https://ytydt-reuz.github.io/FWBC-VLA/
- arXiv：https://arxiv.org/abs/2609.03889
- 实验室 / 院系：跨机构论文协作
- 关键主题：轮腿四足 / VLA / 无传感器力估计 / 全身控制 / 移动操作
- 备注：FWBC-VLA 连接了带机械臂轮腿机器人的学术与产业团队，把本体感知接触估计作为语义动作生成和物理稳定控制之间的共享接口。

### 华中科技大学 / JoyIn AI / CMU 人形协同设计网络
- 机构：华中科技大学 / JoyIn AI / 卡内基梅隆大学
- 主页：https://sites.google.com/view/bridgerobot
- arXiv：https://arxiv.org/abs/2609.03497
- 实验室 / 院系：跨机构论文协作
- 关键主题：人形机器人 / 开源硬件 / 形态—控制协同设计 / 动作模仿 / 全身控制
- 备注：BRIDGE 将华中科技大学与 JoyIn AI 的硬件和控制工作，同 CMU 的 Abhinav Gupta、Deepak Pathak 连接起来，是追踪围绕人类动作数据设计紧凑低成本人形平台的有用来源网络。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

本次未从官方来源核验到足够新、明确有效且高置信的腿足机器人招聘机会。EPFL BioRob openings 页面描述了常规 PhD/Postdoc 申请途径，搜索索引文本也提到人形机器人神经力学方向机会，但可见状态信号互相冲突，不足以将某个具体职位列为正在招聘。

</details>
