[English](../repos.md) | **中文**
# 仓库

> 腿足机器人长期 curated 仓库和工具列表。

---

<details>
<summary><strong>网站与查看器</strong></summary>

### motion_viewer
- Link: https://renkunzhao.github.io/motion_viewer/
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: 面向机器人模型和运动数据的 Web 可视化工具。

### robot_viewer
- Link: https://viewer.robotsfan.com/
- Category: viewer
- Robot Type: general
- Simulator: general
- Deploy: browser
- Summary: 支持 URDF、MJCF 和部分 USD 的 Web 3D 机器人模型/场景查看器。

### netron
- Link: https://netron.app/
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: 神经网络模型 Web 查看器，也适合查看机器人研究中的模型。

### BVHView
- Link: https://theorangeduck.com/media/uploads/BVHView/bvhview.html
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: 简单的 `.bvh` 动画文件查看器。

### sketchfab
- Link: https://sketchfab.com/feed#upload
- Category: viewer
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: Web FBX 播放器和模型查看器。

### rokoko
- Link: https://vision.rokoko.com/
- Category: motion generation
- Robot Type: general
- Simulator: none
- Deploy: browser
- Summary: 将视频转换为动画。

### mjswan
- Link: https://github.com/ttktjmt/mjswan
- Category: simulator
- Robot Type: general
- Simulator: MuJoCo
- Deploy: browser
- Summary: 带神经网络支持的 WebAssembly MuJoCo 仿真。

### mujoco_wasm
- Link: https://zalo.github.io/mujoco_wasm/
- Category: simulator
- Robot Type: general
- Simulator: MuJoCo
- Deploy: browser
- Summary: 在浏览器中仿真和渲染 MuJoCo 模型。

</details>

<details>
<summary><strong>控制、运动学、动力学与优化</strong></summary>

### mink
- Link: https://github.com/kevinzakka/mink
- Category: control
- Robot Type: general
- Simulator: MuJoCo
- Deploy: sim
- Summary: 基于 MuJoCo 的 Python inverse kinematics 工具。

### pyroki
- Link: https://github.com/chungmin99/pyroki
- Category: control
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: 模块化机器人运动学优化工具包。

### PlaCo
- Link: https://github.com/Rhoban/placo.git
- Category: control
- Robot Type: humanoid / general
- Simulator: none
- Deploy: sim
- Summary: 面向全身控制任务的 task-space inverse kinematics 与 dynamics 工具。

### cuRobo
- Link: https://github.com/NVlabs/curobo
- Category: control
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: CUDA 加速的机器人算法库，包括 FK、IK 和轨迹优化。

### pinocchio
- Link: https://github.com/stack-of-tasks/pinocchio
- Category: dynamics
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: 刚体动力学算法与解析导数库。

### se3_trajopt
- Link: https://github.com/upatras-lar/se3_trajopt
- Category: optimization
- Robot Type: general
- Simulator: none
- Deploy: sim
- Summary: SE(3) 切空间轨迹优化工具。

</details>

<details>
<summary><strong>仿真器与模型</strong></summary>

### sofa
- Link: https://github.com/sofa-framework/sofa
- Category: simulator
- Robot Type: general
- Simulator: SOFA
- Deploy: sim
- Summary: 实时多物理仿真框架，重点覆盖医学和可变形仿真。

### chrono
- Link: https://github.com/projectchrono/chrono
- Category: simulator
- Robot Type: general
- Simulator: Chrono
- Deploy: sim
- Summary: 高性能多物理和多体仿真库。

### mujoco_menagerie
- Link: https://github.com/google-deepmind/mujoco_menagerie.git
- Category: model collection
- Robot Type: humanoid / quadruped / general
- Simulator: MuJoCo
- Deploy: sim
- Summary: Google DeepMind curated 高质量 MuJoCo 模型集合。

</details>

<details>
<summary><strong>数据集与模型</strong></summary>

### KungFuAthleteBot
- Link: https://github.com/NPCLEI/KungFuAthleteBot.git
- Category: dataset
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: 使用 GVHMR 处理的运动员武术训练视频数据。

### BONES-SEED
- Link: https://huggingface.co/datasets/bones-studio/seed
- Category: dataset
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: 带 SOMA 和 Unitree G1 格式的大规模标注人体运动数据集。

### SOMA-X
- Link: https://github.com/NVlabs/SOMA-X.git
- Category: model
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: 支持的参数化人体模型的 canonical body topology 与 rig。

### grand_tour_dataset
- Link: https://github.com/leggedrobotics/grand_tour_dataset
- Category: dataset
- Robot Type: quadruped
- Simulator: none
- Deploy: data
- Summary: GrandTour 腿足机器人数据集官方 starter 仓库，包含 Hugging Face examples、ROS1 examples 和 Python utilities。
- Notes: ETH RSL GrandTour 数据集发布的配套工具。

</details>

<details>
<summary><strong>运动生成、重定向与编辑</strong></summary>

### GMR
- Link: https://github.com/YanjieZe/GMR
- Category: retargeting
- Robot Type: humanoid
- Simulator: none
- Deploy: sim
- Summary: 面向多种人形机器人的实时人体动作重定向。

### SOMA Retargeter
- Link: https://github.com/NVIDIA/soma-retargeter.git
- Category: retargeting
- Robot Type: humanoid
- Simulator: Newton / Warp
- Deploy: sim
- Summary: BVH 到人形机器人动作重定向库。

### Kimodo
- Link: https://research.nvidia.com/labs/sil/projects/kimodo/
- Category: motion generation
- Robot Type: human / humanoid
- Simulator: none
- Deploy: sim
- Summary: 支持文本和约束驱动运动生成的 kinematic motion diffusion model。

### GEM-X
- Link: https://github.com/NVlabs/GEM-X.git
- Category: pose estimation
- Robot Type: humanoid
- Simulator: none
- Deploy: sim
- Summary: 使用 SOMA body model 的 monocular whole-body 3D human pose estimation。

</details>

<details>
<summary><strong>强化学习</strong></summary>

### mjlab
- Link: https://github.com/mujocolab/mjlab.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: 基于 MuJoCo-Warp、兼容 Isaac Lab API 的 RL 与机器人研究库。

### mujoco_playground
- Link: https://github.com/google-deepmind/mujoco_playground.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: 面向机器人学习和 sim-to-real 迁移的 GPU 加速库。

### unitree_rl_mjlab
- Link: https://github.com/unitreerobotics/unitree_rl_mjlab.git
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim / hardware
- Summary: 使用 MuJoCo 的 Unitree 机器人真实部署 RL pipeline。

### unitree_rl_lab
- Link: https://github.com/unitreerobotics/unitree_rl_lab
- Category: RL
- Robot Type: humanoid / quadruped
- Simulator: IsaacSim
- Deploy: sim / hardware
- Summary: 使用 IsaacSim 的 Unitree 机器人真实部署 RL pipeline。

### Stage-Wise CMORL
- Link: https://github.com/rllab-snu/Stage-Wise-CMORL/tree/main
- Category: RL
- Robot Type: quadruped
- Simulator: IsaacGym
- Deploy: sim
- Summary: 面向四足杂技动作的 stage-wise curriculum RL。

### My_unitree_go2_gym
- Link: https://github.com/yusongmin1/My_unitree_go2_gym.git
- Category: RL
- Robot Type: quadruped
- Simulator: IsaacGym
- Deploy: sim / MuJoCo
- Summary: Unitree Go2 运动和杂技动作相关工作。

### TWIST2
- Link: https://github.com/amazon-far/TWIST2
- Category: RL / teleoperation
- Robot Type: humanoid
- Simulator: IsaacGym
- Deploy: MuJoCo / hardware
- Summary: 遥操作全身 imitation system。

### SONIC
- Link: https://nvlabs.github.io/GEAR-SONIC/
- Category: motion tracking
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: 大规模人形全身 motion tracking 工作。

### OmniXtreme
- Link: https://extreme-humanoid.github.io/
- Category: motion tracking
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: 面向高动态人形运动跟踪的统一策略框架。

</details>

<details>
<summary><strong>人形全身控制</strong></summary>

### GR00T-WholeBodyControl
- Link: https://github.com/NVlabs/GR00T-WholeBodyControl
- Category: control / toolkit
- Robot Type: humanoid
- Simulator: Isaac Lab / MuJoCo
- Deploy: sim / hardware
- Summary: NVIDIA GEAR 面向人形全身控制、遥操作、部署和 SONIC-based training workflows 的统一平台。
- Notes: Unitree G1-oriented whole-body control 与 teleop-to-deployment workflow 的强参考。

</details>

<details>
<summary><strong>MPC 与模型控制</strong></summary>

### OCS2
- Link: https://github.com/leggedrobotics/ocs2/tree/ros2
- Category: MPC
- Robot Type: quadruped
- Simulator: Raisim
- Deploy: sim
- Summary: 面向 switched systems 的 optimal control 框架，在腿足运动中应用广泛。

### MuJoCo MPC
- Link: https://github.com/google-deepmind/mujoco_mpc
- Category: MPC
- Robot Type: humanoid / quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: 基于 MuJoCo 的实时预测控制框架。

### DIAL-MPC
- Link: https://github.com/LeCAR-Lab/dial-mpc
- Category: MPC
- Robot Type: quadruped
- Simulator: none
- Deploy: sim
- Summary: 面向 full-order torque-level legged control 的 sampling-based MPC。

### Quadruped-PyMPC
- Link: https://github.com/iit-DLSLab/Quadruped-PyMPC/tree/main
- Category: MPC
- Robot Type: quadruped
- Simulator: MuJoCo
- Deploy: sim
- Summary: 使用 SRBM 和 gradient-based / sampling-based solver 的 Python 四足 MPC。

### Cheetah-Software
- Link: https://github.com/mit-biomimetics/Cheetah-Software
- Category: MPC / control
- Robot Type: quadruped
- Simulator: custom
- Deploy: sim / hardware
- Summary: MIT Cheetah 机器人软件栈。

</details>
