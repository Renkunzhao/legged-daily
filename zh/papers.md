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
