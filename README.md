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
| [robot_viewer](https://viewer.robotsfan.com/) | A web-based 3D viewer for robot models and scenes supporting URDF, MJCF (Mujoco XML), USD (partial support) formats.
| [netron](https://netron.app/) | A web-based viewer for neural network models, including those used in robotics research.
| [rokoko](https://vision.rokoko.com/) | Turn video to animation.
| [mujoco_wasm](https://zalo.github.io/mujoco_wasm/) | Simulate and Render MuJoCo Models in the Browser

### Repos

| Project | Description |
|--------|------- |
| [GMR](https://github.com/YanjieZe/GMR) | Retarget human motions into diverse humanoid robots in real time on CPU.
| [mink](https://github.com/kevinzakka/mink) | Python inverse kinematics based on MuJoCo
| [pyroki](https://github.com/chungmin99/pyroki) | A Modular Toolkit for Robot Kinematic Optimization
| [PlaCo](https://github.com/Rhoban/placo.git) | Task-space inverse kinematics and dynamics for whole-body control tasks
| [pinocchio](https://github.com/stack-of-tasks/pinocchio) | Rigid Body Dynamics algorithms and their analytical derivatives

---

## 📦 Project List

| Project | Tasks | Methods | Robots | Training simulator | Deploy | Description |
|--------|-------|------|------|------|------|-------------|
| [mjlab](https://github.com/mujocolab/mjlab.git) | Locomotion, Mimic | RL, IL | Humanoid (G1) & Quadruped (Go1) | Mujoco |  | Isaac Lab API, powered by MuJoCo-Warp, for RL and robotics research. |
| [unitree_rl_mjlab](https://github.com/unitreerobotics/unitree_rl_mjlab.git) | Locomotion, Mimic | RL, IL | Humanoid (H1_2, G1) & Quadruped (Go2)| Mujoco | Mujoco, HW | Real-world RL deployment on Unitree robots |
| [unitree_rl_lab](https://github.com/unitreerobotics/unitree_rl_lab) | Locomotion, Mimic | RL, IL | Humanoid (H1, G1) & Quadruped (Go2)| IsaacSim | Mujoco, HW | Real-world RL deployment on Unitree robots |
| [Stage-Wise CMORL](https://github.com/rllab-snu/Stage-Wise-CMORL/tree/main) | Acrobatics (Flip, Stand) | RL | Quadruped (Go1) | IsaacGym |  | Learning challenge acrobatic maneuvers for quadrupeds |
| [My_unitree_go2_gym](https://github.com/yusongmin1/My_unitree_go2_gym.git) | Locomotion (Trot, Hop), Acrobatics (~~Flip~~, Stand) | RL | Quadruped (Go2) | IsaacGym | Mujoco | |
| [TWIST2](https://github.com/amazon-far/TWIST2) | Teleoperation | IL | Humanoid (G1) | IsaacGym | Mujoco HW | Teleoperated Whole-Body Imitation System |
| [OCS2](https://github.com/leggedrobotics/ocs2/tree/ros2) | Locomotion | MB | Quadruped (Anymal) |  | Raisim | Optimal Control for Switched Systems |
| [Quadruped-PyMPC](https://github.com/iit-DLSLab/Quadruped-PyMPC/tree/main) | Locomotion | MB | Quadruped (Anymal) |  | Mujoco | Model Predictive Control for Quadrupedal Robots | A model predictive controller for quadruped robots based on the single rigid body model and written in python. Gradient-based (acados) or Sampling-based (jax) |
| [Cheetah-Software](https://github.com/mit-biomimetics/Cheetah-Software) | Locomotion | MB | Quadruped (MIT Cheetah) |  | custom | Software for the MIT Cheetah robot, including control and simulation tools. |

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
2. Methods
   - **IL**: Imitation learning / motion tracking
   - **RL**: Reinforcement learning
   - **MB**: Model-based control / optimization
3. Robots (Unitree G1/Go2 are explicitly noted when supported)
   - **Humanoid(W)**: (Wheeled) humanoid platforms
   - **Quadruped(W)**: (Wheeled) quadruped platforms
   - **Dual-Arm(W)**: (Wheeled) dual-arm platforms
   - **G1**: Unitree G1 humanoid
   - **Go2**: Unitree Go2 quadruped
4. Sim Platforms
   - **Mujoco**
   - **IsaacSim/Gym**
   - **Gazebo**
   - **Raisim**
   - **PyBullet**
5. Deployment
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


</details>

---

## 📚 Paper Lists

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
