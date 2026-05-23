# Repositories

> Long-term curated repository and toolkit list for legged robotics.

This file keeps repositories that are worth revisiting over time.
It is organized for fast browsing on GitHub and now follows the collapsible style used in the original README.

---

<details>
<summary><strong>Websites and Viewers</strong></summary>

### motion_viewer
- Link: https://renkunzhao.github.io/motion_viewer/
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: A web-based visualization tool for robot models and motion data.

### robot_viewer
- Link: https://viewer.robotsfan.com/
- Category: viewer
- Robot Type: general
- Simulator: general
- Deploy: browser
- Summary: A web-based 3D viewer for robot models and scenes supporting URDF, MJCF, and partial USD.

### netron
- Link: https://netron.app/
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: A web-based viewer for neural network models, including models used in robotics research.

### BVHView
- Link: https://theorangeduck.com/media/uploads/BVHView/bvhview.html
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: A simple viewer for `.bvh` animation files.

### sketchfab
- Link: https://sketchfab.com/feed#upload
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: A web-based FBX player and model viewer.

### rokoko
- Link: https://vision.rokoko.com/
- Category: motion generation
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: Converts video to animation.

### mjswan
- Link: https://github.com/ttktjmt/mjswan
- Category: simulator
- Robot Type: general
- Simulator: MuJoCo
- Deploy: browser
- Summary: MuJoCo simulation on WebAssembly with neural networks.

### mujoco_wasm
- Link: https://zalo.github.io/mujoco_wasm/
- Category: simulator
- Robot Type: general
- Simulator: MuJoCo
- Deploy: browser
- Summary: Simulate and render MuJoCo models in the browser.

</details>

<details>
<summary><strong>Control, Kinematics, Dynamics, and Optimization</strong></summary>

### mink
- Link: https://github.com/kevinzakka/mink
- Category: control
- Robot Type: general
- Simulator: MuJoCo
- Deploy: sim
- Summary: Python inverse kinematics based on MuJoCo.

### pyroki
- Link: https://github.com/chungmin99/pyroki
- Category: control
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: A modular toolkit for robot kinematic optimization.

### PlaCo
- Link: https://github.com/Rhoban/placo.git
- Category: control
- Robot Type: humanoid / general
- Simulator: none
- Deploy: sim
- Summary: Task-space inverse kinematics and dynamics for whole-body control tasks.

### cuRobo
- Link: https://github.com/NVlabs/curobo
- Category: control
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: CUDA-accelerated robotics algorithms including FK, IK, and trajectory optimization.

### pinocchio
- Link: https://github.com/stack-of-tasks/pinocchio
- Category: dynamics
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: Rigid body dynamics algorithms and analytical derivatives.

### se3_trajopt
- Link: https://github.com/upatras-lar/se3_trajopt
- Category: optimization
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: Trajectory optimization on the SE(3) tangent space.

</details>

<details>
<summary><strong>Simulators and Models</strong></summary>

### sofa
- Link: https://github.com/sofa-framework/sofa
- Category: simulator
- Robot Type: general
- Simulator: SOFA
- Deploy: sim
- Summary: Real-time multi-physics simulation with emphasis on medical and deformable simulation.

### chrono
- Link: https://github.com/projectchrono/chrono
- Category: simulator
- Robot Type: general
- Simulator: Chrono
- Deploy: sim
- Summary: High-performance multiphysics and multibody simulation library.

### mujoco_menagerie
- Link: https://github.com/google-deepmind/mujoco_menagerie.git
- Category: model collection
- Robot Type: humanoid / quadruped / general
- Simulator: MuJoCo
- Deploy: sim
- Summary: A collection of high-quality MuJoCo models curated by Google DeepMind.

</details>

<details>
<summary><strong>Datasets and Models</strong></summary>

### KungFuAthleteBot
- Link: https://github.com/NPCLEI/KungFuAthleteBot.git
- Category: dataset
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Athlete martial arts training videos processed using GVHMR.

### BONES-SEED
- Link: https://huggingface.co/datasets/bones-studio/seed
- Category: dataset
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Large-scale annotated human motion dataset with SOMA and Unitree G1 formats.

### SOMA-X
- Link: https://github.com/NVlabs/SOMA-X.git
- Category: model
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Canonical body topology and rig for supported parametric human body models.

### grand_tour_dataset
- Link: https://github.com/leggedrobotics/grand_tour_dataset
- Category: dataset
- Robot Type: quadruped
- Simulator: none
- Deploy: data
- Summary: Official starter repository for the GrandTour legged-robotics dataset with Hugging Face examples, ROS1 examples, and Python utilities.
- Notes: Companion tooling for the GrandTour dataset release from ETH RSL.

</details>

<details>
<summary><strong>Motion Generation, Retargeting, and Editing</strong></summary>

### GMR
- Link: https://github.com/YanjieZe/GMR
- Category: retargeting
- Robot Type: humanoid
- Simulator: none
- Deploy: sim
- Summary: Real-time human motion retargeting to diverse humanoid robots.

### SOMA Retargeter
- Link: https://github.com/NVIDIA/soma-retargeter.git
- Category: retargeting
- Robot Type: humanoid
- Simulator: Newton / Warp
- Deploy: sim
- Summary: BVH-to-humanoid robot motion retargeting library.

### Kimodo
- Link: https://research.nvidia.com/labs/sil/projects/kimodo/
- Category: motion generation
- Robot Type: human / humanoid
- Simulator: none
- Deploy: sim
- Summary: Kinematic motion diffusion model for text- and constraint-driven motion generation.

### GEM-X
- Link: https://github.com/NVlabs/GEM-X.git
- Category: pose estimation
- Robot Type: humanoid
- Simulator: none
- Deploy: sim
- Summary: Monocular whole-body 3D human pose estimation using the SOMA body model.

</details>

<details>
<summary><strong>Reinforcement Learning</strong></summary>

### mjlab
- Link: https://github.com/mujocolab/mjlab.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: Isaac Lab API powered by MuJoCo-Warp for RL and robotics research.

### mujoco_playground
- Link: https://github.com/google-deepmind/mujoco_playground.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: GPU-accelerated library for robot learning and sim-to-real transfer.

### unitree_rl_mjlab
- Link: https://github.com/unitreerobotics/unitree_rl_mjlab.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim / hardware
- Summary: Real-world RL deployment pipeline for Unitree robots using MuJoCo.

### unitree_rl_lab
- Link: https://github.com/unitreerobotics/unitree_rl_lab
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: IsaacSim
- Deploy: sim / hardware
- Summary: Real-world RL deployment pipeline for Unitree robots using IsaacSim.

### Stage-Wise CMORL
- Link: https://github.com/rllab-snu/Stage-Wise-CMORL/tree/main
- Category: RL
- Robot Type: quadruped
- Simulator: IsaacGym
- Deploy: sim
- Summary: Stage-wise curriculum RL for acrobatic maneuvers in quadrupeds.

### My_unitree_go2_gym
- Link: https://github.com/yusongmin1/My_unitree_go2_gym.git
- Category: RL
- Robot Type: quadruped
- Simulator: IsaacGym
- Deploy: sim / MuJoCo
- Summary: Locomotion and acrobatics work for Unitree Go2.

### TWIST2
- Link: https://github.com/amazon-far/TWIST2
- Category: RL / teleoperation
- Robot Type: humanoid
- Simulator: IsaacGym
- Deploy: MuJoCo / hardware
- Summary: Teleoperated whole-body imitation system.

### SONIC
- Link: https://nvlabs.github.io/GEAR-SONIC/
- Category: motion tracking
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: Large-scale humanoid whole-body motion tracking work.

### OmniXtreme
- Link: https://extreme-humanoid.github.io/
- Category: motion tracking
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: Unified policy framework for high-dynamic humanoid motion tracking.

</details>

<details>
<summary><strong>Humanoid Whole-Body Control</strong></summary>

### GR00T-WholeBodyControl
- Link: https://github.com/NVlabs/GR00T-WholeBodyControl
- Category: control / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / hardware
- Summary: Unified NVIDIA GEAR platform for humanoid whole-body control, teleoperation, deployment, and SONIC-based training workflows.
- Notes: Strong current reference for Unitree G1-oriented whole-body control and teleop-to-deployment workflows.

</details>

<details>
<summary><strong>MPC and Model-Based Control</strong></summary>

### OCS2
- Link: https://github.com/leggedrobotics/ocs2/tree/ros2
- Category: MPC
- Robot Type: quadruped
- Simulator: Raisim
- Deploy: sim
- Summary: Optimal control for switched systems with strong legged locomotion applications.

### MuJoCo MPC
- Link: https://github.com/google-deepmind/mujoco_mpc
- Category: MPC
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: Real-time predictive control framework built on MuJoCo.

### DIAL-MPC
- Link: https://github.com/LeCAR-Lab/dial-mpc
- Category: MPC
- Robot Type: quadruped
- Simulator: none
- Deploy: sim
- Summary: Sampling-based MPC for full-order torque-level legged control.

### Quadruped-PyMPC
- Link: https://github.com/iit-DLSLab/Quadruped-PyMPC/tree/main
- Category: MPC
- Robot Type: quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: Python MPC for quadruped robots using SRBM and gradient-based or sampling-based solvers.

### Cheetah-Software
- Link: https://github.com/mit-biomimetics/Cheetah-Software
- Category: MPC / control
- Robot Type: quadruped
- Simulator: custom
- Deploy: sim / hardware
- Summary: Software stack for MIT Cheetah robots.

</details>