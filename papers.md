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

### BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion
- Link: https://arxiv.org/abs/2508.08241
- Source: arXiv
- Date: 2025-08-11
- Authors: Qiayuan Liao, Takara E. Truong, Xiaoyu Huang, Yuman Gao, Guy Tevet, Koushil Sreenath, C. Karen Liu
- Topics: humanoid / motion tracking / guided diffusion / whole-body control / versatile control
- Summary: Extends motion-tracking-style humanoid control toward more versatile behaviors by using guided diffusion to generate or adapt motion guidance for downstream control.
- Notes: Useful comparison point for residual-learning and skill-blending approaches to move beyond pure tracking.

### SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2511.07820
- Source: Science Robotics / arXiv
- Date: 2025-11-11
- Authors: Zhengyi Luo, Ye Yuan, Tingwu Wang, Chenran Li, Fernando Castañeda, Sirui Chen, Zi-Ang Cao, Jiefeng Li, David Minor, Qingwei Ben, Jinhyung Park, David Sami, Zi Wang, Xingye Da, Runyu Ding, Cyrus Hogg, Lina Song, Edy Lim, Eugene Jeong, Tairan He, Haoru Xue, Wenli Xiao, Simon Yuen, Jan Kautz, Yan Chang, Umar Iqbal, Linxi "Jim" Fan, Yuke Zhu
- Topics: humanoid / whole-body control / motion tracking / large-scale training / natural motion / GEAR
- Summary: Large-scale humanoid whole-body motion-tracking work from the NVIDIA GEAR line, aimed at natural full-body control across broad human-motion data.
- Notes: Connect with the existing SONIC/GEAR repository entry when tracking code, actuator modeling, deployment, and dataset scaling details.

### HoloMotion-1 Technical Report
- Link: https://arxiv.org/abs/2605.15336
- Source: arXiv technical report
- Date: 2026-05-14
- Authors: Maiyue Chen, Kaihui Wang, Bo Zhang, Xihan Ma, Zhiyuan Yang, Yi Ren, Qijun Huang, Zihao Zhu, Yucheng Wang, Zhizhong Su
- Topics: humanoid / motion learning / whole-body control / technical report
- Summary: Technical report around HoloMotion-1, useful as a current reference point for humanoid motion learning and whole-body skill generation.
- Notes: Follow up on project assets, data/code availability, and how the system differs from SONIC or BeyondMimic-style tracking pipelines.

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

### Extreme Parkour with Legged Robots
- Link: https://extreme-parkour.github.io/
- Source: project page / arXiv
- Date: 2023
- Authors: Xuxin Cheng, Kexin Shi, Ananye Agarwal, Deepak Pathak
- Topics: quadruped / parkour / vision-based locomotion / reinforcement learning / sim-to-real / depth camera
- Summary: Trains a single end-to-end neural policy in simulation to perform dynamic quadruped parkour from front-facing depth images, demonstrating high jumps, long jumps, handstands, tilted-ramp traversal, and generalization to novel obstacle courses on a low-cost robot.
- Notes: Cited by the Isaaclab_Parkour repository; useful anchor for vision-based agile locomotion and parkour-style legged RL.

### Robot Parkour Learning
- Link: https://robot-parkour.github.io/
- Source: CoRL 2023 / project page
- Date: 2023
- Authors: Ziwen Zhuang, Zipeng Fu, Jianren Wang, Christopher G. Atkeson, Sören Schwertfeger, Chelsea Finn, Hang Zhao
- Topics: quadruped / parkour / vision-based locomotion / reinforcement learning / distillation / sim-to-real / depth camera
- Summary: Learns diverse quadruped parkour skills with reinforcement learning and distills them into a single egocentric-depth vision policy that autonomously selects skills for climbing obstacles, leaping gaps, crawling under barriers, squeezing through slits, and running in real-world environments.
- Notes: CoRL 2023 Oral and Best Systems Paper Award Finalist; official code: https://github.com/ZiwenZhuang/parkour.

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

### Discovery of skill-switching criteria for learning agile quadruped locomotion
- Link: https://arxiv.org/abs/2502.06676
- Source: Frontiers in Robotics and AI / arXiv
- Date: 2025-02-10
- Authors: Wanming Yu, Fernando Acero, Vassil Atanassov, Chuanyu Yang, Ioannis Havoutis, Dimitrios Kanoulas, Zhibin Li
- Topics: quadruped / agile locomotion / skill switching / reinforcement learning / hierarchical control
- Summary: Studies how to discover criteria for switching among learned locomotion skills so a quadruped can execute agile behaviors more reliably.
- Notes: Useful for comparing explicit skill-switching criteria against mixture-of-experts routing and unified multi-skill policies. Best Paper: no confirmed.

### MoE-Loco: Mixture of Experts for Multitask Locomotion
- Link: https://arxiv.org/abs/2503.08564
- Source: IROS 2025 / arXiv
- Date: 2025-03-11
- Authors: Runhan Huang, Shaoting Zhu, Yilun Du, Hang Zhao
- Topics: locomotion / multitask learning / mixture of experts / reinforcement learning / expert routing
- Summary: Applies a mixture-of-experts architecture to multitask locomotion, emphasizing expert specialization and routing across locomotion tasks.
- Notes: Good anchor for MoE-style policy decomposition in legged control. Best Paper: no confirmed.

### Learning Multi-Skill Legged Locomotion Using Conditional Adversarial Motion Priors
- Link: https://arxiv.org/abs/2509.21810
- Source: arXiv
- Date: 2025-09-26
- Authors: Ning Huang, Zhentao Xie, Qinchuan Li
- Topics: legged locomotion / multi-skill learning / conditional adversarial motion priors / imitation learning / reinforcement learning
- Summary: Learns multi-skill legged locomotion using conditional adversarial motion priors, connecting AMP-style imitation objectives with skill-conditioned control.
- Notes: Track condition design, discriminator structure, and skill-library assumptions for comparison with MoE and switching-criteria methods.

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


### SkillBlender: Towards Versatile Humanoid Whole-Body Loco-Manipulation via Skill Blending
- Link: https://arxiv.org/abs/2506.09366
- Source: arXiv
- Date: 2025-06-11
- Authors: Yuxuan Kuang, Haoran Geng, Amine Elhafsi, Tan-Dzung Do, Pieter Abbeel, Jitendra Malik, Marco Pavone, Yue Wang
- Topics: humanoid / loco-manipulation / skill blending / whole-body control / reinforcement learning
- Summary: Studies how to blend whole-body humanoid skills so locomotion and manipulation behaviors can be composed into more versatile loco-manipulation policies.
- Notes: Useful counterpart to residual-learning, latent-VLA, and motion-discovery approaches for humanoid mobile manipulation.

### ResMimic: From General Motion Tracking to Humanoid Whole-Body Loco-Manipulation via Residual Learning
- Link: https://arxiv.org/abs/2510.05070
- Source: arXiv
- Date: 2025-10-06
- Authors: Siheng Zhao, Yanjie Ze, Yue Wang, C. Karen Liu, Pieter Abbeel, Guanya Shi, Rocky Duan
- Topics: humanoid / loco-manipulation / residual learning / motion tracking / whole-body control
- Summary: Uses residual learning to adapt general humanoid motion-tracking capabilities toward whole-body loco-manipulation behaviors.
- Notes: Strong comparison point for BeyondMimic, SkillBlender, and ULC-style controller designs.

### WholeBodyVLA: Towards Unified Latent VLA for Whole-Body Loco-Manipulation Control
- Link: https://arxiv.org/abs/2512.11047
- Source: ICLR 2026 Poster / arXiv
- Date: 2025-12-11
- Authors: Haoran Jiang, Jin Chen, Qingwen Bu, Li Chen, Modi Shi, Yanjie Zhang, Delong Li, Chuanzhe Suo, Chuang Wang, Zhihui Peng, Hongyang Li
- Topics: humanoid / VLA / latent actions / whole-body control / loco-manipulation
- Summary: Proposes a unified latent VLA direction for whole-body humanoid loco-manipulation control, linking language/vision/action abstractions with locomotion-aware manipulation.
- Notes: Connect with the existing WholeBodyVLA repository/resource entry. Best Paper: no confirmed.

### Learning a Unified Policy for Position and Force Control in Legged Loco-Manipulation
- Link: https://arxiv.org/abs/2505.20829
- Source: CoRL 2025 / arXiv
- Date: 2025-05-27
- Authors: Peiyuan Zhi, Peiyang Li, Jianqin Yin, Baoxiong Jia, Siyuan Huang
- Topics: legged loco-manipulation / position control / force control / unified policy / whole-body control
- Summary: Learns a unified policy that handles both position and force control for legged loco-manipulation, making it a key reference for contact-rich mobile manipulation.
- Notes: Marked by user as CoRL 2025 Best Paper; prioritize for detailed notes on objective structure and real-robot evidence.

### ULC: A Unified and Fine-Grained Controller for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2507.06905
- Source: arXiv / in submission
- Date: 2025-07-09
- Authors: Wandong Sun, Luying Feng, Baoshi Cao, Yang Liu, Yaochu Jin, Zongwu Xie
- Topics: humanoid / loco-manipulation / unified controller / fine-grained control / whole-body control
- Summary: Proposes a unified fine-grained controller for humanoid loco-manipulation, complementing skill blending, residual learning, and latent-VLA approaches.
- Notes: Follow up on controller granularity, command/action interface, and manipulation task suite.

### MotionDisco: Motion Discovery for Extreme Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2606.06139
- Source: arXiv
- Date: 2026-06-04
- Authors: Ilyass Taouil, Michal Ciebelski, Shafeef Omar, Haizhou Zhao, Angela Dai, Aaron M. Johnson, Majid Khadiv
- Topics: humanoid / loco-manipulation / motion discovery / LLM-guided search / kinodynamic optimization / reinforcement learning
- Summary: Discovers contact-rich long-horizon humanoid loco-manipulation motions from scratch using LLM-guided evolutionary search, kinodynamic trajectory optimization, pruning, and RL tracking policies.
- Notes: Important automated skill-discovery route that does not rely primarily on teleoperation or human-motion retargeting.

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
- Date: 2026-05-13
- Authors: Yuqi Li, Peng Zhai, Yueqi Zhang, Xiaoyi Wei, Quancheng Qian, Zhengxu He, Qianxiang Yu, Lihua Zhang
- Topics: wheeled-legged robots / reinforcement learning / multi-skill control / proprioceptive control / sim-to-real
- Summary: Unified multi-skill control architecture for wheeled-legged robots, targeting integrated locomotion skills on platforms such as Unitree Go2-W.
- Notes: Useful practical reference for unified multi-skill wheeled-legged control; included in the user-requested multi-skill reading cluster.

### X2-N: A Transformable Wheel-legged Humanoid Robot with Dual-mode Locomotion and Manipulation
- Link: https://arxiv.org/abs/2604.21541
- Source: arXiv
- Date: 2026-04-28
- Authors: Shengjie Wang, Hui Zhang, Zixuan Wu, Wenhao Yu, Guifeng Yuan, Guohui Tian, Wenhao Zhang, Junyao Gao, Weijia Liu, Zhennan Tang, Jing Peng, Weixia Liu, Wensheng Zhang, Qiang Huang
- Topics: humanoid / wheeled-legged robot / transformable robot / whole-body control / reinforcement learning / manipulation
- Summary: Transformable high-DoF robot that switches between humanoid and wheel-legged modes with RL-based whole-body control for hybrid locomotion and manipulation.
- Notes: Useful hardware-system reference for dual-mode humanoid mobility.

</details>

---

<details>
<summary><strong>July 2026 Daily Additions</strong></summary>

### Athena-WBC: Capability-Aligned Policy Experts for Long-Tail Humanoid Whole-Body Control
- Link: https://arxiv.org/abs/2607.04837
- Source: arXiv
- Date: 2026-07-06; v2 2026-07-07
- Authors: Yuan Jiang, Ningyuan Zhang, Xicun Yang, Yuzhi Jiang, Jie Chen
- Topics: humanoid, whole-body control, motion tracking, teacher-student distillation, policy experts, reinforcement learning
- Summary: Athena-WBC targets long-tail failures in full-size humanoid motion-tracking controllers by routing hard motions to capability-aligned dynamic and balance experts, distilling privileged teachers into one deployable controller, then fine-tuning with RL.
- Notes: High signal for humanoid motion-prior / whole-body-control tracking pipelines because it argues failures are not only data exposure problems, but also training-recipe / induced-capability mismatches.

### Calf-Integrated Arms for Bimanual Quadruped Loco-Manipulation
- Link: https://arxiv.org/abs/2607.06186
- Source: arXiv
- Date: 2026-07-07
- Authors: Yan Pan, Yuanchuan Ren, Chipui Chan, Jingcheng Sun, Chengxu Zhou
- Topics: quadruped, loco-manipulation, robot design, bimanual manipulation, VLM skill sequencing, Unitree Go2
- Summary: The paper proposes adding a prismatic-slider / two-revolute-joint / gripper manipulator to each front calf of a Unitree Go2, enabling ground-level bimanual manipulation while all four feet remain planted and using a VLM to sequence predefined skills.
- Notes: Current validation described in the abstract is simulation-only, but the morphology is a distinctive alternative to trunk-mounted arms or leg-as-manipulator schemes.

### WristMimic: Full-Body Humanoid Control with Wrist-Guided Manipulation
- Link: https://arxiv.org/abs/2607.06438
- Source: arXiv; accepted to ECCV 2026
- Date: 2026-07-07
- Authors: Wongyun Yu, Youngwoon Kim, Minsu Cho
- Topics: humanoid, full-body control, human-object interaction, retargeting, manipulation, contact-rich control
- Summary: WristMimic retargets human object-interaction demonstrations by tracking contact-free body and wrist targets while letting fingers learn manipulation from object tracking and contact outcomes, enabling finger-agnostic transfer across hand embodiments.
- Notes: Useful adjacent signal for humanoid whole-body manipulation and motion retargeting; less locomotion-specific than Athena-WBC, but strong for full-body interaction.

### Human Motion Priors for Scalable Robot Learning Across Morphologies
- Link: https://arxiv.org/abs/2606.30290
- Source: arXiv
- Date: 2026-06-29
- Authors: Guillaume Sartoretti and coauthors
- Topics: cross-morphology retargeting, robot learning, quadruped, hexapod, quadruped manipulator, privileged RL, behavior priors, teleoperation, text-conditioned motion
- Summary: X-Morph converts human motion into deployable locomotion and loco-manipulation policies for non-humanoid legged robots by retargeting human motions into robot references, tracking them with privileged RL, and distilling causal student policies.
- Notes: Selected because it directly addresses the scarce-motion-data problem for non-humanoid legged robots and complements ABot-C0's quadruped motion-corpus direction.

### Semi-Modular Wheel-Legged Quadruped With Agile Bimanual Capability
- Link: https://arxiv.org/abs/2606.30243
- Source: arXiv
- Date: 2026-06-29; v2 2026-07-07
- Authors: Luca Rossini, Arturo Laurenzi, Francesco Ruscelli, Yifang Zhang, Jingcheng Jiang, Giovanbattista Gravina, Lorenzo Baccelliere, Corrado Burchielli, Stefano Cordasco, Luca Muratore, Nikos Tsagarakis
- Topics: wheel-legged quadruped, loco-manipulation, bimanual manipulation, robot design, whole-body control, reinforcement learning
- Summary: KYON is a semi-modular wheel-legged quadruped with reconfigurable lower legs and a bimanual upper body, combining base-mounted actuation, transmission mechanisms, whole-body control, and RL policies for dynamic locomotion and manipulation experiments.
- Notes: v2 appeared on 2026-07-07; high-signal as a hardware morphology update rather than a pure learning method.

### Immersive Social Interaction with VR and LLM-Assisted Humanoids
- Link: https://arxiv.org/abs/2607.07430
- Source: arXiv
- Date: 2026-07-08
- Authors: Niraj Pudasaini, Geeta Chandra Raju Bethala, Pranav Doma, Anthony Tzes, Yi Fang
- Topics: humanoid / teleoperation / VR / LLM-assisted control / locomotion commands / data collection
- Summary: Describes an Apple Vision Pro based teleoperation system for Unitree H1 that combines voice-controlled locomotion, VR manipulation retargeting, dexterous-hand control, and bidirectional social interaction.
- Notes: Reported novice-user evaluations include 80% object-manipulation success and 70% social cube-passing success; the multimodal logs are positioned as future imitation-learning data.

### Behavior Foundations for Quadruped Robots: ABot-C0 Technical Report
- Link: https://arxiv.org/abs/2607.07370
- Source: arXiv
- Date: 2026-07-07
- Authors: Xufeng Zhao, Fuzhi Yang, Jianhui Chen, Li Gao, Zhang Meng, Jie Gao, Yao Zheng, Congyang Zhao, Tianxiong Lv, Menglin Yang, Minqi Gu, Yaru Zhao, Wenyu Liu, Honglin Han, Shihui Su, Zixiao Tang, Liu Liu, Mu Xu, Yang Cai, Wenbin Tang
- Topics: quadruped / motion tracking / locomotion / scene interaction / foundation policy / data scaling / deployment
- Summary: Presents ABot-C0, a quadruped behavior-foundation system built around a multi-source motion-data pipeline, flow-matching generalist motion policy, privileged-to-perceptive locomotion, and unified real-world deployment stack.
- Notes: The abstract reports 16,074 physically feasible motion clips and a project page planned but not yet released; track for future code/data release.

### ContactMimic: Humanoid Object Interaction via Contact Control
- Link: https://arxiv.org/abs/2607.08742
- Source: arXiv / project page
- Date: 2026-07-09
- Authors: Xinyao Li, Xialin He, Runpei Dong, Saurabh Gupta
- Topics: humanoid / loco-manipulation / contact control / motion tracking / sim-to-real
- Summary: Adds explicit part-level binary contact commands to humanoid keypoint tracking so policies can produce or suppress physical contact during object interaction, with simulation tests over 10 motions and real-world validation over 5 motions.
- Notes: Project page: https://lixinyao11.github.io/contactmimic-page/. Adjacent to legged locomotion but useful for humanoid full-body control and real-world Unitree G1 contact-conditioned interaction.

### Physics-Guided Biomechanical Gait Adaptation for Humanoid Locomotion on Extreme Sloped Terrains
- Link: https://arxiv.org/abs/2607.07830
- Source: arXiv
- Date: 2026-07-08
- Authors: Xuanyu Chen, Mohan Liu, Dengchen Mei, Zhihao Gu, Haitian Zhang, Kaimin Mao, Haiyue Zhu, Shijun Yan, Lin Wang
- Topics: humanoid / locomotion / slope traversal / reinforcement learning / sim-to-real / proprioception
- Summary: Introduces HumoSlope, a two-stage physics-guided humanoid locomotion framework with a slope-adaptive ZMP regularizer and biomechanical gait adapter; reports blind proprioceptive outdoor traversal of grass slopes up to 62.7% / 32.1 degrees.
- Notes: High relevance for robust humanoid terrain adaptation because it targets persistent gravitational bias on steep continuous slopes rather than flat or discrete obstacle settings.

### ARDY: Autoregressive Diffusion with Hybrid Representation for Interactive Human Motion Generation
- Link: https://arxiv.org/abs/2607.08741
- Source: arXiv / SIGGRAPH 2026 / project page
- Date: 2026-07-09
- Authors: Kaifeng Zhao, Mathis Petrovich, Haotian Zhang, Tingwu Wang, Siyu Tang, Davis Rempe
- Topics: humanoid / human motion generation / interactive locomotion control / diffusion / text-conditioned control
- Summary: Introduces a streaming autoregressive diffusion framework for real-time, controllable 3D human motion generation with online text prompts, kinematic constraints, path following, and interactive locomotion control.
- Notes: Project page and planned code/model release: https://research.nvidia.com/labs/sil/projects/ardy/. Adjacent signal rather than a robot-control paper, but relevant to humanoid motion-data generation and interactive policy conditioning.

### GIRAF: Towards Generalizable Human Interactions with Articulated Objects
- Link: https://arxiv.org/abs/2607.07880
- Source: arXiv / CVPR 2026 HuMoGen Workshop
- Date: 2026-07-08
- Authors: Xiaohan Zhang, Sebastian Starke, Alexander Winkler, Federica Bogo, Samir Aroudj, Yuting Ye
- Topics: embodied AI / locomotion-to-manipulation transitions / full-body motion generation / articulated objects / contact
- Summary: Proposes a text-conditioned diffusion model for full-body human interaction with articulated objects, emphasizing coordinated approach locomotion, hand-object contact, object articulation, and generalization to unseen object configurations.
- Notes: Not a legged-robot deployment result, but useful for tracking data/model directions for humanoid loco-manipulation and contact-rich full-body behavior synthesis.

### HEFT: Heavy-Payload Full-size Humanoid Teleoperation with Privileged Motion Guidance and Windowed Payload Curriculum
- Link: https://arxiv.org/abs/2607.02332
- Source: arXiv / project page
- Date: 2026-07-02
- Authors: Chenxin Liu, Qingzhou Lu, Guangxiao Yang, Xuanyang Shi, Chenghan Yang, Yanjiang Guo, Jianyu Chen
- Topics: humanoid / whole-body teleoperation / motion tracking / payload-aware locomotion / reinforcement learning
- Summary: Presents HEFT, a full-size humanoid teleoperation framework that trains deployable policies on noisy VR references while using reconstructed motion as privileged guidance, plus a windowed payload curriculum for motion-dependent heavy-load robustness; reports deployment on the 175 cm, 65 kg L7 humanoid with motions including turns, forward/backward locomotion, squats, and two-hand payloads up to 24 kg.
- Notes: Project page: https://heft.axell.top/. The arXiv HTML lists affiliations as Tsinghua University, RobotEra, and Shanghai Qizhi Institute.

### CLAP: Direct VLM-to-VLA Adaptation via Language-Action Grounding
- Link: https://arxiv.org/abs/2607.08974
- Source: arXiv / project page
- Date: 2026-07-09
- Authors: Yuri Ishitoya, Jeremy Siburian, Masashi Hamaya, Kuniaki Saito, Cristian C. Beltran-Hernandez, Mai Nishimura
- Topics: vision-language-action models / robot learning / language-action grounding / compact VLA
- Summary: Introduces CLAP, a Causal Language-Action Prediction method that prepends numeric action sequences with natural-language action descriptions so pretrained VLMs can be adapted into VLAs with minimal architectural changes; reports 90.8% on LIBERO with single-epoch fine-tuning and plans open-weight 0.8B, 2B, and 4B releases.
- Notes: This is manipulation/VLA-focused rather than legged-specific; track as an adjacent compact-VLA signal for future humanoid loco-manipulation pipelines.

### Differential Analysis of Multispectral Images for Terrain Identification
- Link: https://arxiv.org/abs/2607.09319
- Source: arXiv
- Date: 2026-07-10
- Authors: Omar Kashmar, Hemendra Arya, Fulvio Mastrogiovanni
- Topics: terrain perception / multispectral sensing / autonomous navigation / edge deployment
- Summary: Proposes DRIFT, a lightweight multispectral terrain-identification framework combining raw spectral bands, illumination-tolerant band-ratio features, and differential fusion; evaluates on oil-on-soil UAV multispectral data and a controlled water-on-grass study, reporting stronger robustness than RGB-style baselines under lighting and material ambiguity.
- Notes: Not a legged-robot paper by itself, but terrain understanding under illumination/material shifts is relevant to outdoor quadruped and humanoid navigation stacks.

### Robust bipedal locomotion on flowable slopes via foot-driven terrain manipulation
- Link: https://arxiv.org/abs/2607.11855
- Source: arXiv
- Date: 2026-07-13
- Authors: Deniz Kerimoglu, Junnosuke Kamohara, Jiyeon Maeng, Ziwon Yoon, Seth Hutchinson, Ye Zhao, Daniel I. Goldman
- Topics: bipedal locomotion / granular terrain / terradynamics / foot morphology / terrain manipulation
- Summary: Studies bipedal locomotion on granular slopes using a small robophysical biped with cleated feet, showing that intermediate cleat spacing can shape substrate stresses and improve locomotion while overly sparse or dense cleats degrade performance.
- Notes: High relevance for legged robots operating on deformable outdoor terrain; the key signal is that foot design and terrain response control can become active locomotion mechanisms rather than only robustness problems.

### SKooP: Symmetric Koopman Predictions for Faster and More Generalizable Legged Robot Locomotion with Reinforcement Learning
- Link: https://arxiv.org/abs/2607.11624
- Source: arXiv
- Date: 2026-07-13
- Authors: Evelyn D'Elia, Weishu Zhan, Giulio Turrisi, Giulio Romualdi, Giuseppe L'Erario, Raffaello Camoriano, Wei Pan, Daniele Pucci
- Topics: legged locomotion / reinforcement learning / symmetry / Koopman models / sample efficiency / sim-to-real transfer
- Summary: Introduces SKooP, which learns a Koopman dynamics model alongside the locomotion policy, uses Koopman predictions as privileged critic observations, and adds group symmetries to actor, critic, encoder, and decoder networks for more equivariant legged RL.
- Notes: Strong candidate for the long-term paper list if follow-up artifacts or benchmark details are useful; also connects to iit-DLSLab-style work on sample-efficient and transferable locomotion learning.

### TAC-LOCO: Unified Whole-Body Control for Quadrupedal TACtile-Informed LOCO-Manipulation
- Link: https://arxiv.org/abs/2607.10132
- Source: arXiv
- Date: 2026-07-11
- Authors: Muqun Hu, Yuhao Zhou, Kabir Ray Malik, Chi Lin, Won Suk Lee, Yu She, Yan Gu
- Topics: quadruped / loco-manipulation / tactile sensing / whole-body control / reinforcement learning / sim-to-real
- Summary: Proposes TAC-LOCO, a tactile-augmented unified RL controller that fuses tactile-array latent features with proprioception to control a Unitree Go2, arm, and gripper during dynamic loco-manipulation under changing external interactions.
- Notes: Reports zero-shot hardware deployment on Unitree Go2 with WidowX 250 and tactile gripper, including reduced grasp force and improved object stability under load changes and release events.

### GaitSpan: Growing Humanoid Locomotion from Walking to Running
- Link: https://arxiv.org/abs/2607.12114
- Source: arXiv
- Date: 2026-07-13
- Authors: Kwan-Yee Lin, Zilin Wang, Janelle J. Liu, Stella X. Yu
- Topics: humanoid locomotion / reinforcement learning / gait transition / sim-to-real
- Summary: GaitSpan expands a pretrained walking policy into continuous-speed walking, jogging, and running-like locomotion by reusing frozen walking structure, combining learned internal rhythms, shaping dynamic strides, and adding residual corrections; the authors report cross-morphology transfer and zero-shot deployment on unseen simulated and real terrains.
- Notes: Project page: https://gaitspan2026.github.io/. Its code button pointed to https://github.com/LeCAR-Lab/GaitSpan/ during review, but that repository was not publicly accessible at the check time.

### Agile perceptive multi-skill locomotion for quadrupedal robots in the wild
- Link: https://arxiv.org/abs/2607.13579
- Source: Science Robotics / arXiv
- Date: 2026-07-15
- Authors: Jun-Gill Kang, Jaehyun Park, Tae-Gyu Song, Joon-Ha Kim, Seungwoo Hong, Hae-Won Park
- Topics: quadruped / perceptive locomotion / reinforcement learning / gait transition / sim-to-real
- Summary: APT-RL pretrains Transformer-based latent locomotion skills on 180,000 trajectory-optimization samples, adapts them with reinforcement learning, and distills perception into a single onboard policy that autonomously selects and transitions between gaits across stairs, hurdles, stepping stones, gaps, forest debris, and other uneven terrain.
- Notes: Published in Science Robotics on 2026-07-15. The project reports 4.25 m/s over a 60 cm step, a 6 m/s instantaneous peak during a stair drop-down, and completed 1.1 km urban and 0.34 km forest routes using only onboard sensing and computation. Project page: https://skillquadsr.github.io/. No public code link was visible during review.

### EgoHTR: Egocentric 4D Demonstrations of Human Terrain Traversal
- Link: https://arxiv.org/abs/2607.13472
- Source: arXiv
- Date: 2026-07-15
- Authors: Alex Brandes, Haig Conti Georges Sajelian, Manthan Patel, Dominik Hollidt, Chenhao Li, Matthias Heyrman, Oliver Hausdoerfer, Manuel Kaufmann, Xi Wang, Jonas Frey, Angela P. Schoellig, Christian Holz, Marc Pollefeys, Marco Hutter
- Topics: humanoid / terrain traversal / human motion dataset / 4D reconstruction / imitation learning
- Summary: EgoHTR introduces a scene-aligned egocentric reconstruction pipeline and dataset with 55 human terrain-traversal sequences and more than 150,000 frames, connecting contextual human motion capture to perceptive locomotion policies and reconstructed-reference deployment on Unitree G1 hardware.
- Notes: Project page: https://egohtr.github.io/. The paper says the reconstruction pipeline is open source and designed for community extensions, but the public project-site repository checked today exposed website assets rather than a separately documented code or dataset release; release readiness should be rechecked.

### Learning Agile Navigation in Crowded Environments for Quadruped Robots
- Link: https://arxiv.org/abs/2607.15036
- Source: arXiv
- Date: 2026-07-16
- Authors: Shuyu Wu, Zeyu Liu, Tianbao Zhang, Fanxing Li, Fangyu Sun, Mingkang Xiong, Wei Xi, Wenxian Yu, Danping Zou
- Topics: quadruped / crowded navigation / reinforcement learning / Velocity Obstacles / LiDAR / sim-to-real
- Summary: VOP-Nav uses multi-frame local LiDAR to predict a Velocity-Obstacle-derived safe velocity region, feeding that prediction to an end-to-end navigation policy at inference time and using it as a training reward, without explicit human detection, tracking, or global mapping.
- Notes: Evaluated in Isaac Gym and deployed on a Unitree Go2 in indoor and outdoor dynamic crowds. No official code repository was found during today's verification.

### Safe Execution of RL Policies Via Acceleration-Based CBF-QP Constraint Enforcement for Real-World Robotic Deployments
- Link: https://arxiv.org/abs/2607.14488
- Source: IROS 2026 / arXiv
- Date: 2026-07-16
- Authors: Bastien Muraccioli, Alice Cariou, Pierre-Alexandre Leziart, Mathieu Celerier, Arnaud Demont, Gentiane Venture, Mehdi Benallegue
- Topics: humanoid / safe reinforcement learning / control barrier function / quadratic programming / runtime safety / whole-body control
- Summary: Acc-CBF-QP filters an existing RL policy at acceleration level without modifying training, enforcing joint-position, velocity, torque, and collision constraints while regulating deviation from the original policy through torque- or forward-dynamics-based QP tasks.
- Notes: Accepted to IROS 2026 and validated in simulation and hardware on a 19-DoF Unitree H1 and 7-DoF Kinova Gen3. The project reports reducing H1 hardware violations from 10.04 to 0.80 per second, a 92% reduction. Project page: https://safe-rl-qp.github.io/.

### Scaling Behavior Foundation Model for Humanoid Robots
- Link: https://arxiv.org/abs/2607.15163
- Source: arXiv
- Date: 2026-07-16
- Authors: Weishuai Zeng, Kangning Yin, Xiaojie Niu, Shunlin Lu, Weixiang Zhong, Jiahe Chen, Feiyu Jia, Xiao Chen, Zirui Wang, Furui Xu, Ming Zhou, Kailin Li, Weinan Zhang, He Wang, Li Yi, Dahua Lin, Jiangmiao Pang, Jingbo Wang
- Topics: humanoid / behavior foundation model / motion tracking / reinforcement learning / Transformer / scaling
- Summary: ScaleBFM coordinates global-frame whole-body motion tracking, balanced scaling of on-policy rollout width and depth, heterogeneous reference-motion diversity, and a scalable Humanoid Transformer to improve reusable humanoid behavior learning and generalization in simulation and on hardware.
- Notes: The project aggregates more than 102 million human-motion frames at 50 FPS and reports test-set MPKPE reductions of over 10% in local mode and 82% in global mode relative to existing humanoid controllers. Project page: https://scalebfm.github.io/. The official repository currently contains a staged-release notice and expects most retargeting, training, and deployment code by 2026-07-26, so it is not counted as a mature repository today: https://github.com/zengweishuai/ScaleBFM.

### Semantic Audio-driven Understanding for Dynamic Humanoid Whole Body Control
- Link: https://arxiv.org/abs/2607.14182
- Source: RoboCup Symposium 2026 / arXiv
- Date: 2026-07-15
- Authors: J. M. A. Marcelo, M. Brienza, E. Bugli, L. Comito, D. Nardi, D. D. Bloisi, V. Suriani
- Topics: humanoid / whole-body control / reinforcement learning / audio grounding / skill orchestration / sim-to-real
- Summary: The system classifies continuous audio into music or speech, aligns music through fingerprinting and semantic embeddings or grounds speech into a discrete imitation-learned skill library, then schedules the selected whole-body policy through a shared reinforcement-learning control pipeline.
- Notes: Accepted at the 29th RoboCup International Symposium and validated in simulation and on a physical Unitree G1. The contribution is mainly semantic skill selection and orchestration over an existing multi-policy control stack rather than a new low-level locomotion learner. Project page: https://lab-rococo-sapienza.github.io/semantic-WBC/.

### Vision-Based Dribbling for Humanoid Soccer via Privileged Representation Learning
- Link: https://arxiv.org/abs/2607.12702
- Source: arXiv
- Date: 2026-07-14
- Authors: Flavio Maiorana, Valerio Spagnoli, Eugenio Bugli, Flavio Volpi, Daniele Affinita, Vincenzo Suriani, Daniele Nardi, Luca Iocchi
- Topics: humanoid / loco-manipulation / soccer / reinforcement learning / depth perception / privileged learning
- Summary: A temporal depth encoder is embedded into a reinforcement-learning policy through a task-specific projection layer, allowing a simulated Booster T1 humanoid to dribble toward targets and react to obstacles or an active opponent directly from depth observations without explicit scene-state estimation.
- Notes: The paper reports 100% success in nominal target-driven dribbling, 96% with one static obstacle, and 46% against an active ball-attacker. Results are simulation-only, and the lab's associated `learning-to-dribble` repository currently contains only a README and license rather than implementation code.

### Design and Control of the “QuadBoat”: A Quadruped Surface Vehicle for Drowning Rescue
- Link: https://arxiv.org/abs/2607.13633
- Source: arXiv
- Date: 2026-07-15
- Authors: Lianxin Zhang, Yihan Huang, Huihuan Qian
- Topics: quadruped morphology / unmanned surface vehicle / rescue robotics / model predictive control / visual tracking
- Summary: Presents an actively posture-adjustable quadruped-configured surface vehicle that combines inverse kinematics with cascaded MPC-PID control for agile water-surface motion, visual target tracking, and object retrieval.
- Notes: This is adjacent to conventional legged locomotion—the quadruped structure is used as a reconfigurable multi-hull watercraft—but it is a useful morphology-and-control signal for rescue robotics.

### PAKE: Learning Whole-Body Loco-Manipulation with Partial Kinematic Embeddings
- Link: https://arxiv.org/abs/2607.11041
- Source: arXiv
- Date: 2026-07-13
- Authors: Zhengmao He, Moonkyu Jung, Hyeongjun Kim, Jiseong Lee, Hui Zhang, Jemin Hwangbo, Jie Song
- Topics: quadruped / loco-manipulation / whole-body control / reinforcement learning / normalizing flows / sim-to-real
- Summary: Introduces a hierarchical framework in which a Kinematic Normalizing Flow encodes redundant torso-and-arm inverse-kinematic solutions, a high-level policy selects partial references in that latent space, and a low-level policy converts them into dynamically feasible full-body commands.
- Notes: Evaluated on a quadruped with a six-DoF arm; the paper reports 24 hardware episodes across eight tasks, including cart pulling, sweeping, charger insertion, and hanger placement, with 4.5 cm end-effector position error and 0.14 rad orientation error.

### Stop to Decide: Latency-Aware Proprioceptive Navigation Primitives for Mapping-Free Quadruped Inspection
- Link: https://arxiv.org/abs/2607.11204
- Source: arXiv
- Date: 2026-07-13
- Authors: Hanting Suo, Haonan Yan, Liang Wang, Aiguo Song
- Topics: quadruped / inspection / proprioceptive navigation / latency-aware control / stair traversal / mapping-free autonomy
- Summary: Develops a fully onboard, mapping-free and learning-free Unitree Go2 inspection stack whose climb-settle decision primitive remains reliable when shared Jetson Orin compute reduces the navigation loop to about 15 Hz.
- Notes: On the tested short-top stair platform, the settle-based protocol reduced pooled overshoot from 22/45 to 1/45 trials and the complete system finished the inspection course in 18/20 trials; results are limited to one course geometry, platform, and operator.

### Handroid: Bridging Dexterous Hand and Humanoid
- Link: https://arxiv.org/abs/2607.16187
- Source: arXiv
- Date: 2026-07-17
- Authors: Ruogu Li, Chenyang Ma, Sikai Li, Zhenyu Wei, Yunchao Yao, Haochen Shi, C. Karen Liu, Shuran Song, Mingyu Ding
- Topics: humanoid / dexterous hand / reconfigurable robot / reinforcement learning / locomotion / manipulation
- Summary: Handroid reuses one 27-DoF electromechanical platform as either a 20-DoF anthropomorphic hand or a desktop humanoid with 12-DoF lower limbs, providing shared control and learning interfaces for teleoperation, dexterous manipulation, RL locomotion, gait generation, and motion authoring.
- Notes: The 0.33 m, 2.05 kg platform is validated on real-world manipulation, walking and whole-body motions, plus a long-horizon sequence that reconfigures embodiment, walks, docks to a Franka arm, and performs dexterous pick-and-place. The paper states that the platform is open source; the project page is https://handroid.org/.

### RAVEN: Reinforcement-Adaptive Visibility-Graph Planning for Robust Humanoid Navigation with Collision-Free MPC
- Link: https://arxiv.org/abs/2607.15701
- Source: arXiv
- Date: 2026-07-17
- Authors: Ruochen Hou, Shiqi Wang, Beom Jun Kim, Hanzhang Fang, Mehak Singal, Dennis W. Hong
- Topics: humanoid / navigation / reinforcement learning / visibility graph / model predictive control / collision avoidance
- Summary: RAVEN uses an RL meta-policy to adapt obstacle inflation and the geometric construction of a visibility-graph planner, then applies collision-free MPC and a learned locomotion controller for interpretable long-horizon humanoid navigation under delay, observation noise, and tracking uncertainty.
- Notes: Evaluated against manually tuned visibility-graph MPC and pure-RL navigation, with reported improvements in obstacle overshoot, narrow-passage robustness, and reliability under uncertainty; the paper shows deployment on a Booster T1 biped in a half-size RoboCup field. No official code repository was found during today's verification.

### Beyond Transformers: Linear Attention Policy for Open-Vocabulary Object Goal Navigation
- Link: https://arxiv.org/abs/2607.18794
- Source: arXiv
- Date: 2026-07-21
- Authors: Jiahong Zhang, Yifan Lin, Yandong Zhang, Sijun Shen, Kexin Wang, Yuqi Pan, Hongjuan Pei, Wei Wang, Guoqi Li
- Topics: quadruped robots / open-vocabulary navigation / linear attention / robot learning / sim-to-real
- Summary: LANav uses linear-attention policy backbones as structured recurrent state updates and introduces weighted state-expansion linear attention to preserve useful history under partial observability.
- Notes: The reported HM3D-OVON macro-average success rate is 36.4%, 6.3 percentage points above the matched Transformer baseline. Transfer tests cover HSSD, and the real-world evaluation reports 82% success over 50 trials on a Unitree Go2.

### Koopman DCM: Unstable Eigenfunctions as Data-driven Representations for Legged Balancing
- Link: https://arxiv.org/abs/2607.18760
- Source: arXiv
- Date: 2026-07-21
- Authors: Stéphane Caron
- Topics: legged robots / biped balancing / Koopman operators / divergent component of motion / model predictive control
- Summary: The paper reinterprets the divergent component of motion as an unstable Koopman eigenfunction and learns that representation directly from closed-loop measurement-action data instead of restricting it to a linear inverted-pendulum model.
- Notes: Training uses one hour of real-robot data. The learned DCM improves reference-pattern tracking on a real biped, and simulated humanoid experiments use it as a hard state-based viability constraint inside MPC. The manuscript says accompanying code will be released after peer review, so no code is available yet.

### Extreme-RGMT: Continual Learning of Highly Dynamic Skills for Robust Generalist Humanoid Control
- Link: https://arxiv.org/abs/2607.20110
- Source: arXiv
- Date: 2026-07-22
- Authors: Yubiao Ma, Han Yu, Kai Guo, Changtai Lv, Zhengquan Mao, Boyang Xing, Xuemei Ren, Dongdong Zheng
- Topics: humanoid / whole-body motion tracking / continual learning / highly dynamic skills / teleoperation
- Summary: A two-stage framework that starts from a generalist motion-tracking policy, then acquires difficult dynamic skills while constraining policy drift on already-mastered motions.
- Notes: Difficulty-aware sampling and advantage-prioritized trajectory resampling target sparse critical segments; the paper and project page show Unitree G1 rollouts including aerial cartwheels, backflips, kip-ups, and online tracking from inertial motion capture. No training code was verified in this run.

### PGTT: Phase-Guided Terrain Traversal for Perceptive Legged Locomotion
- Link: https://arxiv.org/abs/2510.18348
- Source: arXiv / IROS 2026
- Date: 2026-07-22
- Authors: Alexandros Ntagkas, Chairi Kiourt, Konstantinos Chatzilygeroudis
- Topics: quadruped / perceptive locomotion / reinforcement learning / terrain adaptation / sim-to-real
- Summary: A perceptive deep-RL locomotion method that encodes per-leg phase through spline-based reward shaping while retaining direct joint-space actions, reducing dependence on morphology-specific oscillator or IK action priors.
- Notes: This is a v2 update to a 2025 preprint, now marked accepted at IROS 2026. The paper reports stronger disturbance and obstacle success than evaluated baselines, real Unitree Go2 validation with a LiDAR heightmap pipeline, and preliminary ANYmal-C transfer with the same hyperparameters.

### What Matters in Humanoid General Motion Tracking? An Empirical Study
- Link: https://arxiv.org/abs/2607.19903
- Source: arXiv
- Date: 2026-07-22
- Authors: Fabio Amadio, Enrico Mingo Hoffman
- Topics: humanoid / whole-body motion tracking / imitation learning / sim-to-real / Unitree G1
- Summary: A controlled empirical study of motion-command representation, observation history, action representation, actuation profile, hand-force randomization, and training approach in general humanoid motion tracking, implemented in the open-source YAHMP framework.
- Notes: The authors evaluate retargeted motions against a TWIST2 baseline trained on the same set and deploy policies zero-shot on a real Unitree G1, demonstrating diverse tracking, perturbation recovery, and forceful interaction.

</details>
