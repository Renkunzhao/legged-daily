# Legged Robotics Research Index

A curated, research-oriented index for **legged robotics**, covering:

- **Open-source projects and toolkits**
- **Researchers and research groups**
- **Learning-based and model-based control methods**
- **Humanoids and quadrupeds**
- **Simulation platforms and sim-to-real deployment**

This repository is designed to support **research discovery, orientation, and long-term reference**
for students and researchers working on legged locomotion and related areas.

> This repository is a **curated index**, not a benchmark, ranking, or evaluation.
> All entries are based on **publicly available information** and reflect
> representative research directions rather than exhaustive coverage.

---

## Toolkits

### Websites

| Project | Description |
|--------|------- |
| [motion_viewer](https://renkunzhao.github.io/motion_viewer/) | A web-based visualization tool for robot models and motion data.
| [robot_viewer](https://viewer.robotsfan.com/) | A web-based 3D viewer for robot models and scenes supporting URDF, MJCF (Mujoco XML), USD (partial support) formats.
| [netron](https://netron.app/) | A web-based viewer for neural network models, including those used in robotics research.
| [BVHView](https://theorangeduck.com/media/uploads/BVHView/bvhview.html) | A simple viewer for the .bvh animation file format written using raylib.
| [sketchfab](https://sketchfab.com/feed#upload) | A web-based fbx player, login is needed.
| [rokoko](https://vision.rokoko.com/) | Turn video to animation.
| [mjswan](https://github.com/ttktjmt/mjswan) | MuJoco Simulation on Web Assembly with Neural netwroks.
| [mujoco_wasm](https://zalo.github.io/mujoco_wasm/) | Simulate and Render MuJoCo Models in the Browser.

### Repos

| Project | Description |
|--------|------- |
| [GMR](https://github.com/YanjieZe/GMR) | Retarget human motions into diverse humanoid robots in real time on CPU.
| [mink](https://github.com/kevinzakka/mink) | Python inverse kinematics based on MuJoCo
| [pyroki](https://github.com/chungmin99/pyroki) | A Modular Toolkit for Robot Kinematic Optimization
| [PlaCo](https://github.com/Rhoban/placo.git) | Task-space inverse kinematics and dynamics for whole-body control tasks
| [cuRobo](https://github.com/NVlabs/curobo) | A CUDA accelerated library containing a suite of robotics algorithms (FK, IK, TO).
| [pinocchio](https://github.com/stack-of-tasks/pinocchio) | Rigid Body Dynamics algorithms and their analytical derivatives
| [MuJoCo](https://github.com/google-deepmind/mujoco.git) | Multi-Joint dynamics with Contact. A general purpose physics simulator.
| [mujoco_menagerie](https://github.com/google-deepmind/mujoco_menagerie.git) | A collection of high-quality models for the MuJoCo physics engine, curated by Google DeepMind.

### Dataset
| Project | Description |
|--------|------- |
| [KungFuAthleteBot](https://github.com/NPCLEI/KungFuAthleteBot.git) | Athletes’ daily martial arts training videos processed using GVHMR.

---

## 📦 Project List

### RL
| Project | Tasks | Robots | Training simulator | Deploy | Description |
|--------|-------|------|------|------|-------------|
| [mjlab](https://github.com/mujocolab/mjlab.git) | Locomotion, Mimic | Humanoid (G1) & Quadruped (Go1) | Mujoco |  | Isaac Lab API, powered by MuJoCo-Warp, for RL and robotics research. |
| [mujoco_playground](https://github.com/google-deepmind/mujoco_playground.git) | Locomotion | Humanoid (G1, H1) & Quadruped (Go1) | Mujoco | | An open-source library for GPU-accelerated robot learning and sim-to-real transfer.
| [unitree_rl_mjlab](https://github.com/unitreerobotics/unitree_rl_mjlab.git) | Locomotion, Mimic | Humanoid (H1_2, G1) & Quadruped (Go2)| Mujoco | Mujoco, HW | Real-world RL deployment on Unitree robots |
| [unitree_rl_lab](https://github.com/unitreerobotics/unitree_rl_lab) | Locomotion, Mimic | Humanoid (H1, G1) & Quadruped (Go2)| IsaacSim | Mujoco, HW | Real-world RL deployment on Unitree robots |
| [Stage-Wise CMORL](https://github.com/rllab-snu/Stage-Wise-CMORL/tree/main) | Acrobatics (Flip, Stand) | Quadruped (Go1) | IsaacGym |  | Learning challenge acrobatic maneuvers for quadrupeds |
| [My_unitree_go2_gym](https://github.com/yusongmin1/My_unitree_go2_gym.git) | Locomotion (Trot, Hop), Acrobatics (~~Flip~~, Stand) | Quadruped (Go2) | IsaacGym | Mujoco | |
| [TWIST2](https://github.com/amazon-far/TWIST2) | Teleoperation | Humanoid (G1) | IsaacGym | Mujoco HW | Teleoperated Whole-Body Imitation System |
| [OmniXtreme](https://extreme-humanoid.github.io/) | Mimic | Humanoid (G1) |  | HW | A unified policy framework for high-dynamic humanoid motion tracking |

### Optimization
| Project | Tasks | Robots | Deploy | Description |
|--------|-------|------|------|-------------|
| [OCS2](https://github.com/leggedrobotics/ocs2/tree/ros2) | Locomotion | Quadruped (Anymal) | Raisim | Optimal Control for Switched Systems |
| [MuJoCo MPC](https://github.com/google-deepmind/mujoco_mpc) | Locomotion & Acrobatics | Humanoid & Quadruped | Mujoco | An interactive application and software framework for real-time predictive control with MuJoCo, developed by Google DeepMind |
| [DIAL-MPC](https://github.com/LeCAR-Lab/dial-mpc) | Locomotion & Acrobatics | Quadruped (go2) |  |  A novel sampling-based MPC framework for legged robot full-order torque-level control with both precision and agility in a training-free manner. |
| [se3_trajopt](https://github.com/upatras-lar/se3_trajopt) | Locomotion & Acrobatics | Humanoid & Quadruped (go2) |  |  Trajectory Optimization on the SE(3) Tangent Space. |
| [Quadruped-PyMPC](https://github.com/iit-DLSLab/Quadruped-PyMPC/tree/main) | Locomotion | Quadruped | Mujoco | Model Predictive Control for Quadrupedal Robots | A model predictive controller for quadruped robots based on the single rigid body model and written in python. Gradient-based (acados) or Sampling-based (jax) |
| [Cheetah-Software](https://github.com/mit-biomimetics/Cheetah-Software) | Locomotion | Quadruped (MIT Cheetah) | custom | Software for the MIT Cheetah robot, including control and simulation tools. |

## 🔖 Tag Legend

Use tags to mix and match method, robot, simulator, and deployment.

1. Tasks
   - **Locomotion**: Walking/running on flat or uneven terrain using various gait type
   - **Mimic**: Mimic motion from human
   - **Acrobatics**: Parkour, jumps, flips, handstands, dancing
     - **Parkour/Agility**: Dynamic, complex movement sequences
     - **Jump**: Vertical or gap-clearing jumps
     - **Flip**: Aerial rotations (front/back)
     - **Handstand/Legstand**: Inverted balancing poses
     - **Ground Parkour/Rolling**: Falling, rolling, and getting up
   - **Perception/Navigation**: Stairs, gaps, obstacles, uneven surfaces
   - **Manipulation**: Coordinated arm-leg or multi-limb actions
2. Robots (Unitree G1/Go2 are explicitly noted when supported)
   - **Humanoid(W)**: (Wheeled) humanoid platforms
   - **Quadruped(W)**: (Wheeled) quadruped platforms
   - **Dual-Arm(W)**: (Wheeled) dual-arm platforms
   - **G1**: Unitree G1 humanoid
   - **Go2**: Unitree Go2 quadruped
3. Sim Platforms
   - **Mujoco**
   - **IsaacSim/Gym**
   - **Gazebo**
   - **Raisim**
   - **PyBullet**
4. Deployment
   - **Sim**: Simulation-focused
   - **HW**: Hardware deployment

---

## 👩‍🔬👨‍🔬 Researchers (by Region)

A curated, non-exhaustive index of researchers in legged robotics and related areas.
The list is organized **by region/institution** to avoid rigid topical classification.
Entries are intended for **research discovery and reference**, not ranking or evaluation.

<details>
<summary><strong>🇺🇸 North America</strong></summary>

   <!--  -->
   - <details>
      <summary><strong>Xue Bin (Jason) Peng — SFU</strong></summary>

      - Research Interests: 
         Computer graphics and machine learning, with a focus on reinforcement learning for motion control of simulated characters

      - [Website](https://xbpeng.github.io/) | [Google Scholar](https://scholar.google.com/citations?user=FwxfQosAAAAJ&hl=en)

      - Notable Works:
         - [MimicKit](https://github.com/xbpeng/MimicKit): A framework for imitation learning of physics-based character skills using reinforcement learning.

      </details>

   <!--  -->
   - <details>
      <summary><strong>Zixuan (Eric) Chen (PhD) — UCSD</strong></summary>

      - Research Interests: 
         General intelligent humanoid robots, including robust locomotion and general manipulation.

      - [Website](https://zixuan417.github.io/) | [Google Scholar](https://scholar.google.com/citations?user=lmsiq6oAAAAJ&hl=en)

      - Notable Works:
         - [GMT](https://github.com/zixuan417/humanoid-general-motion-tracking): General Motion Tracking for Humanoid Whole-Body Control.

      </details>  

   <!--  -->
   - <details>
      <summary><strong>Yanjie Ze (PhD) — Standford</strong></summary>

      - Research Interests: 
         General intelligent humanoid robots.

      - [Website](https://yanjieze.com/) | [Google Scholar](https://scholar.google.com/citations?user=BO_b2O8AAAAJ&hl=zh-CN&oi=ao)

      - Notable Works:
         - [TWIST2](https://github.com/amazon-far/TWIST2): Scalable, Portable, and Holistic Humanoid Data Collection System.
         - [TWIST](https://github.com/YanjieZe/TWIST): TWIST: Teleoperated Whole-Body Imitation System.
         - [GMR](https://github.com/YanjieZe/GMR): Retarget human motions into diverse humanoid robots in real time on CPU.

      </details>

</details>

---

<details>
<summary><strong>🇪🇺 Europe</strong></summary>


</details>

---

<details>
<summary><strong>🇨🇳 Asia</strong></summary>

   <!--  -->
   - <details>
      <summary><strong>Siyuan Huang — PKU</strong></summary>

      - Research Interests: 
         Computer vision, robotics, machine learning, and cognition.

      - [Website](https://siyuanhuang.com/) | [Google Scholar](https://scholar.google.com/citations?user=1NN7Ee8AAAAJ&hl=en&citsig=AMstHGQ_eDX956QVraGalRBAEWGG0ltzRw)

      - Notable Works:
         - [OmniXtreme](https://extreme-humanoid.github.io/): A unified policy framework for high-dynamic humanoid motion tracking.
         - [CLONE](https://humanoid-clone.github.io/): A whole-body teleoperation system that achieves comprehensive robot control using a VR headset.

      </details>

   <!--  -->
   - <details>
      <summary><strong>Li Yi — THU</strong></summary>

      - Research Interests: 
         3D perception, humanoid robot learning, and human-robot interaction, with the goal of equipping robotic agent with the ability of understanding and interacting with the 3D world.

      - [Website](https://ericyi.github.io/) | [Google Scholar](https://scholar.google.com/citations?user=UyZL660AAAAJ&hl=en) | [X](https://x.com/ericyi0124)

      - Notable Works:
         - [Any2Track](https://zzk273.github.io/Any2Track/): Track Any Motions under Any Disturbances.
         - [Humanoid-GPT](https://qizekun.github.io/humanoid-gpt/): A GPT-style Transformer with causal attention trained on a billion-scale motion corpus for whole-body control.

      </details>

</details>

---

## 📚 Paper Lists

<details>
<summary><strong>Basic</strong></summary>

- [Rigid Body Dynamics Algorithms](resources/books/Rigid%20Body%20Dynamics%20Algorithms.pdf)

- [仿人机器人](resources/books/仿人机器人.pdf)

- [Robot Dynamics Lecture Notes - ETH](https://ethz.ch/content/dam/ethz/special-interest/mavt/robotics-n-intelligent-systems/rsl-dam/documents/RobotDynamics2017/RD_HS2017script.pdf)

</details>

<details>
<summary><strong>DAPC</strong></summary>

- [Learning quadrupedal locomotion on deformable terrain](https://www.science.org/doi/pdf/10.1126/scirobotics.ade2256)

   - Method: They train a quadruped RL policy in simulation using a fast, parameterized deformable-terrain contact model (normal penetration + shear/friction + horizontal drag) with broad terrain parameter randomization. A recurrent (RNN) policy uses proprioceptive history to implicitly infer the current ground properties and adapt online at deployment. 
   
   - Result: a single controller transfers to hardware and achieves fast, robust locomotion on granular media (e.g., sand) and highly compliant surfaces (e.g., air mattress) without explicit terrain estimation.

- [Data-Enabled Predictive Control: In the Shallows of the DeePC](https://arxiv.org/pdf/1811.05890)

- [Toward a Data-Driven Template Model for Quadrupedal Locomotion](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9799758)

- [Deep DeePC: Data-enabled predictive control with low or no online optimization using deep learning](https://aiche.onlinelibrary.wiley.com/doi/pdf/10.1002/aic.18644)

</details>

---

## 📚 Surveys & Collections

<details>
<summary><strong>Survey / Awesome Lists</strong></summary>

- [many-quadrupeds](https://github.com/beduffy/many-quadrupeds)

</details>

---


## ✍️ Notes

- This list is **not exhaustive** and will evolve.
- Tags reflect the **primary contribution**; secondary aspects may be omitted for brevity.
- Contributions and suggestions are welcome.
