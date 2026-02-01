# Legged Robotics Open-source Projects

A curated index of open-source legged robotics projects spanning **model-based control**, **reinforcement learning**, **imitation learning**, **humanoids**, **quadrupeds**, and **simulation platforms**.

Built to help researchers quickly discover, categorize, and compare relevant work.

---

## Toolkits

| Project | Description |
|--------|------- |
| [robot_viewer](https://viewer.robotsfan.com/) | A web-based 3D viewer for robot models and scenes supporting URDF, MJCF (Mujoco XML), USD (partial support) formats.
| [mink](https://github.com/kevinzakka/mink) | Python inverse kinematics based on MuJoCo
| [pyroki](https://github.com/chungmin99/pyroki) | A Modular Toolkit for Robot Kinematic Optimization
| [pinocchio](https://github.com/stack-of-tasks/pinocchio) | Rigid Body Dynamics algorithms and their analytical derivatives

---

## 📦 Project List

| Project | Tasks | Methods | Robots | Trainning simulator | Deploy | Description |
|--------|-------|------|------|------|------|-------------|
| [unitree_rl_lab](https://github.com/unitreerobotics/unitree_rl_lab) | Locomotion, Mimic | RL, IL | Humanoid (H1, G1) & Quadruped (Go2)| IsaacSim | HW | Real-world RL deployment on Unitree robots |
| [Stage-Wise CMORL](https://github.com/rllab-snu/Stage-Wise-CMORL/tree/main) | Acrobatics (Flip, Stand) | RL | Quadruped (Go1) | IsaacGym | None | Learning challenge acrobatic maneuvers for quadrupeds |
| [My_unitree_go2_gym](https://github.com/yusongmin1/My_unitree_go2_gym.git) | Locomotion (Trot, Hop), Acrobatics (Flip, Stand) | RL | Quadruped (Go2) | IsaacGym | Mujoco | |

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
