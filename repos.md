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

### SIMPLE
- Link: https://github.com/physical-superintelligence-lab/SIMPLE
- Category: simulator / benchmark / loco-manipulation
- Robot Type: humanoid
- Simulator: IsaacSim / MuJoCo
- Deploy: sim
- Summary: Simulation-based policy learning and evaluation environment for humanoid whole-body loco-manipulation.
- Notes: Includes Unitree G1 support, large Objaverse/HSSD assets, and 50+ humanoid whole-body loco-manipulation tasks.

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
