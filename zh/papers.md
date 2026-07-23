[English](../papers.md) | **中文**
# 论文

> 腿足机器人长期 curated 论文列表。

---

<details>
<summary><strong>基础资料</strong></summary>

### Rigid Body Dynamics Algorithms
- Link: resources/books/Rigid%20Body%20Dynamics%20Algorithms.pdf
- Source: book
- Topics: dynamics / rigid body dynamics / fundamentals
- Summary: 刚体动力学算法的基础资料。

### 仿人机器人
- Link: resources/books/仿人机器人.pdf
- Source: book
- Topics: humanoid / fundamentals
- Summary: 仿人机器人方向的中文书籍资源。

### Robot Dynamics Lecture Notes - ETH
- Link: https://ethz.ch/content/dam/ethz/special-interest/mavt/robotics-n-intelligent-systems/rsl-dam/documents/RobotDynamics2017/RD_HS2017script.pdf
- Source: lecture notes
- Topics: robot dynamics / fundamentals
- Summary: ETH 机器人动力学课程讲义。

</details>

<details>
<summary><strong>基于学习的仿真</strong></summary>

### A review of learning-based dynamics models for robotic manipulation
- Link: https://www.science.org/doi/epdf/10.1126/scirobotics.adt1497
- Source: Science Robotics
- Topics: learning-based simulation / dynamics models / manipulation
- Summary: 面向机器人操作的 learning-based dynamics models 综述。

### Robotic World Model: A Neural Network Simulator for Robust Policy Optimization in Robotics
- Link: https://sites.google.com/view/roboticworldmodel
- Source: project page
- Topics: world model / simulation / policy optimization
- Summary: 用于机器人鲁棒策略优化的神经网络仿真器。
- Notes: Code: https://github.com/leggedrobotics/robotic_world_model.git。

### Uncertainty-Aware Robotic World Model Makes Offline Model-Based Reinforcement Learning Work on Real Robots
- Link: https://sites.google.com/view/uncertainty-aware-rwm
- Source: project page
- Topics: world model / offline RL / model-based reinforcement learning
- Summary: 面向真实机器人 offline model-based RL 的 uncertainty-aware robotic world model。

### Neural Robot Dynamics
- Link: https://neural-robot-dynamics.github.io/
- Source: project page
- Topics: robot dynamics / learned dynamics
- Summary: 聚焦 neural robot dynamics 的项目。

### Batched Differentiable Rigid Body Dynamics in PyTorch for GPU-Accelerated Robot Learning
- Link: https://arxiv.org/abs/2605.31481
- Source: arXiv
- Date: 2026-05-29
- Authors: Yue Wang, Yanran Xu, Wenbo Wu, Chuanhang Qiu, Zhaoxing Li
- Topics: 机器人动力学 / 可微仿真 / PyTorch / GPU 加速 / 强化学习 / 四足机器人
- Summary: 提出 BARD，一个 PyTorch 原生的批量可微刚体动力学库，支持 GPU 与 autograd；论文报告其数值上匹配 Pinocchio，并在 FK/Jacobian 吞吐上有大幅提升，还集成到 Isaac Lab AMP 的 11 自由度带脊柱四足训练流水线中。
- Notes: 仓库：https://github.com/YueWang996/bard-pytorch-dynamics。


### UniLab: A Heterogeneous Architecture for Robot RL Beyond GPU-Dominant Paradigms
- Link: https://arxiv.org/abs/2605.30313
- Source: arXiv / project page / GitHub
- Date: 2026-05-28; v3 on 2026-06-02
- Authors: Yufei Jia, Zhanxiang Cao, Mingrui Yu, Heng Zhang, Shenyu Chen, Dixuan Jiang, Meng Li, Xiaofan Li, Yiyang Liu, Junzhe Wu, Zheng Li, XiLin Fang, Ting-Yu Tsui, Shengcheng Fu, Haoyang Li, Anqi Wang, Zifan Wang, Dongjie Zhu, Chenyu Cao, Zhenbiao Huang, Ziang Zheng, Jie Lu, Xin Ma, Zhengyang Wei, Xiang Zhao, Tianyue Zhan, Ye He, Yuxiang Chen, Yizhou Jiang, Yue Li, Haizhou Ge, Yuhang Dong, Fan Jia, Ziheng Zhang, Meng Zhang, Xiwa Deng, Zhixing Chen, Hanyang Shao, Chenxin Dong, Yixuan Li, Yizhi Chen, Bokui Chen, Kaifeng Zhang, Hanqing Cui, Yusen Qin, Ruqi Huang, Lei Han, Tiancai Wang, Xiang Li, Yue Gao, Guyue Zhou
- Topics: robot RL / simulation infrastructure / heterogeneous CPU-GPU training / MuJoCoUni / MotrixSim / cross-platform training / quadruped / humanoid / wheeled-legged / loco-manipulation
- Summary: 提出 UniLab，一个面向机器人 RL 的异构 CPU-simulation / GPU-learning 架构；它通过共享内存缓冲与同步机制，将 CPU 并行物理 rollout 与 GPU 策略更新解耦，并使用 MuJoCoUni 和 MotrixSim 后端；论文报告在代表性机器人控制任务上取得 3-10× 端到端训练效率提升，同时支持 CUDA、Apple Silicon、AMD ROCm 和 Intel XPU。
- Notes: 项目页：https://unilabsim.github.io/。官方代码：https://github.com/unilabsim/UniLab。对腿足机器人相关，因为已发布任务覆盖 Go1/Go2 四足、Unitree G1 walking / motion tracking / whole-body skills、Go2W 轮足运动，以及 Go2+arm 移动操作。
</details>

<details>
<summary><strong>人形机器人运动</strong></summary>

### Learning Whole-Body Humanoid Locomotion via Motion Generation and Motion Tracking
- Link: https://arxiv.org/abs/2604.17335
- Source: arXiv
- Date: 2026-04-19
- Authors: Zewei Zhang, Kehan Wen, Michael Xu, Junzhe He, Chenhao Li, Takahiro Miki, Clemens Schwarke, Chong Zhang, Xue Bin Peng, Marco Hutter
- Topics: humanoid / locomotion / whole-body control / robot learning / perception / sim-to-real
- Summary: 面向 Unitree G1 的 terrain-aware 全身人形运动框架，结合 diffusion-based motion generation 与 RL motion tracking，并展示硬件越障结果。
- Notes: ETH / RSL 强信号，也是当前 whole-body humanoid locomotion 的重要参考。

### SoftMimic: Learning Compliant Whole-body Control from Examples
- Link: https://arxiv.org/abs/2510.17792
- Source: arXiv
- Date: 2025-10-20
- Authors: Gabriel B. Margolis, Michelle Wang, Nolan Fey, Pulkit Agrawal
- Topics: humanoid / whole-body control / imitation learning / compliance / reinforcement learning / sim-to-real / Unitree G1
- Summary: 从示例动作学习人形机器人柔顺全身控制的方法：先用 inverse kinematics 生成可行的柔顺动作增强数据，再训练 RL policy 在跟踪参考动作的同时吸收外界扰动，而不是刚性纠偏。
- Notes: 项目页: https://gmargo11.github.io/softmimic/；代码: https://github.com/Improbable-AI/softmimic。论文标注机构为 MIT Improbable AI Lab，通讯作者为 Gabriel B. Margolis 和 Michelle Wang。

### BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion
- Link: https://arxiv.org/abs/2508.08241
- Source: arXiv
- Date: 2025-08-11
- Authors: Qiayuan Liao, Takara E. Truong, Xiaoyu Huang, Yuman Gao, Guy Tevet, Koushil Sreenath, C. Karen Liu
- Topics: humanoid / motion tracking / guided diffusion / whole-body control / versatile control
- Summary: 用 guided diffusion 将 motion-tracking 式人形控制扩展到更通用的行为生成与适配。
- Notes: 适合与 residual learning、skill blending 等“超越纯 tracking”的路线对照。

### SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2511.07820
- Source: Science Robotics / arXiv
- Date: 2025-11-11
- Authors: Zhengyi Luo, Ye Yuan, Tingwu Wang, Chenran Li, Fernando Castañeda, Sirui Chen, Zi-Ang Cao, Jiefeng Li, David Minor, Qingwei Ben, Jinhyung Park, David Sami, Zi Wang, Xingye Da, Runyu Ding, Cyrus Hogg, Lina Song, Edy Lim, Eugene Jeong, Tairan He, Haoru Xue, Wenli Xiao, Simon Yuen, Jan Kautz, Yan Chang, Umar Iqbal, Linxi "Jim" Fan, Yuke Zhu
- Topics: humanoid / whole-body control / motion tracking / large-scale training / natural motion / GEAR
- Summary: NVIDIA GEAR 方向的大规模人形全身 motion tracking 工作，目标是在广泛人类动作数据上学习自然的全身控制。
- Notes: 后续跟踪代码、actuator modeling、部署和数据规模化细节时，应与现有 SONIC/GEAR 仓库条目关联。

### HoloMotion-1 Technical Report
- Link: https://arxiv.org/abs/2605.15336
- Source: arXiv technical report
- Date: 2026-05-14
- Authors: Maiyue Chen, Kaihui Wang, Bo Zhang, Xihan Ma, Zhiyuan Yang, Yi Ren, Qijun Huang, Zihao Zhu, Yucheng Wang, Zhizhong Su
- Topics: humanoid / motion learning / whole-body control / technical report
- Summary: HoloMotion-1 相关技术报告，可作为近期人形动作学习和全身技能生成方向的参考。
- Notes: 后续重点核查项目资产、数据/代码可用性，以及它和 SONIC、BeyondMimic 式 tracking pipeline 的差异。

</details>

<details>
<summary><strong>四足运动</strong></summary>

### Learning quadrupedal locomotion on deformable terrain
- Link: https://www.science.org/doi/pdf/10.1126/scirobotics.ade2256
- Source: Science Robotics
- Topics: quadruped / deformable terrain / locomotion / adaptation
- Summary: 面向可变形地形的学习式四足运动，强调成功迁移。

### RMA: Rapid Motor Adaptation for Legged Robots
- Link: https://arxiv.org/pdf/2107.04034
- Source: arXiv
- Topics: locomotion / adaptation / legged robots
- Summary: 腿足机器人的快速运动适应方法。

### Extreme Parkour with Legged Robots
- Link: https://extreme-parkour.github.io/
- Source: project page / arXiv
- Date: 2023
- Authors: Xuxin Cheng, Kexin Shi, Ananye Agarwal, Deepak Pathak
- Topics: quadruped / parkour / vision-based locomotion / reinforcement learning / sim-to-real / depth camera
- Summary: 在仿真中训练单个端到端神经网络策略，让低成本四足机器人直接基于前向深度图执行动态 parkour，展示高跳、跳远、倒立、倾斜坡道通过，并能泛化到新障碍路线。
- Notes: Isaaclab_Parkour 仓库引用的基础工作；适合作为视觉敏捷运动和 parkour 式腿足 RL 的锚点论文。

### Robot Parkour Learning
- Link: https://robot-parkour.github.io/
- Source: CoRL 2023 / project page
- Date: 2023
- Authors: Ziwen Zhuang, Zipeng Fu, Jianren Wang, Christopher G. Atkeson, Sören Schwertfeger, Chelsea Finn, Hang Zhao
- Topics: quadruped / parkour / vision-based locomotion / reinforcement learning / distillation / sim-to-real / depth camera
- Summary: 先用强化学习获得多种四足 parkour 技能，再蒸馏成单个基于自我中心深度图的视觉策略，使机器人能在真实环境中自主选择并执行越高障碍、跨大间隙、钻低障碍、穿窄缝和奔跑等技能。
- Notes: CoRL 2023 Oral，Best Systems Paper Award Finalist；官方代码：https://github.com/ZiwenZhuang/parkour。

### Evaluation of an Actuated Spine in Agile Quadruped Locomotion
- Link: https://arxiv.org/abs/2605.07988
- Source: arXiv
- Date: 2026-05-08
- Authors: Nico Bohlinger, Piotr Kicki, Davide Tateo, Krzysztof Walas, Jan Peters
- Topics: quadruped / locomotion / morphology / agile locomotion / simulation
- Summary: 研究 1-DOF 主动脊柱在高速奔跑、楼梯、坡面、跨栏和爬行等四足敏捷任务中的作用。
- Notes: 是 morphology-aware locomotion design 的有用参考，而不仅是控制器比较。

### Learning to Balance Motor Thermal Safety and Quadrupedal Locomotion Performance with Residual Policy
- Link: https://arxiv.org/abs/2605.27046
- Source: arXiv
- Date: 2026-05-26
- Authors: Yuhang Wan, Weixian Lin, Letian Qian, Yiqi Zou, Weiwei Wu, Shengwei Wu, Chuanlin Zhao, Xin Luo
- Topics: quadruped / reinforcement learning / motor thermal safety / residual policy / sim-to-real / Unitree A1
- Summary: 将全身电机热模型集成进四足强化学习，在名义地形运动策略之上训练残差策略，让机器人在轨迹跟踪性能与电机过热风险之间权衡。
- Notes: Unitree A1 真机实验报告在 3 kg 负载下可在多种地形稳定行走超过 13 分钟，而名义策略约 5 分钟后出现电机过热。

### Discovery of skill-switching criteria for learning agile quadruped locomotion
- Link: https://arxiv.org/abs/2502.06676
- Source: Frontiers in Robotics and AI / arXiv
- Date: 2025-02-10
- Authors: Wanming Yu, Fernando Acero, Vassil Atanassov, Chuanyu Yang, Ioannis Havoutis, Dimitrios Kanoulas, Zhibin Li
- Topics: quadruped / agile locomotion / skill switching / reinforcement learning / hierarchical control
- Summary: 研究如何发现 locomotion skills 之间的切换判据，使四足机器人能更稳定地执行敏捷运动。
- Notes: 适合与 mixture-of-experts routing 和统一多技能策略中的技能选择机制对照。Best Paper: no confirmed。

### MoE-Loco: Mixture of Experts for Multitask Locomotion
- Link: https://arxiv.org/abs/2503.08564
- Source: IROS 2025 / arXiv
- Date: 2025-03-11
- Authors: Runhan Huang, Shaoting Zhu, Yilun Du, Hang Zhao
- Topics: locomotion / multitask learning / mixture of experts / reinforcement learning / expert routing
- Summary: 将 mixture-of-experts 架构用于多任务 locomotion，强调不同专家在运动任务中的专门化和路由。
- Notes: 是腿足控制中 MoE-style policy decomposition 的有用锚点。Best Paper: no confirmed。

### Learning Multi-Skill Legged Locomotion Using Conditional Adversarial Motion Priors
- Link: https://arxiv.org/abs/2509.21810
- Source: arXiv
- Date: 2025-09-26
- Authors: Ning Huang, Zhentao Xie, Qinchuan Li
- Topics: legged locomotion / multi-skill learning / conditional adversarial motion priors / imitation learning / reinforcement learning
- Summary: 使用 conditional adversarial motion priors 学习多技能腿足运动，把 AMP 式模仿目标和 skill-conditioned control 连接起来。
- Notes: 后续重点看条件表示、discriminator 结构和 skill-library 假设，并与 MoE / skill-switching 方法对比。

</details>

<details>
<summary><strong>数据驱动优化</strong></summary>

### Data-Enabled Predictive Control: In the Shallows of the DeePC
- Link: https://arxiv.org/pdf/1811.05890
- Source: arXiv
- Topics: data-driven control / predictive control / DeePC
- Summary: DeePC 方向的数据驱动预测控制基础论文。

### Toward a Data-Driven Template Model for Quadrupedal Locomotion
- Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9799758
- Source: IEEE
- Topics: quadruped / template models / data-driven control
- Summary: 面向四足运动的数据驱动 template model 工作。

### Deep DeePC: Data-enabled predictive control with low or no online optimization using deep learning
- Link: https://aiche.onlinelibrary.wiley.com/doi/pdf/10.1002/aic.18644
- Source: journal article
- Topics: DeePC / deep learning / predictive control
- Summary: 使用深度学习降低或消除在线优化需求的 Deep DeePC。

### prescyent
- Link: https://github.com/hucebot/prescyent
- Source: GitHub
- Topics: data-driven control / trajectory prediction
- Summary: Python 数据驱动轨迹预测库。

</details>

<details>
<summary><strong>灵巧操作</strong></summary>

### SimToolReal: An Object-Centric Policy for Zero-Shot Dexterous Tool Manipulation
- Link: https://simtoolreal.github.io/
- Source: project page
- Topics: dexterous manipulation / sim-to-real / policy learning
- Summary: 面向 zero-shot dexterous tool manipulation 的 object-centric policy。
- Notes: PDF: https://arxiv.org/pdf/2602.16863 and code: https://github.com/tylerlum/simtoolreal。

### TactAlign: Human-to-Robot Policy Transfer via Tactile Alignment
- Link: https://yswi.github.io/tactalign/
- Source: project page
- Topics: dexterous manipulation / tactile alignment / policy transfer
- Summary: 通过 tactile alignment 进行人到机器人的策略迁移。
- Notes: PDF: https://arxiv.org/pdf/2602.13579。

</details>

<details>
<summary><strong>数据集与基准</strong></summary>

### GrandTour: A Legged Robotics Dataset in the Wild for Multi-Modal Perception and State Estimation
- Link: https://arxiv.org/abs/2602.18164
- Source: arXiv
- Date: 2026-02-20
- Authors: Jonas Frey, Turcan Tuna, Frank Fu, Katharine Patterson, Tianao Xu, Maurice Fallon, Cesar Cadena, Marco Hutter
- Topics: quadruped / dataset / perception / state estimation / navigation / SLAM
- Summary: ETH RSL 用 ANYmal-D 在多样室内外环境中采集的大规模多模态腿足机器人数据集，包含高精度 ground truth。
- Notes: 对需要真实腿足数据的感知、状态估计和导航工作特别重要。

</details>

<details>
<summary><strong>综述</strong></summary>

### A Survey of Legged Robotics in Non-Inertial Environments: Past, Present, and Future
- Link: https://arxiv.org/abs/2604.20990
- Source: arXiv
- Date: 2026-04-22
- Authors: I-Chia Chang, Xinyan Huang, Tzu-Yuan Lin, Sangli Teng, Wenjing Li, Maani Ghaffari, Jingang Yi, Yan Gu
- Topics: legged robots / locomotion / state estimation / control / dynamic environments
- Summary: 关于腿足机器人在移动、倾斜或加速支撑面上的建模、估计与控制挑战综述。
- Notes: 是非静止地面运动方向的良好 orientation entry。

### Learning Perceptive Legged Robot Locomotion in the Real World: A Systematic Review
- Link: https://ieeexplore.ieee.org/document/11313692
- Source: IEEE Robotics & Automation Magazine
- Date: 2026-04-17
- Authors: Irfan Tito Kurniawan, Wei Zhu, Dai Owaki, Mitsuhiro Hayashibe
- Topics: perceptive locomotion / legged robots / learning / real-world deployment / review
- Summary: 学习式真实世界感知腿足运动系统综述，覆盖能力、感知融合方法和开放挑战。
- Notes: 适合用来定位新的 perception-for-locomotion 工作。

</details>

<details>
<summary><strong>综述与集合</strong></summary>

### many-quadrupeds
- Link: https://github.com/beduffy/many-quadrupeds
- Source: GitHub
- Topics: survey / collection / quadrupeds
- Summary: awesome-style 四足机器人相关资源集合。

</details>

---

<details>
<summary><strong>腿足状态估计与动力学</strong></summary>

### PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots
- Link: https://arxiv.org/abs/2605.17681
- Source: arXiv / RSS 2026
- Date: 2026-05-22
- Authors: Jiarong Kang, Kunzhao Ren, Linxuan Wang, Jingbo Wang, Tao Pang, Xiaobin Xiong
- Topics: legged robots / humanoid robots / state estimation / motion estimation / contact dynamics / inertial parameters
- Summary: 基于 MAP 的运动估计方法，把运动学测量和执行器命令修正为动力学一致轨迹，同时估计腿足和人形机器人的接触力与惯性参数。
- Notes: 适合继续跟踪其物理一致机器人数据重建、力/接触标注相关代码或数据释放。

</details>

---

<details>
<summary><strong>人形导航与移动操作</strong></summary>

### Learning to Evolve: Multi-modal Interactive Fields for Robust Humanoid Navigation in Dynamic Environments
- Link: https://arxiv.org/abs/2605.21935
- Source: arXiv / RSS 2026 / project page
- Date: 2026-05-21
- Authors: Peifeng Jiang, Hong Liu, Jin Jin, Wenshuai Wang, Xia Li
- Topics: humanoid / navigation / semantic mapping / 3D Gaussian Splatting / dynamic environments / Unitree G1
- Summary: MIF 结合 semantic 3D Gaussian Splatting、memory updates 和 task-driven geometry reconstruction，用于动态室内环境中 Unitree G1 稳健导航。
- Notes: 具有真实办公室结果的 perception-aware humanoid navigation 强信号。

### SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework
- Link: https://arxiv.org/abs/2605.20373
- Source: arXiv / project page
- Date: 2026-05-19
- Authors: Tianshu Wu, Xiangqi Kong, Yue Chen, Qize Yu, Hang Ye, Jia Li, Yizhou Wang, Hao Dong
- Topics: humanoid / loco-manipulation / human video / imitation learning / reinforcement learning / sim-to-real
- Summary: 将非结构化人类视频转成可部署 humanoid loco-manipulation skills 的框架，包含 interaction-prior extraction、physical refinement 和 hierarchical policy learning。
- Notes: 对减少 humanoid loco-manipulation 中 reward design 与遥操作负担有参考价值。

### Learning Terrain-Aware Whole-Body Control for Perceptive Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2605.31343
- Source: arXiv
- Date: 2026-05-29
- Authors: Sikai Guo, Yudong Zhong, Guoyang Zhao, Botao Dang, Zhihai Bi, Jun Ma
- Topics: 腿足移动操作 / 全身控制 / 地形感知 / 强化学习 / sim-to-real
- Summary: 提出 TA-WBC，一个面向腿足移动操作机器人的地形感知全身控制框架；它结合混合外感知编码、基于足端接触平面的末端采样，以及双策略蒸馏，在仿真和真实实验中提升复杂地形下的移动操作稳定性和可达性。
- Notes: 与腿足方向强相关，重点在地形拓扑感知、姿态/落足自适应和 legged loco-manipulation 的统一控制。

### Gaze2Act: Gaze-Conditioned Vision-Language-Action Policies for Interactive Robot Manipulation
- Link: https://arxiv.org/abs/2605.30282
- Source: arXiv
- Date: 2026-05-28
- Authors: Kuangji Zuo, Gen Li, Bofan Lyu, Yanshuo Lu, Boyu Ma, Shijia Han, Xinyu Zhou, Xichen Yuan, Chuhao Zhou, Jiaqi Bai, Geng Li, Jianfei Yang
- Topics: 人形机器人 / VLA / 人机交互 / gaze conditioning / 操作 / Unitree G1
- Summary: 用人类视线作为连续意图信号来增强 VLA 操作策略，将第一视角 gaze 映射到机器人视角，并在 Unitree G1 人形机器人上完成 7 类、16 个真实任务评测。
- Notes: 不是纯 locomotion，但对人形机器人交互与操作栈有价值；项目/GitHub 页面：https://github.com/zuo-kuangji/Gaze2Act。

### GRAIL: Generating Humanoid Loco-Manipulation from 3D Assets and Video Priors
- Link: https://arxiv.org/abs/2606.05160
- Source: arXiv
- Date: 2026-06-03
- Authors: Tianyi Xie, Haotian Zhang, Jinhyung Park, Zi Wang, Bowen Wen, Jiefeng Li, Xueting Li, Qingwei Ben, Haoyang Weng, Yufei Ye, David Minor, Tingwu Wang, Chenfanfu Jiang, Sanja Fidler, Jan Kautz, Linxi Fan, Yuke Zhu, Zhengyi Luo, Umar Iqbal, Ye Yuan
- Topics: humanoid / loco-manipulation / synthetic data / video foundation models / 3D assets / sim-to-real / Unitree G1
- Summary: 提出 GRAIL，一个全数字化数据生成流水线：组合 3D 资产、可用于仿真的场景、机器人比例角色和视频基础模型先验，恢复 metric 4D human-object interaction 轨迹，再重定向到人形机器人并训练面向操作和地形穿越的 task-general trackers；论文报告生成 20,000+ 序列，并在 Unitree G1 上实现 84% 物体抓取成功率和 90% 爬楼梯成功率。
- Notes: 项目页：https://research.nvidia.com/labs/dair/grail/。官方代码：https://github.com/NVlabs/GRAIL。它是近期 teleoperation-free 人形移动操作数据工作的强相关补充。

### Humanoid-GPT: Scaling Data and Structure for Zero-Shot Motion Tracking
- Link: https://arxiv.org/abs/2606.03985
- Source: arXiv / CVPR 2026
- Date: 2026-06-02
- Authors: Zekun Qi, Xuchuan Chen, Dairu Liu, Chenghuai Lin, Yunrui Lian, Sikai Liang, Zhikai Zhang, Yu Guan, Jilong Wang, Wenyao Zhang, Xinqiang Yu, He Wang, Li Yi
- Topics: humanoid / whole-body control / motion tracking / Transformer / large-scale motion data / zero-shot generalization
- Summary: 提出 Humanoid-GPT，一个用于全身控制的 GPT-style causal Transformer；它在 2B-frame 重定向 motion corpus 上预训练，语料结合主要 mocap 数据集和自采数据，目标是对未见动态动作和控制任务进行 zero-shot tracking。
- Notes: 已被 CVPR 2026 接收。今天快速检查中没有验证到真机细节或公开代码；建议先作为「数据规模化 / 架构」高信号条目跟踪，不把它写成部署结论。

### CoRe-MoE: Contrastive Reweighted Mixture of Experts for Multi-Terrain Humanoid Locomotion with Gait Adaptation
- Link: https://arxiv.org/abs/2606.04718
- Source: arXiv
- Date: 2026-06-03
- Authors: Kailun Huang, Zikang Xie, Yanzhe Xie, Panpan Liao, Fanghai Zhang, Yanheng Mai, Wenhao Xu, Yunheng Wang, Renjing Xu, Haohui Huang
- Topics: humanoid / reinforcement learning / mixture of experts / gait transition / terrain adaptation / Unitree G1
- Summary: 提出 CoRe-MoE，一个两阶段 RL 框架：先学习稳定的步行/跑步切换，再加入 terrain-aware mixture-of-experts 分支，并用 contrastive gating 促进专家分化和多地形适应；摘要报告了在 Unitree G1 上零样本部署于楼梯、斜坡、台阶、障碍物和户外非结构化地形。
- Notes: arXiv 摘要列出的机构包括 HKUST(GZ)、South China Agricultural University 和 Guangdong University of Technology；通讯作者为 Renjing Xu 和 Haohui Huang。

### SkillBlender: Towards Versatile Humanoid Whole-Body Loco-Manipulation via Skill Blending
- Link: https://arxiv.org/abs/2506.09366
- Source: arXiv
- Date: 2025-06-11
- Authors: Yuxuan Kuang, Haoran Geng, Amine Elhafsi, Tan-Dzung Do, Pieter Abbeel, Jitendra Malik, Marco Pavone, Yue Wang
- Topics: humanoid / loco-manipulation / skill blending / whole-body control / reinforcement learning
- Summary: 研究如何 blend 人形全身技能，使 locomotion 和 manipulation 行为能组合成更通用的移动操作策略。
- Notes: 是 residual learning、latent VLA 和 motion discovery 路线的重要对照。

### ResMimic: From General Motion Tracking to Humanoid Whole-Body Loco-Manipulation via Residual Learning
- Link: https://arxiv.org/abs/2510.05070
- Source: arXiv
- Date: 2025-10-06
- Authors: Siheng Zhao, Yanjie Ze, Yue Wang, C. Karen Liu, Pieter Abbeel, Guanya Shi, Rocky Duan
- Topics: humanoid / loco-manipulation / residual learning / motion tracking / whole-body control
- Summary: 用 residual learning 将通用人形 motion tracking 能力适配到 whole-body loco-manipulation 行为。
- Notes: 是 BeyondMimic、SkillBlender 和 ULC 等控制器设计的强对照参考。

### WholeBodyVLA: Towards Unified Latent VLA for Whole-Body Loco-Manipulation Control
- Link: https://arxiv.org/abs/2512.11047
- Source: ICLR 2026 Poster / arXiv
- Date: 2025-12-11
- Authors: Haoran Jiang, Jin Chen, Qingwen Bu, Li Chen, Modi Shi, Yanjie Zhang, Delong Li, Chuanzhe Suo, Chuang Wang, Zhihui Peng, Hongyang Li
- Topics: humanoid / VLA / latent actions / whole-body control / loco-manipulation
- Summary: 提出面向人形 whole-body loco-manipulation control 的 unified latent VLA 方向，把语言/视觉/动作抽象与 locomotion-aware manipulation 联系起来。
- Notes: 应与现有 WholeBodyVLA 仓库/资源条目关联。Best Paper: no confirmed。

### Learning a Unified Policy for Position and Force Control in Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2505.20829
- Source: CoRL 2025 / arXiv
- Date: 2025-05-27
- Authors: Peiyuan Zhi, Peiyang Li, Jianqin Yin, Baoxiong Jia, Siyuan Huang
- Topics: legged loco-manipulation / position control / force control / unified policy / whole-body control
- Summary: 学习同时处理位置控制和力控制的统一策略，是接触丰富腿足移动操作的重要参考。
- Notes: 用户标注为 CoRL 2025 Best Paper；优先精读 objective structure 和真实机器人证据。

### ULC: A Unified and Fine-Grained Controller for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2507.06905
- Source: arXiv / in submission
- Date: 2025-07-09
- Authors: Wandong Sun, Luying Feng, Baoshi Cao, Yang Liu, Yaochu Jin, Zongwu Xie
- Topics: humanoid / loco-manipulation / unified controller / fine-grained control / whole-body control
- Summary: 提出面向人形 loco-manipulation 的统一细粒度控制器，补充 skill blending、residual learning 和 latent VLA 等路线。
- Notes: 后续重点检查 controller granularity、command/action interface 和 manipulation task suite。

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Source: arXiv
- Date: 2026-06-04
- Authors: Ilyass Taouil, Michal Ciebelski, Shafeef Omar, Haizhou Zhao, Angela Dai, Aaron M. Johnson, Majid Khadiv
- Topics: humanoid / loco-manipulation / motion discovery / LLM-guided search / kinodynamic optimization / reinforcement learning
- Summary: 通过 LLM 引导的进化搜索、kinodynamic 轨迹优化、剪枝和 RL tracking policies，从零发现接触丰富、长时域的人形移动操作动作。
- Notes: 这是不主要依赖遥操作或人体动作重定向的自动技能发现路线，值得重点跟踪。

</details>

---

<details>
<summary><strong>轮足与可变形机器人</strong></summary>

### WiXus: A Wheeled-Legged Robot with Wire-Driven Environmental Utilizing to Integrate Mobility and Manipulation
- Link: https://arxiv.org/abs/2605.20932
- Source: arXiv / ICRA 2026 / project page
- Date: 2026-05-20
- Authors: Shintaro Inoue, Kento Kawaharazuka, Temma Suzuki, Sota Yuzaki, Kei Okada
- Topics: wheeled-legged robot / mobility / manipulation / environmental wire actuation / hardware system
- Summary: 使用环境钢索锚定的轮足硬件系统，让腿同时支持移动、操作和工具使用角色。
- Notes: JSK 网络中值得关注的 mobility-manipulation integration 信号。

### MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots
- Link: https://arxiv.org/abs/2605.13058
- Source: arXiv
- Date: 2026-05-13
- Authors: Yuqi Li, Peng Zhai, Yueqi Zhang, Xiaoyi Wei, Quancheng Qian, Zhengxu He, Qianxiang Yu, Lihua Zhang
- Topics: wheeled-legged robots / reinforcement learning / multi-skill control / proprioceptive control / sim-to-real
- Summary: 面向轮足机器人的统一多技能控制架构，目标是在 Unitree Go2-W 等平台上整合多种运动技能。
- Notes: 是轮足机器人统一多技能控制的实用参考；已纳入用户指定的 multi-skill reading cluster。

### X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation
- Link: https://arxiv.org/abs/2604.21541
- Source: arXiv
- Date: 2026-04-28
- Authors: Shengjie Wang, Hui Zhang, Zixuan Wu, Wenhao Yu, Guifeng Yuan, Guohui Tian, Wenhao Zhang, Junyao Gao, Weijia Liu, Zhennan Tang, Jing Peng, Weixia Liu, Wensheng Zhang, Qiang Huang
- Topics: humanoid / wheeled-legged robot / transformable robot / whole-body control / reinforcement learning / manipulation
- Summary: 可在人形与轮足模式之间切换的高自由度机器人，使用 RL 全身控制实现混合移动和操作。
- Notes: 双模式人形移动方向的有用硬件系统参考。

</details>

---

<details>
<summary><strong>2026 年 7 月日报新增论文</strong></summary>

### Athena-WBC: Capability-Aligned Policy Experts for Long-Tail Humanoid Whole-Body Control
- 链接: https://arxiv.org/abs/2607.04837
- 来源: arXiv
- 日期: 2026-07-06；v2 2026-07-07
- 作者: Yuan Jiang, Ningyuan Zhang, Xicun Yang, Yuzhi Jiang, Jie Chen
- 主题: 人形机器人、全身控制、动作跟踪、teacher-student 蒸馏、策略专家、强化学习
- 摘要: Athena-WBC 面向全尺寸人形机器人动作跟踪中的长尾失败问题：先把困难动作路由给能力对齐的 dynamic / balance 专家，再把 privileged teachers 蒸馏成一个可部署控制器，并用 RL 微调。
- 备注: 对人形 motion prior / 全身控制跟踪管线是高信号条目，因为它强调失败不只是数据曝光不足，也来自训练 recipe 与实际诱导能力之间的错配。

### Calf-Integrated Arms for Bimanual Quadruped Loco-Manipulation
- 链接: https://arxiv.org/abs/2607.06186
- 来源: arXiv
- 日期: 2026-07-07
- 作者: Yan Pan, Yuanchuan Ren, Chipui Chan, Jingcheng Sun, Chengxu Zhou
- 主题: 四足机器人、移动操作、机器人构型设计、双手操作、VLM 技能编排、Unitree Go2
- 摘要: 该论文在 Unitree Go2 的两个前小腿上各集成一个带直线滑轨、两个转动关节和夹爪的机械臂，使机器人能四足着地完成地面高度双手操作，并用 VLM 在技能边界选择预定义技能。
- 备注: 摘要中的验证目前是仿真，但这种构型是 trunk-mounted arm 和 leg-as-manipulator 方案之外的一个有辨识度方向。

### WristMimic: Full-Body Humanoid Control with Wrist-Guided Manipulation
- 链接: https://arxiv.org/abs/2607.06438
- 来源: arXiv；ECCV 2026 接收
- 日期: 2026-07-07
- 作者: Wongyun Yu, Youngwoon Kim, Minsu Cho
- 主题: 人形机器人、全身控制、人类-物体交互、重定向、操作、接触丰富控制
- 摘要: WristMimic 在重定向人类物体交互演示时，只对无接触的身体与腕部做运动学跟踪，让手指通过物体跟踪和接触结果学习抓取 / 操作，从而支持跨手部构型的 finger-agnostic 迁移。
- 备注: 更偏人形全身操作与动作重定向，不是纯 locomotion，但对 full-body interaction 很有参考价值。

### Human Motion Priors for Scalable Robot Learning Across Morphologies
- 链接: https://arxiv.org/abs/2606.30290
- 来源: arXiv
- 日期: 2026-06-29
- 作者: Guillaume Sartoretti 等
- 主题: 跨形态重定向、机器人学习、四足、六足、四足机械臂、privileged RL、行为先验、遥操作、文本条件运动
- 摘要: X-Morph 将人类运动转化为非人形腿足机器人的可部署运动和移动操作策略：先把人类动作重定向为机器人参考轨迹，再用 privileged RL 跟踪，并蒸馏为因果学生策略。
- 备注: 该工作直接面向非人形腿足机器人运动数据稀缺问题，也与 ABot-C0 的四足运动语料方向互补。

### Semi-Modular Wheel-Legged Quadruped With Agile Bimanual Capability
- 链接: https://arxiv.org/abs/2606.30243
- 来源: arXiv
- 日期: 2026-06-29；v2 2026-07-07
- 作者: Luca Rossini, Arturo Laurenzi, Francesco Ruscelli, Yifang Zhang, Jingcheng Jiang, Giovanbattista Gravina, Lorenzo Baccelliere, Corrado Burchielli, Stefano Cordasco, Luca Muratore, Nikos Tsagarakis
- 主题: 轮腿四足、移动操作、双臂操作、机器人设计、全身控制、强化学习
- 摘要: KYON 是一个半模块化轮腿四足平台，具有可重构下肢和双臂上身；通过基座内置驱动、传动机构、全身控制和 RL 策略，展示动态运动与操作实验。
- 备注: v2 于 2026-07-07 更新；它更像一个高信号硬件形态更新，而不是纯学习方法。

### Immersive Social Interaction with VR and LLM-Assisted Humanoids
- Link: https://arxiv.org/abs/2607.07430
- Source: arXiv
- Date: 2026-07-08
- Authors: Niraj Pudasaini, Geeta Chandra Raju Bethala, Pranav Doma, Anthony Tzes, Yi Fang
- Topics: humanoid / teleoperation / VR / LLM-assisted control / locomotion commands / data collection
- Summary: 描述了基于 Apple Vision Pro 的 Unitree H1 遥操作系统，结合语音控制行走、VR 操作重定向、灵巧手控制和双向社交交互。
- Notes: 新手用户评估中，物体操作成功率为 80%，社交传方块任务成功率为 70%；系统记录的多模态日志被定位为后续模仿学习数据。

### Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report
- Link: https://arxiv.org/abs/2607.07370
- Source: arXiv
- Date: 2026-07-07
- Authors: Xufeng Zhao, Fuzhi Yang, Jianhui Chen, Li Gao, Zhang Meng, Jie Gao, Yao Zheng, Congyang Zhao, Tianxiong Lv, Menglin Yang, Minqi Gu, Yaru Zhao, Wenyu Liu, Honglin Han, Shihui Su, Zixiao Tang, Liu Liu, Mu Xu, Yang Cai, Wenbin Tang
- Topics: quadruped / motion tracking / locomotion / scene interaction / foundation policy / data scaling / deployment
- Summary: 提出 ABot-C0，一个四足机器人 behavior-foundation 系统，围绕多源运动数据管线、flow-matching 通用运动策略、privileged-to-perceptive locomotion，以及统一真实部署栈构建。
- Notes: 摘要称包含 16,074 段物理可行动作片段，项目页尚待发布；后续应继续跟踪代码/数据释放。

### ContactMimic: Humanoid Object Interaction via Contact Control
- Link: https://arxiv.org/abs/2607.08742
- Source: arXiv / project page
- Date: 2026-07-09
- Authors: Xinyao Li, Xialin He, Runpei Dong, Saurabh Gupta
- Topics: humanoid / loco-manipulation / contact control / motion tracking / sim-to-real
- Summary: 在人形机器人 keypoint tracking 中加入显式 body-part 级二值接触指令，使策略在物体交互中能按需产生或抑制物理接触；包含 10 类动作仿真实验与 5 类动作真实验证。
- Notes: 项目页：https://lixinyao11.github.io/contactmimic-page/。它偏 humanoid full-body control / loco-manipulation，但对 Unitree G1 上的真实接触条件交互有跟踪价值。

### Physics-Guided Biomechanical Gait Adaptation for Humanoid Locomotion on Extreme Sloped Terrains
- Link: https://arxiv.org/abs/2607.07830
- Source: arXiv
- Date: 2026-07-08
- Authors: Xuanyu Chen, Mohan Liu, Dengchen Mei, Zhihao Gu, Haitian Zhang, Kaimin Mao, Haiyue Zhu, Shijun Yan, Lin Wang
- Topics: humanoid / locomotion / slope traversal / reinforcement learning / sim-to-real / proprioception
- Summary: 提出 HumoSlope，两阶段 physics-guided 人形机器人运动框架，结合 slope-adaptive ZMP regularizer 与 biomechanical gait adapter；报告了仅靠本体感知在户外草坡上盲行通过最高 62.7% / 32.1 度坡地。
- Notes: 对鲁棒人形 terrain adaptation 很有价值，因为它针对的是连续陡坡上的持续重力偏置，而不是平地或离散障碍。

### ARDY: Autoregressive Diffusion with Hybrid Representation for Interactive Human Motion Generation
- Link: https://arxiv.org/abs/2607.08741
- Source: arXiv / SIGGRAPH 2026 / project page
- Date: 2026-07-09
- Authors: Kaifeng Zhao, Mathis Petrovich, Haotian Zhang, Tingwu Wang, Siyu Tang, Davis Rempe
- Topics: humanoid / human motion generation / interactive locomotion control / diffusion / text-conditioned control
- Summary: 提出流式自回归扩散框架，用于实时、可控的 3D 人体运动生成，支持在线文本提示、运动学约束、路径跟随，以及通过鼠标键盘进行交互式 locomotion 控制。
- Notes: 项目页与计划发布代码/模型：https://research.nvidia.com/labs/sil/projects/ardy/。它不是机器人控制论文，但对人形机器人运动数据生成与交互式策略条件输入有参考价值。

### GIRAF: Towards Generalizable Human Interactions with Articulated Objects
- Link: https://arxiv.org/abs/2607.07880
- Source: arXiv / CVPR 2026 HuMoGen Workshop
- Date: 2026-07-08
- Authors: Xiaohan Zhang, Sebastian Starke, Alexander Winkler, Federica Bogo, Samir Aroudj, Yuting Ye
- Topics: embodied AI / locomotion-to-manipulation transitions / full-body motion generation / articulated objects / contact
- Summary: 提出面向 articulated objects 的文本条件扩散模型，重点生成从接近移动到手-物接触、物体关节运动的全身交互，并强调对未见物体位置和形状的泛化。
- Notes: 不是腿足机器人部署结果，但适合作为人形 loco-manipulation、接触丰富全身行为合成方向的数据/模型信号。

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv / project page
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid / whole-body teleoperation / motion tracking / payload-aware locomotion / reinforcement learning
- Summary: 提出 HEFT，全尺寸人形机器人遥操作框架：部署策略输入嘈杂 VR 参考，训练时用重建后的物理合理动作做 privileged guidance，并用 Windowed Payload Curriculum 学习不同动作片段对应的重载鲁棒性；在 175 cm、65 kg 的 L7 人形机器人上验证转身、前进/后退、下蹲与最高 24 kg 双手负载。
- Notes: 项目页：https://heft.axell.top/。arXiv HTML 标注作者机构为清华大学、RobotEra、上海期智研究院。

### CLAP: Direct VLM-to-VLA Adaptation via Language-Action Grounding
- 链接: https://arxiv.org/abs/2607.08974
- 来源: arXiv / 项目页
- 日期: 2026-07-09
- 作者: Yuri Ishitoya, Jeremy Siburian, Masashi Hamaya, Kuniaki Saito, Cristian C. Beltran-Hernandez, Mai Nishimura
- 主题: vision-language-action models / robot learning / language-action grounding / compact VLA
- 摘要: 提出 CLAP（Causal Language-Action Prediction），在数值动作序列前加入自然语言动作描述，让预训练 VLM 在尽量少改架构的情况下适配成 VLA；单 epoch 微调在 LIBERO 达到 90.8%，并计划开放 0.8B、2B、4B 多尺度权重。
- 备注: 这是 manipulation/VLA 方向，不是腿足专用；但可作为未来人形移动操作 pipeline 的紧凑 VLA 相邻信号继续跟踪。

### Differential Analysis of Multispectral Images for Terrain Identification
- 链接: https://arxiv.org/abs/2607.09319
- 来源: arXiv
- 日期: 2026-07-10
- 作者: Omar Kashmar, Hemendra Arya, Fulvio Mastrogiovanni
- 主题: 地形感知 / 多光谱传感 / 自主导航 / 边缘部署
- 摘要: 提出 DRIFT，一个轻量多光谱地形识别框架，结合原始光谱 band、对光照更鲁棒的 band-ratio 特征和 differential fusion；在 oil-on-soil UAV 多光谱数据和受控 water-on-grass 实验中，相比强基线在光照、材料歧义和噪声下更稳。
- 备注: 它本身不是腿足机器人论文，但对光照/材料变化鲁棒的地形理解，对户外四足和人形导航栈有潜在价值。

### Robust bipedal locomotion on flowable slopes via foot-driven terrain manipulation
- 链接: https://arxiv.org/abs/2607.11855
- 来源: arXiv
- 日期: 2026-07-13
- 作者: Deniz Kerimoglu, Junnosuke Kamohara, Jiyeon Maeng, Ziwon Yoon, Seth Hutchinson, Ye Zhao, Daniel I. Goldman
- 主题: bipedal locomotion / granular terrain / terradynamics / foot morphology / terrain manipulation
- 摘要: 研究双足机器人在颗粒坡面等 flowable terrain 上的运动，用带 cleated feet 的小型 robophysical biped 做系统实验，发现中等 cleat spacing 可以调节基质应力并改善坡面行走，而过稀或过密都会导致性能下降甚至失败。
- 备注: 对户外可变形地形上的腿足机器人很相关；关键启发是 foot design 和 terrain response control 可以成为主动 locomotion mechanism，而不只是鲁棒控制要抵消的误差源。

### SKooP: Symmetric Koopman Predictions for Faster and More Generalizable Legged Robot Locomotion with Reinforcement Learning
- 链接: https://arxiv.org/abs/2607.11624
- 来源: arXiv
- 日期: 2026-07-13
- 作者: Evelyn D'Elia, Weishu Zhan, Giulio Turrisi, Giulio Romualdi, Giuseppe L'Erario, Raffaello Camoriano, Wei Pan, Daniele Pucci
- 主题: legged locomotion / reinforcement learning / symmetry / Koopman models / sample efficiency / sim-to-real transfer
- 摘要: 提出 SKooP，在训练 locomotion policy 的同时学习 Koopman dynamics model，把 Koopman predictions 作为 critic 的 privileged observations，并在 actor、critic、encoder、decoder 中加入 group symmetries，以得到更等变、更容易学习和迁移的腿足 RL 策略。
- 备注: 如果后续 artifact 或 benchmark 细节足够完整，适合进入长期论文列表；也和 iit-DLSLab 一类关注 sample-efficient / transferable locomotion learning 的工作形成连接。

### TAC-LOCO: Unified Whole-Body Control for Quadrupedal TACtile-Informed LOCO-Manipulation
- 链接: https://arxiv.org/abs/2607.10132
- 来源: arXiv
- 日期: 2026-07-11
- 作者: Muqun Hu, Yuhao Zhou, Kabir Ray Malik, Chi Lin, Won Suk Lee, Yu She, Yan Gu
- 主题: quadruped / loco-manipulation / tactile sensing / whole-body control / reinforcement learning / sim-to-real
- 摘要: 提出 TAC-LOCO，一个触觉增强的统一 RL 控制器；它把 tactile array latent features 和 proprioception 融合起来，同时控制 Unitree Go2、机械臂和夹爪，在外力变化的动态移动操作任务中调节身体、末端和抓取稳定性。
- 备注: 论文报告了在 Unitree Go2 + WidowX 250 + tactile gripper 上的 zero-shot hardware deployment，并在 load changes / sudden release 场景下降低抓取力、提升物体稳定性。

### GaitSpan：从行走生长出人形机器人的跑步能力
- 链接：https://arxiv.org/abs/2607.12114
- 来源：arXiv
- 日期：2026-07-13
- 作者：Kwan-Yee Lin、Zilin Wang、Janelle J. Liu、Stella X. Yu
- 主题：人形机器人运动 / 强化学习 / 步态转换 / 仿真到现实
- 摘要：GaitSpan 复用冻结的行走策略结构，通过组合学习得到的内部节律、塑造适合高速运动的动态步幅并加入残差修正，将预训练行走策略扩展为连续速度范围内的行走、慢跑和跑步式运动；作者还报告了跨形态迁移，以及在未见过的仿真和真实地形上的零样本部署。
- 备注：项目页：https://gaitspan2026.github.io/。检查时项目页的代码按钮指向 https://github.com/LeCAR-Lab/GaitSpan/，但该仓库当时尚无法公开访问。

### Agile perceptive multi-skill locomotion for quadrupedal robots in the wild
- 链接: https://arxiv.org/abs/2607.13579
- 来源: Science Robotics / arXiv
- 日期: 2026-07-15
- 作者: Jun-Gill Kang, Jaehyun Park, Tae-Gyu Song, Joon-Ha Kim, Seungwoo Hong, Hae-Won Park
- 主题: 四足机器人 / 感知运动 / 强化学习 / 步态切换 / sim-to-real
- 摘要: APT-RL 先用 18 万条轨迹优化样本预训练基于 Transformer 的潜在运动技能，再通过强化学习适配复杂地形并蒸馏感知模块，最终得到一个可在楼梯、障碍杆、踏脚石、沟隙、林地倒木等场景中自主选择和切换步态的机载策略。
- 备注: 论文于 2026-07-15 发表于 Science Robotics。项目报告机器人跨越 60 cm 台阶时达到 4.25 m/s、下落穿越三级台阶时瞬时峰值达到 6 m/s，并仅依赖机载感知与计算完成 1.1 km 城市场景和 0.34 km 林地路线。项目页: https://skillquadsr.github.io/。核验时未看到公开代码链接。

### EgoHTR: Egocentric 4D Demonstrations of Human Terrain Traversal
- 链接: https://arxiv.org/abs/2607.13472
- 来源: arXiv
- 日期: 2026-07-15
- 作者: Alex Brandes, Haig Conti Georges Sajelian, Manthan Patel, Dominik Hollidt, Chenhao Li, Matthias Heyrman, Oliver Hausdoerfer, Manuel Kaufmann, Xi Wang, Jonas Frey, Angela P. Schoellig, Christian Holz, Marc Pollefeys, Marco Hutter
- 主题: 人形机器人 / 地形穿越 / 人体动作数据集 / 4D 重建 / 模仿学习
- 摘要: EgoHTR 提出场景对齐的第一视角重建流程与数据集，包含 55 段人类复杂地形穿越序列和超过 15 万帧数据，把具有环境上下文的人体动作采集连接到感知运动策略，并在 Unitree G1 上部署重建参考动作。
- 备注: 项目页: https://egohtr.github.io/。论文称重建流程已开源且支持社区扩展，但今日检查到的公开项目站仓库主要暴露网站资源，尚未看到单独、文档完整的代码或数据发布；建议后续复查发布状态。

### Learning Agile Navigation in Crowded Environments for Quadruped Robots
- 链接: https://arxiv.org/abs/2607.15036
- 来源: arXiv
- 日期: 2026-07-16
- 作者: Shuyu Wu, Zeyu Liu, Tianbao Zhang, Fanxing Li, Fangyu Sun, Mingkang Xiong, Wei Xi, Wenxian Yu, Danping Zou
- 主题: 四足机器人 / 人群导航 / 强化学习 / 速度障碍 / LiDAR / sim-to-real
- 摘要: VOP-Nav 用局部多帧 LiDAR 预测由速度障碍理论导出的安全速度区域，在推理时把该预测输入端到端导航策略，并在训练时将其作为奖励信号，全程不依赖显式行人检测、跟踪或全局建图。
- 备注: 方法在 Isaac Gym 中评测，并部署到 Unitree Go2，在室内和户外动态人群中验证。今日核验时未找到官方代码仓库。

### Safe Execution of RL Policies Via Acceleration-Based CBF-QP Constraint Enforcement for Real-World Robotic Deployments
- 链接: https://arxiv.org/abs/2607.14488
- 来源: IROS 2026 / arXiv
- 日期: 2026-07-16
- 作者: Bastien Muraccioli, Alice Cariou, Pierre-Alexandre Leziart, Mathieu Celerier, Arnaud Demont, Gentiane Venture, Mehdi Benallegue
- 主题: 人形机器人 / 安全强化学习 / 控制障碍函数 / 二次规划 / 运行时安全 / 全身控制
- 摘要: Acc-CBF-QP 在不修改或重新训练原策略的前提下，于加速度级过滤 RL 策略，在统一 QP 中执行关节位置、速度、力矩与碰撞约束，并通过力矩任务或前向动力学任务控制安全修正对原策略指令的偏离。
- 备注: 论文被 IROS 2026 接收，在 19-DoF Unitree H1 和 7-DoF Kinova Gen3 上完成仿真与真机验证。项目报告 H1 真机约束违规频率由每秒 10.04 次降至 0.80 次，降低 92%。项目页: https://safe-rl-qp.github.io/。

### Scaling Behavior Foundation Model for Humanoid Robots
- 链接: https://arxiv.org/abs/2607.15163
- 来源: arXiv
- 日期: 2026-07-16
- 作者: Weishuai Zeng, Kangning Yin, Xiaojie Niu, Shunlin Lu, Weixiang Zhong, Jiahe Chen, Feiyu Jia, Xiao Chen, Zirui Wang, Furui Xu, Ming Zhou, Kailin Li, Weinan Zhang, He Wang, Li Yi, Dahua Lin, Jiangmiao Pang, Jingbo Wang
- 主题: 人形机器人 / 行为基础模型 / 动作跟踪 / 强化学习 / Transformer / scaling
- 摘要: ScaleBFM 协同全局坐标系全身动作跟踪、on-policy rollout 宽度与深度的均衡扩展、异构参考动作多样性以及可扩展 Humanoid Transformer，以提升可复用人形行为在仿真和真机中的学习效果与泛化能力。
- 备注: 项目汇集了超过 1.02 亿帧、50 FPS 的人体动作数据，并报告相对现有人形控制器，测试集 MPKPE 在局部模式降低超过 10%、全局模式降低 82%。项目页: https://scalebfm.github.io/。官方仓库当前仅有分阶段发布说明，预计到 2026-07-26 才会提供大部分重定向、训练和部署代码，因此今日不将其计为成熟仓库: https://github.com/zengweishuai/ScaleBFM。

### Semantic Audio-driven Understanding for Dynamic Humanoid Whole Body Control
- 链接: https://arxiv.org/abs/2607.14182
- 来源: RoboCup Symposium 2026 / arXiv
- 日期: 2026-07-15
- 作者: J. M. A. Marcelo, M. Brienza, E. Bugli, L. Comito, D. Nardi, D. D. Bloisi, V. Suriani
- 主题: 人形机器人 / 全身控制 / 强化学习 / 音频语义落地 / 技能编排 / sim-to-real
- 摘要: 系统把连续音频分流为音乐或语音：音乐通过音频指纹和语义嵌入完成曲目识别与时间对齐，语音则映射到离散的模仿学习技能库，随后通过统一接口在强化学习控制管线中调度对应全身策略。
- 备注: 论文被第 29 届 RoboCup International Symposium 接收，并在仿真和 Unitree G1 真机上验证。其主要贡献是基于现有多策略控制栈的语义技能选择与编排，而不是新的底层运动学习器。项目页: https://lab-rococo-sapienza.github.io/semantic-WBC/。

### Vision-Based Dribbling for Humanoid Soccer via Privileged Representation Learning
- 链接: https://arxiv.org/abs/2607.12702
- 来源: arXiv
- 日期: 2026-07-14
- 作者: Flavio Maiorana, Valerio Spagnoli, Eugenio Bugli, Flavio Volpi, Daniele Affinita, Vincenzo Suriani, Daniele Nardi, Luca Iocchi
- 主题: 人形机器人 / 移动操作 / 机器人足球 / 强化学习 / 深度感知 / 特权学习
- 摘要: 该方法通过任务专用投影层把时序深度编码器嵌入强化学习策略，使仿真中的 Booster T1 无需显式场景状态估计，即可直接根据深度观测向目标运球，并对障碍物或主动对手作出反应。
- 备注: 论文报告常规目标运球成功率 100%、单个静态障碍场景 96%、面对主动抢球对手 46%。结果仅来自仿真；实验室关联的 `learning-to-dribble` 仓库目前只有 README 和许可证，没有实现代码。

### “QuadBoat”的设计与控制：用于溺水救援的四足构型水面载具
- 链接：https://arxiv.org/abs/2607.13633
- 来源：arXiv
- 日期：2026-07-15
- 作者：Lianxin Zhang, Yihan Huang, Huihuan Qian
- 主题：四足形态 / 无人水面载具 / 救援机器人 / 模型预测控制 / 视觉跟踪
- 摘要：提出可主动调节姿态的四足构型水面载具，以逆运动学和级联 MPC-PID 控制实现敏捷水面运动、视觉目标跟踪与物体回收。
- 备注：它与传统腿足运动相邻而非完全相同——四足结构被用作可重构多船体水面平台——但对救援机器人的形态与控制设计仍是有价值的信号。

### PAKE：使用部分运动学嵌入学习全身移动操作
- 链接：https://arxiv.org/abs/2607.11041
- 来源：arXiv
- 日期：2026-07-13
- 作者：Zhengmao He, Moonkyu Jung, Hyeongjun Kim, Jiseong Lee, Hui Zhang, Jemin Hwangbo, Jie Song
- 主题：四足 / 移动操作 / 全身控制 / 强化学习 / 归一化流 / 仿真到现实
- 摘要：提出分层框架，用运动学归一化流编码冗余的躯干与机械臂逆运动学解，高层策略在潜在空间中选择部分参考动作，低层策略再将其转换为动力学可行的全身指令。
- 备注：在搭载六自由度机械臂的四足机器人上评估；论文报告了 8 类任务共 24 个硬件回合，包括拉车、扫地、插充电器和挂衣架，末端位置误差为 4.5 cm、姿态误差为 0.14 rad。

### Stop to Decide：面向无地图四足巡检的延迟感知本体导航原语
- 链接：https://arxiv.org/abs/2607.11204
- 来源：arXiv
- 日期：2026-07-13
- 作者：Hanting Suo, Haonan Yan, Liang Wang, Aiguo Song
- 主题：四足 / 巡检 / 本体感知导航 / 延迟感知控制 / 楼梯穿越 / 无地图自主
- 摘要：构建完全机载、无地图且不依赖学习的 Unitree Go2 巡检栈；当共享 Jetson Orin 算力使导航循环降至约 15 Hz 时，“攀爬—停稳—判断”原语仍能可靠工作。
- 备注：在所测试的短顶平台楼梯上，停稳协议将汇总冲出顶部次数从 22/45 降至 1/45，完整系统以 18/20 的成功率完成巡检路线；结果仅覆盖一种路线几何、平台和操作员。

### Handroid：连接灵巧手与人形机器人
- 链接：https://arxiv.org/abs/2607.16187
- 来源：arXiv
- 日期：2026-07-17
- 作者：Ruogu Li, Chenyang Ma, Sikai Li, Zhenyu Wei, Yunchao Yao, Haochen Shi, C. Karen Liu, Shuran Song, Mingyu Ding
- 主题：人形机器人 / 灵巧手 / 可重构机器人 / 强化学习 / 运动控制 / 操作
- 摘要：Handroid 将同一个 27 自由度机电平台复用为 20 自由度仿人灵巧手或具有 12 自由度下肢的桌面人形，并提供统一控制与学习接口，覆盖遥操作、灵巧操作、强化学习行走、步态生成和动作编排。
- 备注：平台高 0.33 米、重 2.05 千克，已验证真实操作、行走和全身动作，以及“形态重构—行走—对接 Franka 机械臂—灵巧抓取放置”的长时程任务。论文称平台将开源；项目页：https://handroid.org/。

### RAVEN：面向鲁棒人形导航、结合无碰撞 MPC 的强化学习自适应可见图规划
- 链接：https://arxiv.org/abs/2607.15701
- 来源：arXiv
- 日期：2026-07-17
- 作者：Ruochen Hou, Shiqi Wang, Beom Jun Kim, Hanzhang Fang, Mehak Singal, Dennis W. Hong
- 主题：人形机器人 / 导航 / 强化学习 / 可见图 / 模型预测控制 / 避碰
- 摘要：RAVEN 使用强化学习元策略自适应调整障碍膨胀与可见图规划器的几何构造，再由无碰撞 MPC 和学习型运动控制器执行，从而在延迟、观测噪声和跟踪不确定性下保留可解释的长时程人形导航。
- 备注：论文与人工调参的可见图 MPC、纯强化学习导航进行比较，报告了更小的障碍附近过冲、更强的狭窄通道鲁棒性，以及噪声和延迟下更可靠的导航；文中展示了 Booster T1 双足机器人在半尺寸 RoboCup 场地上的部署。今天未找到官方代码仓库。

### 超越 Transformer：用于开放词汇目标导航的线性注意力策略
- 链接：https://arxiv.org/abs/2607.18794
- 来源：arXiv
- 日期：2026-07-21
- 作者：Jiahong Zhang, Yifan Lin, Yandong Zhang, Sijun Shen, Kexin Wang, Yuqi Pan, Hongjuan Pei, Wei Wang, Guoqi Li
- 主题：四足机器人 / 开放词汇导航 / 线性注意力 / 机器人学习 / 仿真到现实
- 摘要：LANav 把线性注意力策略骨干用作结构化递归状态更新，并提出加权状态扩展线性注意力，以在部分可观测环境中保留有用历史信息。
- 备注：论文报告 HM3D-OVON 宏平均成功率 36.4%，比匹配的 Transformer 基线高 6.3 个百分点；迁移测试覆盖 HSSD，真实部署在 Unitree Go2 上进行 50 次试验，报告成功率 82%。

### Koopman DCM：作为腿足机器人平衡数据驱动表示的不稳定特征函数
- 链接：https://arxiv.org/abs/2607.18760
- 来源：arXiv
- 日期：2026-07-21
- 作者：Stéphane Caron
- 主题：腿足机器人 / 双足平衡 / Koopman 算子 / 发散运动分量 / 模型预测控制
- 摘要：论文将发散运动分量重新解释为不稳定 Koopman 特征函数，并直接从闭环测量—动作数据学习该表示，不再把它限制在线性倒立摆模型中。
- 备注：训练使用一小时真实机器人数据；学习到的 DCM 在真实双足机器人上改善参考步态跟踪，并在仿真人形实验中作为 MPC 的硬状态可行性约束。论文称将在同行评审后开源配套代码，因此目前尚无代码。

### Extreme-RGMT：面向稳健通用人形控制的高动态技能持续学习
- 链接：https://arxiv.org/abs/2607.20110
- 来源：arXiv
- 日期：2026-07-22
- 作者：Yubiao Ma, Han Yu, Kai Guo, Changtai Lv, Zhengquan Mao, Boyang Xing, Xuemei Ren, Dongdong Zheng
- 主题：人形机器人 / 全身动作跟踪 / 持续学习 / 高动态技能 / 遥操作
- 摘要：一个两阶段框架，先训练通用动作跟踪策略，再在约束已掌握动作策略漂移的同时学习困难高动态技能。
- 备注：方法结合难度感知采样与优势优先轨迹重采样，聚焦稀疏的关键动作片段；论文及项目页展示 Unitree G1 侧空翻、后空翻、鲤鱼打挺等动作，以及基于惯性动捕的在线跟踪。本次未核验到训练代码。

### PGTT：用于感知型腿足运动的相位引导地形穿越
- 链接：https://arxiv.org/abs/2510.18348
- 来源：arXiv / IROS 2026
- 日期：2026-07-22
- 作者：Alexandros Ntagkas, Chairi Kiourt, Konstantinos Chatzilygeroudis
- 主题：四足机器人 / 感知运动 / 强化学习 / 地形适应 / 仿真到现实
- 摘要：一种感知深度强化学习运动方法，通过基于样条的奖励塑形编码各腿相位，同时保留直接关节空间动作，降低对形态特定振荡器或 IK 动作先验的依赖。
- 备注：这是 2025 年预印本的 v2 更新，现已标注被 IROS 2026 接收。论文报告其在受推扰动和离散障碍上的成功率优于所比较基线，并以 LiDAR 高程图管线完成 Unitree Go2 实机验证，还用相同超参数进行了初步 ANYmal-C 迁移。

### 人形机器人通用动作跟踪中，什么真正重要？一项实证研究
- 链接：https://arxiv.org/abs/2607.19903
- 来源：arXiv
- 日期：2026-07-22
- 作者：Fabio Amadio, Enrico Mingo Hoffman
- 主题：人形机器人 / 全身动作跟踪 / 模仿学习 / 仿真到现实 / Unitree G1
- 摘要：一项受控实证研究，在开源 YAHMP 框架中比较动作指令表示、观测历史、动作表示、执行器配置、手部受力随机化和训练方法等通用人形动作跟踪设计因素。
- 备注：作者在同一重定向动作集上与 TWIST2 基线比较，并将策略零样本部署到真实 Unitree G1，展示多样动作跟踪、受扰恢复和用力交互。

</details>
