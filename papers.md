# Papers

> Long-term curated paper list for legged robotics.

This file is for **persistent retrieval**, not daily triage.
Use it for papers that remain useful after the day they were discovered.

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
- Notes: Code link in the original README points to https://github.com/leggedrobotics/robotic_world_model.git.

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
