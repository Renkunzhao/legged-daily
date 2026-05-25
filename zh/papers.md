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
