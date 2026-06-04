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

### BARD PyTorch Dynamics
- Link: https://github.com/YueWang996/bard-pytorch-dynamics
- Category: dynamics / toolkit
- Robot Type: general / quadruped
- Simulator: 论文报告 Isaac Lab 集成
- Deploy: sim
- Summary: PyTorch 原生刚体动力学库，支持 URDF 机器人、CPU/GPU 批量计算、autograd、floating base、FK、Jacobian、RNEA、ABA 和 CRBA。
- Notes: README 强调可直接嵌入 ML/机器人学习流水线并与 Pinocchio benchmark；论文报告其用于 11 自由度带脊柱四足的 AMP 训练。

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

### rl_sar
- 链接: https://github.com/fan-ziqi/rl_sar
- 类别: RL / deployment / simulator / toolkit
- 机器人类型: quadruped / wheeled-legged / humanoid
- 仿真器: IsaacGym / IsaacSim / Gazebo / MuJoCo
- 部署: sim / hardware
- 摘要: 面向强化学习策略的仿真验证与实机部署框架，覆盖四足、轮足和人形机器人。
- 备注: 支持 ROS Noetic、ROS 2 Foxy/Humble、libtorch、onnxruntime、Linux 和部分 macOS MuJoCo 仿真；README 列出 Unitree A1/Go2/Go2W/B2/B2W/G1、傅利叶 GR1、智脑 L4W4、DeepRobotics Lite3、Agibot D1、DDTRobot Tita 等硬件支持。

### legged_rl_lab
- 链接: https://github.com/zhw0422/legged_rl_lab
- 类别: RL / simulator / toolkit
- 机器人类型: humanoid / quadruped / general
- 仿真器: Isaac Lab / Isaac Sim
- 部署: sim / sim2sim2real
- 摘要: 基于 Isaac Lab 的腿足 RL 训练栈，面向 Unitree Go1、Go2 和 G1，覆盖粗糙地形行走、G1 AMP、深度 parkour 和跨形态实验。
- 备注: 记录 RSL-RL 训练、多 GPU 训练、G1+Go2 cross-embodied 任务、形态编码器、retargeted 运动数据和 skrl AMP 替代实现。

### BipedRobot
- 链接: https://github.com/AsterisCrack/BipedRobot
- 类别: RL / simulator / hardware / imitation learning
- 机器人类型: biped / humanoid-adjacent
- 仿真器: Isaac Lab / MuJoCo
- 部署: sim / hardware
- 摘要: 自制双足运动项目，包含 12 自由度实物机器人、Isaac Lab 与 MuJoCo 环境、自写 RL 算法、动作模仿和 sim-to-real randomization。
- 备注: 更适合作为技术细节丰富的个人项目跟踪，而不是已广泛采用的实验室框架。

### SoftMimic
- 链接: https://github.com/Improbable-AI/softmimic
- 类别: RL / imitation learning / whole-body control / deployment
- 机器人类型: humanoid
- 仿真器: Isaac Lab / MuJoCo
- 部署: sim / hardware
- 摘要: SoftMimic 官方实现，面向 Unitree G1 柔顺全身动作模仿，包含 compliant-motion augmentation、Isaac Lab 训练/评估、预训练策略、MuJoCo rollout 和部署工具。
- 备注: 来自 MIT Improbable AI Lab；依赖 Isaac Lab、RSL-RL、Mink、MuJoCo 和 Unitree SDK2，并采用 MIT license。

### ASAP-G1-RL
- 链接: https://github.com/Lurrkkking/ASAP-G1-RL
- 类别: RL / imitation learning / simulator / sim-to-sim
- 机器人类型: humanoid
- 仿真器: Isaac Gym / Genesis / MuJoCo
- 部署: sim
- 摘要: 基于 ASAP 的 Unitree G1 实验仓库，覆盖动作跟踪、崎岖地形 locomotion、MuJoCo-to-IsaacGym residual-action 复现、闭环 fine-tuning，以及足球 kickup / juggling 任务重设计。
- 备注: 更适合作为个人实验仓库跟踪，而不是成熟通用框架；可作为 ASAP 风格 residual action learning 和 Unitree G1 任务设计参考。

### legged-locomotion-control
- 链接: https://github.com/BrilliantCarrot/legged-locomotion-control
- 类别: RL / simulator / navigation / toolkit
- 机器人类型: quadruped
- 仿真器: Isaac Lab / Isaac Sim
- 部署: sim / ROS 2 integration
- 摘要: 面向 Unitree Go2 的 locomotion-control 工作区，用于 Isaac Lab PPO 实验、步态/接触分析、地形与域随机化、扰动测试，以及 ROS 2 导航命令生成。
- 备注: 小型但透明的教学 / 实验记录式工作区；可参考 Go2 pretrained-policy probe、reward tracking、joint-limit analysis 和 ROS 2 命令集成。

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

### LeRobot Humanoid
- Link: https://github.com/Virgileboat/lerobot-humanoid
- Category: toolkit / hardware / simulator / identification / runtime
- Robot Type: humanoid
- Simulator: MuJoCo / MJLab
- Deploy: sim / hardware
- Summary: Hugging Face / LeRobot 生态的全栈开源低成本人形机器人项目，聚合硬件搭建资产、模型资产、运行时、基于仿真的参数辨识和训练环境，用于可复现的 3D 打印双足平台。
- Notes: umbrella repo 连接 `lerobot-humanoid-hardware`、`lerobot-humanoid-model`、`lerobot-humanoid-runtime`、`lerobot-humanoid-identification` 等组件仓库。


### LeRobot Legged Zoo
- Link: https://github.com/Virgileboat/lerobot-legged-zoo
- Category: simulator / RL / training environments
- Robot Type: humanoid / legged
- Simulator: MJLab
- Deploy: sim
- Summary: LeRobot/Pollen 腿足机器人模型与 MJLab 训练示例，包含 LeRobot Humanoid；仓库描述明确不提供 pretrained policies。
- Notes: 可作为 LeRobot Humanoid 发布中的训练环境侧入口；目前早期阶段，适合跟踪但不应视为成熟基准。
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

---

<details>
<summary><strong>机器人操作与移动操作工具</strong></summary>

### BotBrain
- Link: https://github.com/botbotrobotics/BotBrain
- Category: toolkit / teleoperation / navigation
- Robot Type: humanoid / quadruped / biped / general
- Simulator: none
- Deploy: hardware
- Summary: 模块化 ROS2 robot brain，提供 Web UI、teleoperation、autonomous navigation、mapping、monitoring 与 3D-printable hardware。
- Notes: 面向 Jetson / RealSense 和 Unitree Go2/G1 类平台部署。

### EgoHumanoid
- Link: https://github.com/OpenDriveLab/EgoHumanoid
- Category: imitation learning / VLA / loco-manipulation
- Robot Type: humanoid
- Simulator: none
- Deploy: hardware
- Summary: 用 egocentric human demonstrations 加少量 robot data 训练 humanoid whole-body loco-manipulation 的框架。
- Notes: 使用 view alignment 和 action alignment 后，将 VLA policy 部署到 Unitree G1 硬件。

### SIMPLE
- Link: https://github.com/physical-superintelligence-lab/SIMPLE
- Category: simulator / benchmark / loco-manipulation
- Robot Type: humanoid
- Simulator: IsaacSim / MuJoCo
- Deploy: sim
- Summary: 面向 humanoid whole-body loco-manipulation 的 simulation-based policy learning and evaluation 环境。
- Notes: 包含 Unitree G1 支持、大规模 Objaverse/HSSD assets，以及 50+ humanoid whole-body loco-manipulation tasks。

### GRAIL
- Link: https://github.com/NVlabs/GRAIL
- Category: dataset / synthetic data / retargeting / loco-manipulation toolkit
- Robot Type: humanoid
- Simulator: Isaac / MuJoCo-adjacent pipeline components; Blender and generated 3D assets are used in the pipeline
- Deploy: data / sim / hardware
- Summary: GRAIL 的 NVIDIA 官方仓库；它是数字化人形移动操作数据生成流水线，可从 3D 资产和视频先验合成 metric 4D human-object interaction 轨迹，重定向到 Unitree G1，并支持 pickup、manipulation、sitting、terrain traversal 等任务的 task-general tracking。
- Notes: README 包含 Docker 安装、Blender/checkpoint 依赖，以及 terrain/asset generation、2D HOI generation、4D reconstruction、retargeting、tracking、export、visualization 和 web visualizer 等流水线入口。许可证为 NVIDIA non-commercial，NVIDIA 及其关联方例外。

### SIMPLE
- Link: https://github.com/physical-superintelligence-lab/SIMPLE
- Category: simulator / benchmark / VLA evaluation / loco-manipulation toolkit
- Robot Type: humanoid / general
- Simulator: Isaac Sim 4.5 / MuJoCo 3.3
- Deploy: sim
- Summary: USC Physical Superintelligence Lab 的全栈人形移动操作仿真环境；支持 Unitree G1、1000+ Objaverse 资产、50+ Habitat HSSD 场景、50+ 全身移动操作任务，并集成 Psi-0、π0.5、GR00T 等 VLA 策略评测。
- Notes: README 报告了 6 个 G1 全身任务上的初步 benchmark 结果，并提供 uv、robo-nix 和 Docker 安装路径；适合作为当前人形 VLA 移动操作的 benchmark / evaluation 环境跟踪。

### FORGE
- Link: https://github.com/bb0928/FORGE
- Category: RL / control / loco-manipulation
- Robot Type: humanoid
- Simulator: Isaac Gym / MuJoCo deployment planned
- Deploy: sim; real-robot deployment script not yet open-sourced
- Summary: FORGE 的官方实现；FORGE 是一种用于高效人形移动操作的 force-aware multi-granularity control 方法，当前仓库开放了围绕 Isaac Gym、rsl_rl 和 legged_gym 的 residual policy 训练与评估脚本。
- Notes: README 明确说明 base-policy training script、MuJoCo deployment script 和 real-robot deployment script 尚未开源，所以当前仓库应视为部分开放，但对力/负载感知的人形操作控制仍有参考价值。

</details>

---

<details>
<summary><strong>人形 MPC 与 Watchlists</strong></summary>

### g1_locomotion
- Link: https://github.com/ioloizou/g1_locomotion
- Category: control / MPC
- Robot Type: humanoid
- Simulator: MuJoCo
- Deploy: sim
- Summary: Unitree G1 运动控制栈，把 Single Rigid Body Dynamics 与 Whole-Body Inverse Dynamics 组合成级联线性控制流程。
- Notes: README 显示支持 MuJoCo 直线行走，并说明尚未在真实机器人上测试。

### awesome-unitree-humanoid-papers
- Link: https://github.com/eai2-repos/awesome-unitree-humanoid-papers
- Category: toolkit
- Robot Type: humanoid
- Simulator: none
- Deploy: data
- Summary: Unitree 人形论文和项目整理列表，覆盖 2025-2026 年 G1、H1、H1-2 相关工作。
- Notes: 更适合作为来源发现 watchlist，而不是研究实现仓库。

</details>
