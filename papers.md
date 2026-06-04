**English** | [中文](zh/papers.md)
# Papers

> Long-term curated paper list for legged robotics.

---

<details>
<summary><strong>Basics</strong></summary>

### Rigid Body Dynamics Algorithms
- Link: resources/books/Rigid%20Body%20Dynamics%20Algorithms.pdf
- Source: book
- Topics: dynamics / rigid body dynamics / fundamentals
- Summary: Foundational material on rigid body dynamics algorithms.

### 仿人机器人
- Link: resources/books/仿人机器人.pdf
- Source: book
- Topics: humanoid / fundamentals
- Summary: Book resource on humanoid robots.

### Robot Dynamics Lecture Notes - ETH
- Link: https://ethz.ch/content/dam/ethz/special-interest/mavt/robotics-n-intelligent-systems/rsl-dam/documents/RobotDynamics2017/RD_HS2017script.pdf
- Source: lecture notes
- Topics: robot dynamics / fundamentals
- Summary: ETH lecture notes on robot dynamics.

</details>

<details>
<summary><strong>Learning-based Simulation</strong></summary>

### A review of learning-based dynamics models for robotic manipulation
- Link: https://www.science.org/doi/epdf/10.1126/scirobotics.adt1497
- Source: Science Robotics
- Topics: learning-based simulation / dynamics models / manipulation
- Summary: Review of learning-based dynamics models for robotic manipulation.

### Robotic World Model: A Neural Network Simulator for Robust Policy Optimization in Robotics
- Link: https://sites.google.com/view/roboticworldmodel
- Source: project page
- Topics: world model / simulation / policy optimization
- Summary: Neural network simulator for robust policy optimization in robotics.
- Notes: Code: https://github.com/leggedrobotics/robotic_world_model.git.

### Uncertainty-Aware Robotic World Model Makes Offline Model-Based Reinforcement Learning Work on Real Robots
- Link: https://sites.google.com/view/uncertainty-aware-rwm
- Source: project page
- Topics: world model / offline RL / model-based reinforcement learning
- Summary: Uncertainty-aware robotic world model for offline model-based RL on real robots.

### Neural Robot Dynamics
- Link: https://neural-robot-dynamics.github.io/
- Source: project page
- Topics: robot dynamics / learned dynamics
- Summary: Project focused on neural robot dynamics.

### Batched Differentiable Rigid Body Dynamics in PyTorch for GPU-Accelerated Robot Learning
- Link: https://arxiv.org/abs/2605.31481
- Source: arXiv
- Date: 2026-05-29
- Authors: Yue Wang, Yanran Xu, Wenbo Wu, Chuanhang Qiu, Zhaoxing Li
- Topics: robot dynamics / differentiable simulation / PyTorch / GPU acceleration / reinforcement learning / quadruped
- Summary: Presents BARD, a PyTorch-native batched articulated rigid-body dynamics library that supports GPU acceleration and autograd, matching Pinocchio numerically while reporting large throughput gains for FK/Jacobians and integration into Isaac Lab AMP training for an 11-DOF spined quadruped.
- Notes: Repository: https://github.com/YueWang996/bard-pytorch-dynamics.


### UniLab: A Heterogeneous Architecture for Robot RL Beyond GPU-Dominant Paradigms
- Link: https://arxiv.org/abs/2605.30313
- Source: arXiv / project page / GitHub
- Date: 2026-05-28; v3 on 2026-06-02
- Authors: Yufei Jia, Zhanxiang Cao, Mingrui Yu, Heng Zhang, Shenyu Chen, Dixuan Jiang, Meng Li, Xiaofan Li, Yiyang Liu, Junzhe Wu, Zheng Li, XiLin Fang, Ting-Yu Tsui, Shengcheng Fu, Haoyang Li, Anqi Wang, Zifan Wang, Dongjie Zhu, Chenyu Cao, Zhenbiao Huang, Ziang Zheng, Jie Lu, Xin Ma, Zhengyang Wei, Xiang Zhao, Tianyue Zhan, Ye He, Yuxiang Chen, Yizhou Jiang, Yue Li, Haizhou Ge, Yuhang Dong, Fan Jia, Ziheng Zhang, Meng Zhang, Xiwa Deng, Zhixing Chen, Hanyang Shao, Chenxin Dong, Yixuan Li, Yizhi Chen, Bokui Chen, Kaifeng Zhang, Hanqing Cui, Yusen Qin, Ruqi Huang, Lei Han, Tiancai Wang, Xiang Li, Yue Gao, Guyue Zhou
- Topics: robot RL / simulation infrastructure / heterogeneous CPU-GPU training / MuJoCoUni / MotrixSim / cross-platform training / quadruped / humanoid / wheeled-legged / loco-manipulation
- Summary: Presents UniLab, a heterogeneous CPU-simulation / GPU-learning architecture for robot RL that decouples CPU-parallel physics rollouts from GPU policy updates through shared-memory buffering and synchronization, using MuJoCoUni and MotrixSim backends; the paper reports 3-10× end-to-end training-efficiency gains on representative robot-control tasks while supporting CUDA, Apple Silicon, AMD ROCm, and Intel XPU execution.
- Notes: Project page: https://unilabsim.github.io/. Official code: https://github.com/unilabsim/UniLab. Relevant for legged robotics because released tasks include Go1/Go2 quadrupeds, Unitree G1 walking / motion tracking / whole-body skills, Go2W wheeled-leg locomotion, and Go2+arm loco-manipulation.
</details>

<details>
<summary><strong>Humanoid Locomotion</strong></summary>

### Learning Whole-Body Humanoid Locomotion via Motion Generation and Motion Tracking
- Link: https://arxiv.org/abs/2604.17335
- Source: arXiv
- Date: 2026-04-19
- Authors: Zewei Zhang, Kehan Wen, Michael Xu, Junzhe He, Chenhao Li, Takahiro Miki, Clemens Schwarke, Chong Zhang, Xue Bin Peng, Marco Hutter
- Topics: humanoid / locomotion / whole-body control / robot learning / perception / sim-to-real
- Summary: Terrain-aware whole-body humanoid locomotion framework that combines diffusion-based motion generation with RL motion tracking and demonstrates hardware traversal on Unitree G1.
- Notes: Strong ETH / RSL signal and a good anchor for current whole-body humanoid locomotion work.

### SoftMimic: Learning Compliant Whole-body Control from Examples
- Link: https://arxiv.org/abs/2510.17792
- Source: arXiv
- Date: 2025-10-20
- Authors: Gabriel B. Margolis, Michelle Wang, Nolan Fey, Pulkit Agrawal
- Topics: humanoid / whole-body control / imitation learning / compliance / reinforcement learning / sim-to-real / Unitree G1
- Summary: Framework for learning compliant humanoid whole-body control from example motions by generating feasible compliant-motion augmentations with inverse kinematics and training an RL policy to absorb disturbances instead of rigidly tracking references.
- Notes: Project page: https://gmargo11.github.io/softmimic/; code: https://github.com/Improbable-AI/softmimic. Paper lists Improbable AI Lab, MIT, and correspondence to Gabriel B. Margolis and Michelle Wang.

</details>

<details>
<summary><strong>Quadruped Locomotion</strong></summary>

### Learning quadrupedal locomotion on deformable terrain
- Link: https://www.science.org/doi/pdf/10.1126/scirobotics.ade2256
- Source: Science Robotics
- Topics: quadruped / deformable terrain / locomotion / adaptation
- Summary: Learning-based quadruped locomotion on deformable terrain with successful transfer emphasis.

### RMA: Rapid Motor Adaptation for Legged Robots
- Link: https://arxiv.org/pdf/2107.04034
- Source: arXiv
- Topics: locomotion / adaptation / legged robots
- Summary: Rapid motor adaptation for legged robots.

### Evaluation of an Actuated Spine in Agile Quadruped Locomotion
- Link: https://arxiv.org/abs/2605.07988
- Source: arXiv
- Date: 2026-05-08
- Authors: Nico Bohlinger, Piotr Kicki, Davide Tateo, Krzysztof Walas, Jan Peters
- Topics: quadruped / locomotion / morphology / agile locomotion / simulation
- Summary: Empirical study of how a 1-DOF actuated spine affects agile quadruped locomotion across high-speed running, stairs, slopes, hurdling, and crawling tasks.
- Notes: Useful reference for morphology-aware locomotion design rather than controller-only comparison.

### Learning to Balance Motor Thermal Safety and Quadrupedal Locomotion Performance with Residual Policy
- Link: https://arxiv.org/abs/2605.27046
- Source: arXiv
- Date: 2026-05-26
- Authors: Yuhang Wan, Weixian Lin, Letian Qian, Yiqi Zou, Weiwei Wu, Shengwei Wu, Chuanlin Zhao, Xin Luo
- Topics: quadruped / reinforcement learning / motor thermal safety / residual policy / sim-to-real / Unitree A1
- Summary: Integrates a whole-body motor thermal model into quadruped RL and trains a residual policy on top of a nominal terrain locomotion policy so the robot can trade tracking performance against actuator overheating risk.
- Notes: Real-world Unitree A1 validation reports stable multi-terrain locomotion under a 3 kg payload for over 13 minutes, versus nominal-policy overheating after about 5 minutes.

</details>

<details>
<summary><strong>Data-driven Optimization</strong></summary>

### Data-Enabled Predictive Control: In the Shallows of the DeePC
- Link: https://arxiv.org/pdf/1811.05890
- Source: arXiv
- Topics: data-driven control / predictive control / DeePC
- Summary: Data-enabled predictive control in the shallows of DeePC.

### Toward a Data-Driven Template Model for Quadrupedal Locomotion
- Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9799758
- Source: IEEE
- Topics: quadruped / template models / data-driven control
- Summary: Toward a data-driven template model for quadrupedal locomotion.

### Deep DeePC: Data-enabled predictive control with low or no online optimization using deep learning
- Link: https://aiche.onlinelibrary.wiley.com/doi/pdf/10.1002/aic.18644
- Source: journal article
- Topics: DeePC / deep learning / predictive control
- Summary: Deep DeePC with low or no online optimization using deep learning.

### prescyent
- Link: https://github.com/hucebot/prescyent
- Source: GitHub
- Topics: data-driven control / trajectory prediction
- Summary: Data-driven trajectory prediction library in Python.

</details>

<details>
<summary><strong>Dexterous Manipulation</strong></summary>

### SimToolReal: An Object-Centric Policy for Zero-Shot Dexterous Tool Manipulation
- Link: https://simtoolreal.github.io/
- Source: project page
- Topics: dexterous manipulation / sim-to-real / policy learning
- Summary: Object-centric policy for zero-shot dexterous tool manipulation.
- Notes: PDF: https://arxiv.org/pdf/2602.16863 and code: https://github.com/tylerlum/simtoolreal.

### TactAlign: Human-to-Robot Policy Transfer via Tactile Alignment
- Link: https://yswi.github.io/tactalign/
- Source: project page
- Topics: dexterous manipulation / tactile alignment / policy transfer
- Summary: Human-to-robot policy transfer through tactile alignment.
- Notes: PDF: https://arxiv.org/pdf/2602.13579.

</details>

<details>
<summary><strong>Datasets and Benchmarks</strong></summary>

### GrandTour: A Legged Robotics Dataset in the Wild for Multi-Modal Perception and State Estimation
- Link: https://arxiv.org/abs/2602.18164
- Source: arXiv
- Date: 2026-02-20
- Authors: Jonas Frey, Turcan Tuna, Frank Fu, Katharine Patterson, Tianao Xu, Maurice Fallon, Cesar Cadena, Marco Hutter
- Topics: quadruped / dataset / perception / state estimation / navigation / SLAM
- Summary: Large-scale multi-modal legged-robotics dataset collected with ANYmal-D across diverse indoor and outdoor environments with high-precision ground truth.
- Notes: Especially relevant for perception, state estimation, and navigation work that needs real-world legged data.

</details>

<details>
<summary><strong>Surveys and Reviews</strong></summary>

### A Survey of Legged Robotics in Non-Inertial Environments: Past, Present, and Future
- Link: https://arxiv.org/abs/2604.20990
- Source: arXiv
- Date: 2026-04-22
- Authors: I-Chia Chang, Xinyan Huang, Tzu-Yuan Lin, Sangli Teng, Wenjing Li, Maani Ghaffari, Jingang Yi, Yan Gu
- Topics: legged robots / locomotion / state estimation / control / dynamic environments
- Summary: Survey of modeling, estimation, and control challenges for legged robots on moving, tilting, or accelerating support surfaces.
- Notes: Good orientation entry for non-stationary-ground locomotion.

### Learning Perceptive Legged Robot Locomotion in the Real World: A Systematic Review
- Link: https://ieeexplore.ieee.org/document/11313692
- Source: IEEE Robotics & Automation Magazine
- Date: 2026-04-17
- Authors: Irfan Tito Kurniawan, Wei Zhu, Dai Owaki, Mitsuhiro Hayashibe
- Topics: perceptive locomotion / legged robots / learning / real-world deployment / review
- Summary: Systematic review of learning-based perceptive legged locomotion, covering capabilities, methods for integrating perception, and open challenges.
- Notes: Useful overview paper for situating new perception-for-locomotion work.

</details>

<details>
<summary><strong>Surveys and Collections</strong></summary>

### many-quadrupeds
- Link: https://github.com/beduffy/many-quadrupeds
- Source: GitHub
- Topics: survey / collection / quadrupeds
- Summary: Awesome-style collection of many quadruped-related resources.

</details>

---

<details>
<summary><strong>Legged State Estimation and Dynamics</strong></summary>

### PRIME: Physically-consistent Robotic Inertial and Motion Estimation for Legged and Humanoid Robots
- Link: https://arxiv.org/abs/2605.17681
- Source: arXiv / RSS 2026
- Date: 2026-05-22
- Authors: Jiarong Kang, Kunzhao Ren, Linxuan Wang, Jingbo Wang, Tao Pang, Xiaobin Xiong
- Topics: legged robots / humanoid robots / state estimation / motion estimation / contact dynamics / inertial parameters
- Summary: MAP-based motion-estimation method that refines kinematics and actuator commands into dynamically consistent trajectories while estimating contact forces and inertial parameters for legged and humanoid robots.
- Notes: Useful to track for physically consistent robot-data reconstruction and force/contact annotation.

</details>

---

<details>
<summary><strong>Humanoid Navigation and Loco-Manipulation</strong></summary>

### Learning to Evolve: Multi-modal Interactive Fields for Robust Humanoid Navigation in Dynamic Environments
- Link: https://arxiv.org/abs/2605.21935
- Source: arXiv / RSS 2026 / project page
- Date: 2026-05-21
- Authors: Peifeng Jiang, Hong Liu, Jin Jin, Wenshuai Wang, Xia Li
- Topics: humanoid / navigation / semantic mapping / 3D Gaussian Splatting / dynamic environments / Unitree G1
- Summary: MIF combines semantic 3D Gaussian Splatting, memory updates, and task-driven geometry reconstruction for robust Unitree G1 navigation in dynamic indoor environments.
- Notes: Strong perception-aware humanoid navigation signal with real-office results.

### SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework
- Link: https://arxiv.org/abs/2605.20373
- Source: arXiv / project page
- Date: 2026-05-19
- Authors: Tianshu Wu, Xiangqi Kong, Yue Chen, Qize Yu, Hang Ye, Jia Li, Yizhou Wang, Hao Dong
- Topics: humanoid / loco-manipulation / human video / imitation learning / reinforcement learning / sim-to-real
- Summary: Framework that converts unstructured human videos into deployable humanoid loco-manipulation skills through interaction-prior extraction, physical refinement, and hierarchical policy learning.
- Notes: Useful reference for reducing reward-design and teleoperation burden in humanoid loco-manipulation.

### Learning Terrain-Aware Whole-Body Control for Perceptive Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2605.31343
- Source: arXiv
- Date: 2026-05-29
- Authors: Sikai Guo, Yudong Zhong, Guoyang Zhao, Botao Dang, Zhihai Bi, Jun Ma
- Topics: legged manipulators / whole-body control / loco-manipulation / terrain perception / reinforcement learning / sim-to-real
- Summary: Introduces TA-WBC, an RL-based terrain-aware whole-body control framework for legged manipulators that uses hybrid exteroception, foot-contact-plane-based end-effector sampling, and dual-policy distillation to improve cross-terrain loco-manipulation in simulation and real-world experiments.
- Notes: Strong daily candidate because it directly links terrain perception, foothold/posture adaptation, and legged mobile manipulation.

### Gaze2Act: Gaze-Conditioned Vision-Language-Action Policies for Interactive Robot Manipulation
- Link: https://arxiv.org/abs/2605.30282
- Source: arXiv
- Date: 2026-05-28
- Authors: Kuangji Zuo, Gen Li, Bofan Lyu, Yanshuo Lu, Boyu Ma, Shijia Han, Xinyu Zhou, Xichen Yuan, Chuhao Zhou, Jiaqi Bai, Geng Li, Jianfei Yang
- Topics: humanoid / VLA / human-robot interaction / gaze conditioning / manipulation / Unitree G1
- Summary: Proposes using human gaze as a continuous intent signal for VLA manipulation, projecting first-person gaze into the robot view and evaluating across 16 real-robot tasks on a Unitree G1 humanoid.
- Notes: Adjacent to locomotion but high-signal for humanoid interaction stacks; project/GitHub page: https://github.com/zuo-kuangji/Gaze2Act.

### GRAIL: Generating Humanoid Loco-Manipulation from 3D Assets and Video Priors
- Link: https://arxiv.org/abs/2606.05160
- Source: arXiv
- Date: 2026-06-03
- Authors: Tianyi Xie, Haotian Zhang, Jinhyung Park, Zi Wang, Bowen Wen, Jiefeng Li, Xueting Li, Qingwei Ben, Haoyang Weng, Yufei Ye, David Minor, Tingwu Wang, Chenfanfu Jiang, Sanja Fidler, Jan Kautz, Linxi Fan, Yuke Zhu, Zhengyi Luo, Umar Iqbal, Ye Yuan
- Topics: humanoid / loco-manipulation / synthetic data / video foundation models / 3D assets / sim-to-real / Unitree G1
- Summary: Presents GRAIL, a fully digital data-generation pipeline that composes 3D assets, simulator-ready scenes, robot-proportioned characters, and video foundation model priors to recover metric 4D human-object interaction trajectories, retarget them to humanoids, and train task-general trackers for manipulation and terrain traversal; the paper reports more than 20,000 generated sequences and real Unitree G1 deployment with 84% object-pickup success and 90% stair-climbing success.
- Notes: Project page: https://research.nvidia.com/labs/dair/grail/. Official code: https://github.com/NVlabs/GRAIL. Strong data-generation counterpart to recent teleoperation-free humanoid loco-manipulation work.

### Humanoid-GPT: Scaling Data and Structure for Zero-Shot Motion Tracking
- Link: https://arxiv.org/abs/2606.03985
- Source: arXiv / CVPR 2026
- Date: 2026-06-02
- Authors: Zekun Qi, Xuchuan Chen, Dairu Liu, Chenghuai Lin, Yunrui Lian, Sikai Liang, Zhikai Zhang, Yu Guan, Jilong Wang, Wenyao Zhang, Xinqiang Yu, He Wang, Li Yi
- Topics: humanoid / whole-body control / motion tracking / Transformer / large-scale motion data / zero-shot generalization
- Summary: Introduces Humanoid-GPT, a GPT-style causal Transformer for whole-body control pretrained on a 2B-frame retargeted motion corpus combining major mocap datasets and in-house recordings, targeting zero-shot tracking of unseen dynamic motions and control tasks.
- Notes: Accepted at CVPR 2026. Hardware details and public code were not verified in today's quick pass; keep as a high-signal data-scaling / architecture item rather than a deployment claim.

### CoRe-MoE: Contrastive Reweighted Mixture of Experts for Multi-Terrain Humanoid Locomotion with Gait Adaptation
- Link: https://arxiv.org/abs/2606.04718
- Source: arXiv
- Date: 2026-06-03
- Authors: Kailun Huang, Zikang Xie, Yanzhe Xie, Panpan Liao, Fanghai Zhang, Yanheng Mai, Wenhao Xu, Yunheng Wang, Renjing Xu, Haohui Huang
- Topics: humanoid / reinforcement learning / mixture of experts / gait transition / terrain adaptation / Unitree G1
- Summary: Proposes CoRe-MoE, a two-stage RL framework that first learns stable walking/running transitions and then adds a terrain-aware mixture-of-experts branch with contrastive gating to improve expert specialization and multi-terrain adaptation; the abstract reports zero-shot Unitree G1 deployment over stairs, slopes, steps, obstacles, and outdoor unstructured terrain.
- Notes: Affiliations listed in the arXiv abstract include HKUST(GZ), South China Agricultural University, and Guangdong University of Technology; corresponding authors are Renjing Xu and Haohui Huang.


</details>

---

<details>
<summary><strong>Wheeled-Legged and Transformable Robots</strong></summary>

### WiXus: A Wheeled-Legged Robot with Wire-Driven Environmental Utilizing to Integrate Mobility and Manipulation
- Link: https://arxiv.org/abs/2605.20932
- Source: arXiv / ICRA 2026 / project page
- Date: 2026-05-20
- Authors: Shintaro Inoue, Kento Kawaharazuka, Temma Suzuki, Sota Yuzaki, Kei Okada
- Topics: wheeled-legged robot / mobility / manipulation / environmental wire actuation / hardware system
- Summary: Wheeled-legged hardware system that uses wire-driven environmental anchoring so legs can support mobility, manipulation, and tool-use roles.
- Notes: Notable mobility-manipulation integration signal from the JSK network.

### MUJICA: Multi-skill Unified Joint Integration of Control Architecture for Wheeled-Legged Robots
- Link: https://arxiv.org/abs/2605.13058
- Source: arXiv
- Date: 2026-05-17
- Authors: Wanming Yu, Xinshuo Yang, Wenxuan Wei, ZhuoJia Huang, Junzheng Wang
- Topics: wheeled-legged robots / reinforcement learning / proprioceptive control / sim-to-real / fall recovery
- Summary: Unified proprioceptive multi-skill controller for omnidirectional movement, high-platform climbing, and fall recovery on wheeled-legged robots.
- Notes: Real Unitree Go2-W experiments make it a practical sim-to-real control reference.

### X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation
- Link: https://arxiv.org/abs/2604.21541
- Source: arXiv
- Date: 2026-04-28
- Authors: Shengjie Wang, Hui Zhang, Zixuan Wu, Wenhao Yu, Guifeng Yuan, Guohui Tian, Wenhao Zhang, Junyao Gao, Weijia Liu, Zhennan Tang, Jing Peng, Weixia Liu, Wensheng Zhang, Qiang Huang
- Topics: humanoid / wheeled-legged robot / transformable robot / whole-body control / reinforcement learning / manipulation
- Summary: Transformable high-DoF robot that switches between humanoid and wheel-legged modes with RL-based whole-body control for hybrid locomotion and manipulation.
- Notes: Useful hardware-system reference for dual-mode humanoid mobility.

</details>
