**English** | [中文](zh/repos.md)
# Repositories

> Long-term curated repository and toolkit list for legged robotics.

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

### BARD PyTorch Dynamics
- Link: https://github.com/YueWang996/bard-pytorch-dynamics
- Category: dynamics / toolkit
- Robot Type: general / quadruped
- Simulator: Isaac Lab integration reported in paper
- Deploy: sim
- Summary: PyTorch-native rigid-body dynamics library for URDF-loaded robots with batched CPU/GPU computation, autograd, floating-base support, FK, Jacobians, RNEA, ABA, and CRBA.
- Notes: GitHub README reports PyTorch-native ML workflow integration and benchmark comparisons against Pinocchio; arXiv paper reports use inside an 11-DOF spined quadruped AMP pipeline.

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

### mujoco_ros2_control
- Link: https://github.com/ros-controls/mujoco_ros2_control
- Category: control / simulator / sensor simulation / ROS 2 integration
- Robot Type: general / quadruped / humanoid
- Simulator: MuJoCo
- Deploy: sim / ROS 2
- Summary: Official ROS Controls integration that exposes MuJoCo robots as a `ros2_control` system interface, with MJCF/URDF model workflows, controller support, and extensible ROS 2 simulation plugins.
- Notes: Particularly valuable for perception-enabled legged-robot simulation: its camera plugin automatically publishes RGB images, depth images, and `CameraInfo` for MJCF cameras, supports multiple RGB-D cameras and EGL-based headless GPU rendering, while the bundled ray-casting lidar extension supports configurable 2D/3D scans, horizontal/vertical resolution and field of view, range limits, and update rate. A legacy rangefinder-lidar plugin is also retained, but the project recommends the newer 3D lidar extension.

### MuJoCo-LiDAR
- Link: https://github.com/discoverse-dev/MuJoCo-LiDAR
- Category: simulator / sensor simulation / perception toolkit
- Robot Type: general / quadruped / humanoid
- Simulator: MuJoCo
- Deploy: sim / ROS1 / ROS2
- Summary: High-performance LiDAR simulation for MuJoCo with CPU, Taichi, JAX, and NVIDIA Warp backends, multiple LiDAR scan patterns, Unitree Go2 / G1 examples, and ROS integration.
- Notes: Useful for legged-robot perception and navigation simulation because it supports GPU ray casting, batched scenes, dynamic meshes, MJX/JAX workflows, and common LiDAR models such as Velodyne, Livox, and Ouster.

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

### rl_sar
- Link: https://github.com/fan-ziqi/rl_sar
- Category: RL / deployment / simulator / toolkit
- Robot Type: quadruped / wheeled-legged / humanoid
- Simulator: IsaacGym / IsaacSim / Gazebo / MuJoCo
- Deploy: sim / hardware
- Summary: Simulation-verification and real-robot deployment framework for reinforcement-learning policies across quadrupeds, wheeled-legged robots, and humanoids.
- Notes: Supports ROS Noetic, ROS 2 Foxy/Humble, libtorch, onnxruntime, Linux, and partial macOS MuJoCo simulation; README lists Unitree A1/Go2/Go2W/B2/B2W/G1, Fourier GR1, zhiniao L4W4, Deeprobotics Lite3, Agibot D1, and DDTRobot Tita support.

### LeggedSkillDeploy
- Link: https://github.com/haozhang04/LeggedSkillDeploy
- Category: RL / deployment / simulator / toolkit
- Robot Type: quadruped / humanoid / wheeled-biped / wheeled-quadruped
- Simulator: MuJoCo / Gazebo (ROS 2)
- Deploy: sim / hardware
- Summary: State-machine-based Python framework for deploying multiple reinforcement-learning and imitation-learning motion policies across legged robot embodiments.
- Notes: Includes policies and configurations for Unitree Go1/Go2, Go2W, G1 (29 DoF), Duow, and M20; supports keyboard, gamepad, and phone-web control. The README reports hardware testing only on Go1 Pro and warns that real-robot deployment requires appropriate safety precautions and interface adaptation.

### legged_rl_lab
- Link: https://github.com/zhw0422/legged_rl_lab
- Category: RL / simulator / toolkit
- Robot Type: humanoid / quadruped / general
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim / sim2sim2real
- Summary: Isaac Lab-based legged-RL training stack for Unitree Go1, Go2, and G1, including rough-terrain walking, G1 AMP, depth parkour, and cross-embodiment experiments.
- Notes: Documents RSL-RL training, multi-GPU training, cross-embodied G1+Go2 tasks, morphology encoders, retargeted motion data, and skrl AMP alternatives.

### BipedRobot
- Link: https://github.com/AsterisCrack/BipedRobot
- Category: RL / simulator / hardware / imitation learning
- Robot Type: biped / humanoid-adjacent
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / hardware
- Summary: Custom biped locomotion project with a physical 12-DoF robot, Isaac Lab and MuJoCo environments, custom RL algorithms, motion imitation, and sim-to-real randomization.
- Notes: Technically detailed individual project rather than a widely adopted lab framework.


### UniLab
- Link: https://github.com/unilabsim/UniLab
- Category: RL / simulator / heterogeneous training runtime / toolkit
- Robot Type: quadruped / humanoid / wheeled-legged / dexterous hand / manipulator
- Simulator: MuJoCoUni / MotrixSim
- Deploy: sim / hardware
- Summary: Official repository for UniLab, a heterogeneous robot-RL training framework that runs CPU physics simulation and GPU policy learning asynchronously through a shared-memory runtime, with unified CLI support for PPO, APPO, SAC, TD3, FlashSAC, HORA, and HIM-PPO across CUDA, Apple Silicon, ROCm, and Intel XPU.
- Notes: Released demos and tasks include Go1/Go2 locomotion, Unitree G1 walk / dance / motion tracking / backflip / climb / box tracking, Go2W wheeled-leg locomotion, Sharpa / Allegro dexterous manipulation, and Go2+arm loco-manipulation; project page: https://unilabsim.github.io/.
### SoftMimic
- Link: https://github.com/Improbable-AI/softmimic
- Category: RL / imitation learning / whole-body control / deployment
- Robot Type: humanoid
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / hardware
- Summary: Official implementation of SoftMimic for compliant Unitree G1 whole-body motion imitation, including compliant-motion augmentation, Isaac Lab training/evaluation, pretrained policies, MuJoCo rollout, and deployment utilities.
- Notes: From MIT Improbable AI Lab; depends on Isaac Lab, RSL-RL, Mink, MuJoCo, and Unitree SDK2, and is distributed under an MIT license.

### ASAP-G1-RL
- Link: https://github.com/Lurrkkking/ASAP-G1-RL
- Category: RL / imitation learning / simulator / sim-to-sim
- Robot Type: humanoid
- Simulator: Isaac Gym / Genesis / MuJoCo
- Deploy: sim
- Summary: Unitree G1 experiment repository built on ASAP, covering motion tracking, rough-terrain locomotion, MuJoCo-to-IsaacGym residual-action reproduction, closed-loop fine-tuning, and football kickup / juggling task redesign.
- Notes: Individual experiment repo rather than a mature reusable framework; useful for ASAP-style residual action learning and Unitree G1 task-design references.

### legged-locomotion-control
- Link: https://github.com/BrilliantCarrot/legged-locomotion-control
- Category: RL / simulator / navigation / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim / ROS 2 integration
- Summary: Unitree Go2 locomotion-control workspace for Isaac Lab PPO experiments, gait/contact analysis, terrain and domain randomization, disturbance testing, and ROS 2 navigation command generation.
- Notes: Small transparent educational / experiment-log style workspace; useful for Go2 pretrained-policy probes, reward tracking, joint-limit analysis, and ROS 2 command integration.

### BeamDojo
- Link: https://why618188.github.io/beamdojo/
- Category: RL / perceptive locomotion / sparse footholds / deployment
- Robot Type: humanoid
- Simulator: simulation training (implementation not publicly specified)
- Deploy: sim / hardware
- Summary: Two-stage reinforcement-learning framework for agile Unitree G1 locomotion on sparse footholds, combining a polygon-foot foothold reward, double critics, and a LiDAR-based elevation map for real-world deployment.
- Notes: RSS 2025 project page and paper rather than a public code repository; reports stepping-stone and balance-beam traversal, zero-shot terrain transfer, and an 80% sim-to-real success rate.

### extreme-parkour
- Link: https://github.com/chengxuxin/extreme-parkour
- Category: RL / simulator / parkour / deployment
- Robot Type: quadruped
- Simulator: Isaac Gym
- Deploy: sim / hardware
- Summary: Official ICRA 2024 implementation of Extreme Parkour, training an end-to-end depth-camera policy for dynamic quadruped obstacle traversal with a base-policy and vision-policy distillation pipeline.
- Notes: Built on legged_gym and RSL-RL; the README documents training, playback, JIT export, and browser visualization, and reports roughly 15-20 hours of training on an RTX 3090.

### parkour
- Link: https://github.com/ZiwenZhuang/parkour
- Category: RL / simulator / parkour / deployment
- Robot Type: quadruped
- Simulator: Isaac Gym
- Deploy: sim / hardware
- Summary: Official code for Robot Parkour Learning, a CoRL 2023 oral project for training quadruped parkour policies with legged_gym and RSL-RL, including A1 / Go1 / Go2 training and deployment materials.
- Notes: Project page: https://robot-parkour.github.io/. README reports Go1 and Go2 deployment guides and lists the paper as CoRL 2023 Oral and Best Systems Paper Award Finalist.

### Isaaclab_Parkour
- Link: https://github.com/CAI23sbP/Isaaclab_Parkour
- Category: RL / simulator / parkour / deployment
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / sim2sim / hardware planned
- Summary: Isaac Lab-based Unitree Go2 parkour locomotion project derived from Extreme Parkour, with teacher/student RSL-RL training, play, evaluation, and demo tasks.
- Notes: README references downloadable teacher/student policies, Isaac Lab-to-MuJoCo sim2sim work, future real-world deployment via go2_parkour_deploy, and required citation of Extreme Parkour and ORBIT.

### go2_parkour_deploy
- Link: https://github.com/CAI23sbP/go2_parkour_deploy
- Category: deployment / sim2sim / simulator / parkour
- Robot Type: quadruped
- Simulator: MuJoCo / Isaac Lab policy source
- Deploy: sim / hardware
- Summary: Unitree Go2 deployment companion for IsaacLab_Parkour policies, supporting Isaac Lab-to-MuJoCo simulation deployment and real-world Go2 deployment.
- Notes: Requires Unitree MuJoCo; README cites influence from Go2Py, HOVER, Eurekaverse, Spot RL Example, and gym-quadruped.

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

### LeRobot Humanoid
- Link: https://github.com/Virgileboat/lerobot-humanoid
- Category: toolkit / hardware / simulator / identification / runtime
- Robot Type: humanoid
- Simulator: MuJoCo / MJLab
- Deploy: sim / hardware
- Summary: Full-stack open low-cost humanoid project from the Hugging Face / LeRobot ecosystem, grouping hardware build assets, model assets, runtime, simulation-based identification, and training environments for a reproducible 3D-printed bipedal platform.
- Notes: Umbrella repository for component repos including `lerobot-humanoid-hardware`, `lerobot-humanoid-model`, `lerobot-humanoid-runtime`, and `lerobot-humanoid-identification`.

### LeRobot Legged Zoo
- Link: https://github.com/Virgileboat/lerobot-legged-zoo
- Category: simulator / RL / training environments
- Robot Type: humanoid / legged
- Simulator: MJLab
- Deploy: sim
- Summary: MJLab training examples and legged robot models for LeRobot/Pollen platforms, including LeRobot Humanoid; the repository description notes that it does not provide pretrained policies.
- Notes: Useful as the training-environment side of the LeRobot Humanoid release; currently early-stage and should be treated as experimental.

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

---

<details>
<summary><strong>Robot Operation and Loco-Manipulation Toolkits</strong></summary>

### BotBrain
- Link: https://github.com/botbotrobotics/BotBrain
- Category: toolkit / teleoperation / navigation
- Robot Type: humanoid / quadruped / biped / general
- Simulator: none
- Deploy: hardware
- Summary: Modular ROS2 robot brain with web UI support for teleoperation, autonomous navigation, mapping, monitoring, and 3D-printable hardware.
- Notes: Targets Jetson / RealSense deployments and Unitree Go2/G1-style platforms.

### EgoHumanoid
- Link: https://github.com/OpenDriveLab/EgoHumanoid
- Category: imitation learning / VLA / loco-manipulation
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: Framework for training humanoid whole-body loco-manipulation from egocentric human demonstrations plus limited robot data.
- Notes: Uses view alignment and action alignment before deploying VLA policies on Unitree G1 hardware.

### GRAIL
- Link: https://github.com/NVlabs/GRAIL
- Category: dataset / synthetic data / retargeting / loco-manipulation toolkit
- Robot Type: humanoid
- Simulator: Isaac / MuJoCo-adjacent pipeline components; Blender and generated 3D assets are used in the pipeline
- Deploy: data / sim / hardware
- Summary: Official NVIDIA repository for GRAIL, a digital humanoid loco-manipulation data-generation pipeline that synthesizes metric 4D human-object interaction trajectories from 3D assets and video priors, retargets them to Unitree G1, and supports task-general tracking for pickup, manipulation, sitting, and terrain traversal.
- Notes: README includes Docker setup, Blender/checkpoint dependencies, pipeline entrypoints for terrain/asset generation, 2D HOI generation, 4D reconstruction, retargeting, tracking, export, visualization, and a web visualizer. License is NVIDIA non-commercial except for NVIDIA and affiliates.

### SIMPLE
- Link: https://github.com/physical-superintelligence-lab/SIMPLE
- Category: simulator / benchmark / VLA evaluation / loco-manipulation toolkit
- Robot Type: humanoid / general
- Simulator: Isaac Sim 4.5 / MuJoCo 3.3
- Deploy: sim
- Summary: Full-stack simulation environment from USC Physical Superintelligence Lab for humanoid loco-manipulation, with Unitree G1 support, 1000+ Objaverse assets, 50+ Habitat HSSD scenes, 50+ whole-body loco-manipulation tasks, and integrated evaluation for VLA policies such as Psi-0, π0.5, GR00T, and others.
- Notes: README reports preliminary benchmark results on six G1 whole-body tasks and provides installation through uv, robo-nix, and Docker; useful as a current benchmark/evaluation environment for humanoid VLA loco-manipulation.

### FORGE
- Link: https://github.com/bb0928/FORGE
- Category: RL / control / loco-manipulation
- Robot Type: humanoid
- Simulator: Isaac Gym / MuJoCo deployment planned
- Deploy: sim; real-robot deployment script not yet open-sourced
- Summary: Official implementation for FORGE, a force-aware multi-granularity control approach for efficient humanoid loco-manipulation, exposing residual-policy training and evaluation scripts around Isaac Gym, rsl_rl, and legged_gym.
- Notes: README states the base-policy training script, MuJoCo deployment script, and real-robot deployment script are not yet open-sourced, so the current repository should be treated as partial but relevant for force/load-aware humanoid manipulation control.

</details>

---

<details>
<summary><strong>Humanoid MPC and Watchlists</strong></summary>

### g1_locomotion
- Link: https://github.com/ioloizou/g1_locomotion
- Category: control / MPC
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: Unitree G1 locomotion stack combining Single Rigid Body Dynamics and Whole-Body Inverse Dynamics in a cascaded linear control pipeline.
- Notes: README reports MuJoCo straight-line walking support and states that physical-robot testing has not yet been performed.

### awesome-unitree-humanoid-papers
- Link: https://github.com/eai2-repos/awesome-unitree-humanoid-papers
- Category: toolkit
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Curated list of Unitree humanoid papers and projects covering G1, H1, and H1-2 work from 2025-2026.
- Notes: Best treated as a source-discovery watchlist rather than a research implementation repository.

</details>

---

<details>
<summary><strong>July 2026 Daily Additions</strong></summary>

### BotRunner64/Teleopit
- Link: https://github.com/BotRunner64/Teleopit
- Category: retargeting / teleoperation / dataset / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: Lightweight whole-body teleoperation framework for Unitree G1, supporting BVH and Pico 4 VR retargeting, sim2sim, sim2real, training data recording, and ONNX policy playback.
- Notes: Recent README updates mention Pico realtime control, LinkerHand sim2real control, manual HDF5 recording, and consolidated sim/sim2real buffering.

### NJU-RLC/quadrupedal-agility
- Link: https://github.com/NJU-RLC/quadrupedal-agility
- Category: RL / deployment / retargeting / dataset
- Robot Type: quadruped
- Simulator: Isaac Gym
- Deploy: both
- Summary: Official implementation of "Learning Diverse Natural Behaviors for Enhancing the Agility of Quadrupedal Robots," with BBC/TSC/EASI training pipelines and Go2 deployment assets.
- Notes: Repository cites arXiv:2505.09979 and includes planned/released motion-capture, training, deployment, and retargeting components.

### ansh1113/humanoid-motion-planning
- Link: https://github.com/ansh1113/humanoid-motion-planning
- Category: motion planning / control / MPC / RL / simulation
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: A Unitree G1 MuJoCo motion-planning demo stack combining ZMP preview control, A* footstep planning, MPC balance, Jacobian IK manipulation, push recovery, and a pre-trained RL walking policy.
- Notes: README reports a 2.01 m walking demo at about 0.4 m/s, 4/4 push recovery directions, and 49% MPC energy savings versus PD; no hardware deployment claim, so treat as a simulation / educational watchlist repo.

### matteogoddi/labrob_mujoco_environment
- Link: https://github.com/matteogoddi/labrob_mujoco_environment
- Category: MPC / WBC / state estimation / simulator
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim / hardware-oriented setup notes
- Summary: A Unitree G1 locomotion control environment built around an offline footstep planner, EKF state estimation, IS-MPC for CoM trajectory generation, and whole-body control for reference tracking and constraints.
- Notes: README frames the goal as closed-loop experiments on Unitree G1 and includes Unitree SDK / network setup notes; the fetched GitHub page does not establish a polished hardware result, so keep it as a technical watchlist candidate.

### iit-DLSLab/mpx
- Link: https://github.com/iit-DLSLab/mpx
- Category: MPC / trajectory optimization / JAX / MJX
- Robot Type: humanoid / quadruped / general legged
- Simulator: MJX / MuJoCo
- Deploy: sim / research infrastructure
- Summary: MPX implements legged-robot MPC and trajectory optimization in JAX, with GPU-parallel scans, differentiable solvers, batched learning-pipeline compatibility, and MJX examples for Talos, H1, Aliengo, and Go2.
- Notes: Useful as solver infrastructure rather than a robot-specific release; README highlights quadruped trot, humanoid jump, and quadruped barrel-roll examples.

### lbnmahs/quadrrl
- Link: https://github.com/lbnmahs/quadrrl
- Category: RL / benchmark / simulator / toolkit
- Robot Type: quadruped / wheeled-quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Quadrrl is a training and benchmarking library for legged and wheeled-legged quadruped locomotion, with flat and rough terrain RL tasks across ANYmal C/D, Spot, Unitree Go2/B2, Go2W/B2W, Deeprobotics, and Zsibot models.
- Notes: README lists RSL-RL, RL Games, SKRL, and HARL support; no hardware deployment claim was verified, so treat it as simulation / benchmarking infrastructure.

### BrandoUlissi/isaaclab-go2-locomotion
- Link: https://github.com/BrandoUlissi/isaaclab-go2-locomotion
- Category: RL / control / training baseline
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: Unitree Go2 reinforcement-learning locomotion baseline in NVIDIA Isaac Lab, with PPO training, deterministic replay scripts, TensorBoard plotting, and documented push-recovery extension.
- Notes: Latest verified release `v0.2.0-pushrecovery` was published on 2026-06-03 and adds mixed impulsive/sustained disturbance curricula; the release reports 87.5% recovery under 120 N peak impulse loads in simulation.

### CMUYUY/legged-gym-in-isaac-lab
- Link: https://github.com/CMUYUY/legged-gym-in-isaac-lab
- Category: RL / simulator migration / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: Migrates the classic `legged_gym` ANYmal-C rough-terrain reinforcement-learning setup from Isaac Gym style APIs to NVIDIA Isaac Lab, including DirectRLEnv, USD assets, observations/actions/rewards, and RSL-RL training glue.
- Notes: Not a fresh 2026-07 update, but useful as a reference for teams porting older Isaac Gym legged-locomotion code to Isaac Lab.

### IsaacLab-Tutorial
- Link: https://github.com/Lab-of-AI-and-Robotics/IsaacLab-Tutorial/
- Category: RL / simulator / tutorial / toolkit
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab
- Deploy: sim / sim-to-real tutorial material
- Summary: Ten-chapter Isaac Lab tutorial for developing reinforcement-learning environments for legged robots, starting from Unitree Go2 quadruped baselines and extending toward Unitree H1 humanoid locomotion.
- Notes: Created by Jihoon Moon from the Lab of AI and Robotics at Sungkyunkwan University; chapters cover project scaffolding, assets, kinematics, custom actions, reward shaping, curriculum, ActuatorNet sim-to-real bridging, and humanoid frontiers.

### Axellwppr/motion_tracking
- Link: https://github.com/Axellwppr/motion_tracking
- Category: RL / retargeting / dataset / deployment
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: both
- Summary: Official implementation for HEFT, with training, evaluation, export, and deployment-facing assets for humanoid whole-body motion tracking; branches cover HEFT training, G1 compliance work, and sim2real runtime/checkpoints.
- Notes: README mentions PMG support, WPC support, public training datasets or samples, ONNX/PT export, and sim2real branch assets. Full HEFT datasets and some WPC payload labels appear planned for later release.

### johnzhang3/mujoco_mpc_deploy
- Link: https://github.com/johnzhang3/mujoco_mpc_deploy
- Category: MPC / control / deployment
- Robot Type: quadruped / humanoid-adjacent
- Simulator: MuJoCo / MuJoCo MPC
- Deploy: hardware
- Summary: Hardware interface repository for deploying MuJoCo MPC on Unitree robots, paired with the ICRA 2026 paper "Whole-Body Model-Predictive Control of Legged Robots with MuJoCo" and the official MuJoCo MPC / Menagerie stacks.
- Notes: README says the repo is still work in progress and points users to separate Go1/Go2 branches of MuJoCo MPC; useful as a practical bridge from model-based whole-body MPC to Unitree hardware.

### mjlab-homierl
- Link: https://github.com/Nagi-ovo/mjlab-homierl
- Category: RL / locomotion / deployment / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: both
- Summary: External mjlab task package reproducing the lower-body locomotion RL portion of HOMIE on Unitree G1 and H1, including custom tasks/assets, HIM-PPO training, ONNX export metadata, pretrained checkpoints, sim playback, and a DDS-based real-robot deployment script for G1.
- Notes: The repository is explicit about deviations from OpenHomie, domain-randomization choices, deployment-grade PD gains, G1/H1 variants, hand/payload attachments, and HOMIE+ torso-pitch extensions; treat as a practical implementation signal, not an official HOMIE release unless confirmed.

### OmniContact_sim2sim
- Link: https://github.com/Ingrid789/OmniContact_sim2sim
- Category: control / loco-manipulation / policy deployment / simulator
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim / sim2real-style execution path
- Summary: Official implementation for OmniContact, a contact-flow framework for chaining humanoid loco-manipulation meta-skills such as carry, push, slide, relocate, kick, and multi-skill sequences; the repository provides scripted CFgen/NPZ motion tracking and joystick hot-switch execution paths for Unitree G1-style MuJoCo scenes.
- Notes: Paper: https://arxiv.org/abs/2606.26201. The README links Noitom Robotics, HKUST, Wuhan University, and HKU affiliations and an OmniContact dataset on Hugging Face.

### convex-mpc-biped
- Link: https://github.com/ispaik06/convex-mpc-biped
- Category: MPC / control / simulator
- Robot Type: humanoid / biped
- Simulator: MuJoCo
- Deploy: sim
- Summary: C++17 MuJoCo implementation of convex MPC over a single-rigid-body model for humanoid/biped locomotion, using contact-wrench optimization, Raibert-style swing-foot planning, and OSQP/Eigen-based infrastructure.
- Notes: Recent, small repository; track as an educational or prototype-grade convex-MPC implementation unless hardware validation or broader robot support appears.

### fault-locomotion-isaaclab
- Link: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- Category: RL / locomotion / simulator / deployment
- Robot Type: quadruped
- Simulator: Isaac Lab / MuJoCo
- Deploy: both
- Summary: Isaac Lab DirectEnv for quadrupedal locomotion under motor failures, supporting Aliengo and Go2 flat/rough blind and rough-vision environments, sim-to-sim in MuJoCo, and ROS2 sim-to-real deployment paths.
- Notes: README links concurrent state estimation, rapid motor adaptation, and Mixture-of-Experts RL for fault-tolerant locomotion; practical follow-up source for robust quadruped locomotion under degraded actuation.

### DribbleMaster
- Link: https://github.com/Zhuoheng0910/DribbleMaster
- Category: RL / locomotion / sim-to-sim
- Robot Type: humanoid
- Simulator: Isaac Gym / MuJoCo
- Deploy: sim
- Summary: Newly published training and evaluation code for the ICRA 2026 paper “Dribble Master,” providing an Isaac Gym humanoid dribbling task, PPO training, policy playback, and MuJoCo sim-to-sim validation.
- Notes: The repository was created on 2026-07-14 and is MIT-licensed. It corresponds to the earlier arXiv paper 2505.12679 rather than a new paper from this week.

### UFO
- Link: https://github.com/Roboparty/UFO
- Category: RL / motion learning / deployment toolkit
- Robot Type: humanoid
- Simulator: MJLab / MuJoCo
- Deploy: both
- Summary: An unsupervised reinforcement-learning framework for humanoid control with FB and TeCH training, robot-aware motion-data import, tracking/goal/reward inference, and ONNX export; Unitree G1 is the best-tested path and real-robot deployment and teleoperation live on a separate deploy branch.
- Notes: The repository was created on 2026-07-13 and had 43 GitHub stars when checked. New robot bring-up is explicitly experimental, requires already-retargeted robot motion data, and does not provide automatic motion retargeting or cross-morphology checkpoint reuse.

### safe-rl-qp-mc-rtc-superbuild
- Link: https://github.com/safe-rl-qp/safe-rl-qp-mc-rtc-superbuild
- Category: control / RL / toolkit
- Robot Type: humanoid / general
- Simulator: MuJoCo / mc_rtc
- Deploy: both
- Summary: A CMake superbuild that installs the Acc-CBF-QP framework and dependencies and provides a ready-to-run Unitree H1 walking-policy example for MuJoCo, with a path toward hardware execution and custom RL-QP controllers.
- Notes: Created on 2026-06-28 and updated on 2026-07-17; documented for Ubuntu 24.04. It links the archived paper implementation and experiment logs at https://github.com/safe-rl-qp/mc-safe-rl-qp, plus a controller template and community examples. This is the recommended starting point for reproducing the open-source IROS 2026 system.

### semantic-WBC
- Link: https://github.com/Lab-RoCoCo-Sapienza/semantic-WBC
- Category: control / RL / toolkit
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: An official standalone deployment bundle for audio-driven Unitree G1 whole-body skills, with Python code, G1 configurations, ONNX policy execution, a split robot/PC TCP command pipeline, local audio fingerprinting, simulation scripts, and hardware safety guidance.
- Notes: The repository was substantially prepared for release on 2026-07-15 and is built on RoboJuDo/BeyondMimic components. Base assets can be pulled from upstream, but the README says demo-specific ONNX and audio extras still await a GitHub release or separate URL. No repository-level SPDX license is declared; users should inspect upstream and bundled third-party licenses before reuse.

### asimov-1
- Link: https://github.com/asimovinc/asimov-1
- Category: hardware / simulator / control platform
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: both
- Summary: Open-source files for building and simulating Asimov 1, a 1.2 m, 35 kg humanoid with 25 actuated DoFs, including mechanical CAD, electrical CAD, a MuJoCo model, wiring, schematics, PCB files, and onboard software.
- Notes: Hardware is licensed under CERN-OHL-S-2.0; the repository marks the locomotion policy and Asimov API as forthcoming, so this is a substantial open platform signal rather than a complete locomotion stack today.

### G1_RL_FootstepTracking
- Link: https://github.com/CYH-SWU/G1_RL_FootstepTracking
- Category: RL / locomotion / simulator
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: PPO-based omnidirectional footstep-tracking environment for the Unitree G1, using proprioception and commanded footstep positions/yaws to generate 12 leg-joint position increments for forward, backward, lateral, turning, curved, and standing behaviors.
- Notes: Includes curriculum terrain up to 5 cm steps, symmetry augmentation, tests, CI, and training/evaluation scripts; it is a new small simulation-only repository with no documented hardware deployment.

### fastwmr
- Link: https://github.com/kevinpark135/fastwmr
- Category: RL / control
- Robot Type: humanoid
- Simulator: Isaac Lab
- Deploy: sim
- Summary: An early independent implementation that combines FastSAC-style off-policy humanoid learning with WMR-style recurrent world-state estimation and reconstruction, including environment definitions, actor/critic/decoder modules, replay buffers, training scripts, and focused unit tests.
- Notes: Created 2026-07-16 and actively updated through 2026-07-20. The repository has zero stars and no declared license at verification time; it is a promising implementation-in-progress, not yet a validated reproduction or hardware deployment.

### g1_real_ws
- Link: https://github.com/JeanMayoko18/g1_real_ws
- Category: control / perception / toolkit
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: A ROS 2 workspace that adapts Nav2 to the Unitree G1 through 3D-LiDAR-to-2D scan processing, planar odometry adaptation and calibration, and command scaling and conditioning for the learned locomotion interface.
- Notes: Created and last pushed on 2026-07-16, with G1 descriptions, maps, launch files, and ROS packages present. It is very new and has zero stars; the README documents the architecture, but independent real-robot reproduction was not verified today.

### go2_rl_robotlab
- Link: https://github.com/wertyuilife2/go2_rl_robotlab
- Category: reinforcement learning / locomotion / benchmarking
- Robot Type: quadruped robot — Unitree Go2
- Simulator: Isaac Lab / MuJoCo
- Deploy: simulation, sim-to-sim, and documented real-robot evaluation
- Summary: An Apache-2.0 Isaac Lab/RobotLab implementation of MoE-CTS for Go2 locomotion, with MuJoCo sim-to-sim deployment, asynchronous RoboGauge policy evaluation, and real-stair-walking demonstrations.
- Notes: The repository was pushed on 2026-07-21 and had 44 stars at verification. It reports a RoboGauge score of 0.6984 versus 0.6713 for its earlier Isaac Gym implementation and links an RSS 2026 paper; these results and real-robot demos were not independently reproduced in this run.

### HOPE
- Link: https://github.com/hitchopen/HOPE
- Category: reinforcement learning / whole-body control / planning / challenge platform
- Robot Type: humanoid robot
- Simulator: Isaac Lab / MuJoCo
- Deploy: simulation and Agibot A3 reference deployment path
- Summary: An Apache-2.0 open platform for humanoid table tennis that integrates unified forehand/backhand whole-body policy training, ROS 2 ball planning, MuJoCo evaluation with ball physics, ONNX export, and an Agibot A3 deployment runner.
- Notes: The repository was updated on 2026-07-22 and had 14 stars at verification. Its A3 path is documented end to end, but generated assets, checkpoints, and exported models are not bundled; the included swing motions are explicitly placeholders that must be replaced before serious deployment. Unitree G1 appears only in design documents, not as a shipped code path.

### legged_mpc_amp
- Link: https://github.com/Lxliam/legged_mpc_amp
- Category: control / dataset tooling / reinforcement learning
- Robot Type: quadruped robots
- Simulator: Gazebo; exports AMP data in Isaac Lab format
- Deploy: simulation
- Summary: A ROS Noetic workspace built around NMPC and whole-body control that automates keyboard-driven gait rollout, AMP motion-data recording, foot-trajectory visualization, and conversion to Isaac Lab `.npz` datasets.
- Notes: The repository supports Go1, Go2, A1, Aliengo, and Lite3, and was pushed on 2026-07-22. It had 41 stars at verification and declares BSD-3-Clause terms for its modifications; it is based on `QiayuanLiao/legged_control`. There is no tagged release or verified hardware deployment.

### phase_guided_terrain_traversal
- Link: https://github.com/NtagkasAlex/phase_guided_terrain_traversal
- Category: RL / control / perception / terrain generation
- Robot Type: quadruped — Unitree Go2 / ANYmal
- Simulator: MuJoCo MJX
- Deploy: simulation and Unitree Go2 hardware
- Summary: The official PGTT implementation, covering procedural terrain generation, JAX/MJX training, multi-run evaluation, saved policies, a LiDAR elevation-mapping perception stack, and Unitree SDK hardware deployment.
- Notes: Shared robot-agnostic modules support Go2 and ANYmal configurations; the documented hardware path uses Unitree L1 LiDAR, Point-LIO, elevation mapping, and `unitree_sdk2py`. The repository had 66 stars at verification and no explicit license was visible in GitHub metadata.

### YAHMP
- Link: https://github.com/fabio-amadio/yahmp
- Category: RL / motion tracking / evaluation / toolkit
- Robot Type: humanoid — Unitree G1
- Simulator: MuJoCo / MJLab
- Deploy: simulation and documented hardware deployment
- Summary: An Apache-2.0 modular framework for training, evaluating, exporting, and deploying Unitree G1 general motion-tracking policies, with retargeted AMASS/OMOMO support and a supplied ONNX policy path.
- Notes: The repository includes nominal, future-reference, and teacher-student variants plus conversion, evaluation, ONNX export, and deployment utilities. It had 13 stars at verification; the paper reports zero-shot real-G1 deployment, but this run did not reproduce training or hardware results.

</details>
