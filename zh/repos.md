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

### mujoco_ros2_control
- Link: https://github.com/ros-controls/mujoco_ros2_control
- Category: control / simulator / sensor simulation / ROS 2 integration
- Robot Type: general / quadruped / humanoid
- Simulator: MuJoCo
- Deploy: sim / ROS 2
- Summary: ROS Controls 官方维护的 MuJoCo 集成，将仿真机器人封装为 `ros2_control` 系统接口，并提供 MJCF/URDF 模型流程、控制器支持和可扩展的 ROS 2 仿真插件。
- Notes: 尤其适合带感知系统的腿足机器人仿真：相机插件可为 MJCF 相机自动发布 RGB 图像、深度图像和 `CameraInfo`，支持多路 RGB-D 相机及基于 EGL 的无显示器 GPU 渲染；内置的光线投射 LiDAR 扩展支持可配置的 2D/3D 扫描、水平/垂直分辨率与视场、量程限制和更新频率。项目还保留了旧版 rangefinder LiDAR 插件，但官方推荐使用功能和性能更好的 3D LiDAR 扩展。

### MuJoCo-LiDAR
- Link: https://github.com/discoverse-dev/MuJoCo-LiDAR
- Category: simulator / sensor simulation / perception toolkit
- Robot Type: general / quadruped / humanoid
- Simulator: MuJoCo
- Deploy: sim / ROS1 / ROS2
- Summary: 面向 MuJoCo 的高性能 LiDAR 仿真工具，支持 CPU、Taichi、JAX 和 NVIDIA Warp 后端，多种激光雷达扫描模式，Unitree Go2 / G1 示例，以及 ROS 集成。
- Notes: 对腿足机器人感知与导航仿真有用，因为它支持 GPU ray casting、批量场景、动态 mesh、MJX/JAX 工作流，以及 Velodyne、Livox、Ouster 等常见 LiDAR 模型。

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

### Sharpa-RL-Lab
- Link: https://github.com/sharpa-robotics/sharpa-rl-lab
- Category: RL / 灵巧操作 / sim-to-real / 部署
- Robot Type: 灵巧手
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim / hardware
- Summary: SharpaWave 官方强化学习示例，面向手内物体旋转，提供训练、可视化、策略蒸馏和实机部署的逐步流程。
- Notes: 文档覆盖已测试的 Isaac Lab 2.2/2.3 环境、抓取缓存生成、ProprioAdapt 蒸馏、主机触觉或板载触觉部署，以及可配置的自定义旋转任务。

### rl_sar
- 链接: https://github.com/fan-ziqi/rl_sar
- 类别: RL / deployment / simulator / toolkit
- 机器人类型: quadruped / wheeled-legged / humanoid
- 仿真器: IsaacGym / IsaacSim / Gazebo / MuJoCo
- 部署: sim / hardware
- 摘要: 面向强化学习策略的仿真验证与实机部署框架，覆盖四足、轮足和人形机器人。
- 备注: 支持 ROS Noetic、ROS 2 Foxy/Humble、libtorch、onnxruntime、Linux 和部分 macOS MuJoCo 仿真；README 列出 Unitree A1/Go2/Go2W/B2/B2W/G1、傅利叶 GR1、智脑 L4W4、DeepRobotics Lite3、Agibot D1、DDTRobot Tita 等硬件支持。

### LeggedSkillDeploy
- 链接: https://github.com/haozhang04/LeggedSkillDeploy
- 类别: RL / deployment / simulator / toolkit
- 机器人类型: quadruped / humanoid / wheeled-biped / wheeled-quadruped
- 仿真器: MuJoCo / Gazebo（ROS 2）
- 部署: sim / hardware
- 摘要: 基于状态机的 Python 多策略部署框架，可将强化学习与模仿学习运动策略部署到多种腿足机器人形态。
- 备注: 包含 Unitree Go1/Go2、Go2W、G1（29 DoF）、Duow 和 M20 的策略及配置，支持键盘、手柄和手机网页控制。README 表明目前仅在 Go1 Pro 上完成实机测试，并提醒实机部署需要充分安全防护及接口适配。

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


### UniLab
- Link: https://github.com/unilabsim/UniLab
- Category: RL / simulator / heterogeneous training runtime / toolkit
- Robot Type: quadruped / humanoid / wheeled-legged / dexterous hand / manipulator
- Simulator: MuJoCoUni / MotrixSim
- Deploy: sim / hardware
- Summary: UniLab 官方仓库；它是一个异构机器人 RL 训练框架，通过共享内存运行时异步执行 CPU 物理仿真与 GPU 策略学习，并用统一 CLI 支持 PPO、APPO、SAC、TD3、FlashSAC、HORA 和 HIM-PPO，可运行在 CUDA、Apple Silicon、ROCm 和 Intel XPU 上。
- Notes: 已发布 demo / task 覆盖 Go1/Go2 运动控制、Unitree G1 walk / dance / motion tracking / backflip / climb / box tracking、Go2W 轮足运动、Sharpa / Allegro 灵巧操作，以及 Go2+arm 移动操作；项目页：https://unilabsim.github.io/。
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

### BeamDojo
- 链接: https://why618188.github.io/beamdojo/
- 类别: RL / perceptive locomotion / sparse footholds / deployment
- 机器人类型: humanoid
- 仿真器: 仿真训练（公开材料未注明具体实现）
- 部署: sim / hardware
- 摘要: 面向 Unitree G1 稀疏落脚点敏捷运动的两阶段强化学习框架，结合多边形足底落脚奖励、双 critic，以及用于实机部署的 LiDAR elevation map。
- 备注: 当前链接为 RSS 2025 项目页与论文，并非公开代码仓库；报告了踏石、平衡木、零样本地形迁移及 80% sim-to-real 成功率。

### extreme-parkour
- 链接: https://github.com/chengxuxin/extreme-parkour
- 类别: RL / simulator / parkour / deployment
- 机器人类型: quadruped
- 仿真器: Isaac Gym
- 部署: sim / hardware
- 摘要: Extreme Parkour 的 ICRA 2024 官方实现，通过基础策略与视觉策略蒸馏流程，训练基于深度相机的端到端四足动态越障策略。
- 备注: 基于 legged_gym 与 RSL-RL；README 提供训练、回放、JIT 导出和浏览器可视化说明，并报告使用 RTX 3090 约需 15–20 小时完成训练。

### parkour
- 链接: https://github.com/ZiwenZhuang/parkour
- 类别: RL / simulator / parkour / deployment
- 机器人类型: quadruped
- 仿真器: Isaac Gym
- 部署: sim / hardware
- 摘要: Robot Parkour Learning 的官方代码，CoRL 2023 oral 项目，基于 legged_gym 与 RSL-RL 训练四足 parkour 策略，包含 A1 / Go1 / Go2 训练和部署材料。
- 备注: 项目页：https://robot-parkour.github.io/。README 提供 Go1 和 Go2 部署指南，并标注论文为 CoRL 2023 Oral、Best Systems Paper Award Finalist。

### Isaaclab_Parkour
- 链接: https://github.com/CAI23sbP/Isaaclab_Parkour
- 类别: RL / simulator / parkour / deployment
- 机器人类型: quadruped
- 仿真器: Isaac Lab / MuJoCo
- 部署: sim / sim2sim / hardware planned
- 摘要: 基于 Isaac Lab 的 Unitree Go2 parkour locomotion 项目，源自 Extreme Parkour，包含 teacher/student RSL-RL 训练、play、evaluation 和 demo 任务。
- 备注: README 提供 teacher/student policy 下载说明，提到 Isaac Lab 到 MuJoCo 的 sim2sim、未来通过 go2_parkour_deploy 做实机部署，并要求引用 Extreme Parkour 与 ORBIT。

### go2_parkour_deploy
- 链接: https://github.com/CAI23sbP/go2_parkour_deploy
- 类别: deployment / sim2sim / simulator / parkour
- 机器人类型: quadruped
- 仿真器: MuJoCo / Isaac Lab policy source
- 部署: sim / hardware
- 摘要: Isaaclab_Parkour 策略的 Unitree Go2 部署配套仓库，支持 Isaac Lab 到 MuJoCo 的仿真部署，以及 Go2 实机部署。
- 备注: 依赖 Unitree MuJoCo；README 提到参考 Go2Py、HOVER、Eurekaverse、Spot RL Example 和 gym-quadruped。

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

---

<details>
<summary><strong>2026 年 7 月日报新增仓库</strong></summary>

### BotRunner64/Teleopit
- 链接: https://github.com/BotRunner64/Teleopit
- 类别: 重定向 / 遥操作 / 数据集 / 工具库
- 机器人类型: 人形
- 仿真器: MuJoCo
- 部署: 仿真与硬件
- 摘要: 面向 Unitree G1 的轻量全身遥操作框架，支持 BVH 与 Pico 4 VR 重定向、sim2sim、sim2real、训练数据记录和 ONNX 策略回放。
- 备注: 近期 README 更新提到 Pico 实时控制、LinkerHand sim2real 控制、手动 HDF5 记录，以及 sim / sim2real reference buffering 的统一。

### NJU-RLC/quadrupedal-agility
- 链接: https://github.com/NJU-RLC/quadrupedal-agility
- 类别: 强化学习 / 部署 / 重定向 / 数据集
- 机器人类型: 四足
- 仿真器: Isaac Gym
- 部署: 仿真与硬件
- 摘要: “Learning Diverse Natural Behaviors for Enhancing the Agility of Quadrupedal Robots”的官方实现，包含 BBC/TSC/EASI 训练流水线与 Go2 部署资产。
- 备注: 仓库引用 arXiv:2505.09979，并包含动捕、训练、部署和运动重定向相关组件。

### ansh1113/humanoid-motion-planning
- 链接: https://github.com/ansh1113/humanoid-motion-planning
- 类别: 运动规划 / 控制 / MPC / RL / 仿真
- 机器人类型: 人形
- 仿真器: MuJoCo
- 部署: 仿真
- 摘要: 面向 Unitree G1 的 MuJoCo 运动规划 demo 栈，组合了 ZMP preview control、A* 落脚规划、MPC 平衡、Jacobian IK 操作、抗推恢复和预训练 RL 行走策略。
- 备注: README 报告 2.01 m 行走、约 0.4 m/s、4/4 方向抗推恢复、MPC 相对 PD 节能 49%；未看到硬件部署声明，建议作为仿真 / 教学型 watchlist 仓库。

### matteogoddi/labrob_mujoco_environment
- 链接: https://github.com/matteogoddi/labrob_mujoco_environment
- 类别: MPC / WBC / 状态估计 / 仿真器
- 机器人类型: 人形
- 仿真器: MuJoCo
- 部署: 仿真 / 硬件导向配置说明
- 摘要: Unitree G1 locomotion 控制环境，包含离线落脚规划、EKF 状态估计、用于 CoM 轨迹生成的 IS-MPC，以及用于参考跟踪和约束满足的 whole-body controller。
- 备注: README 把目标描述为在 Unitree G1 上做闭环实验，并包含 Unitree SDK / 网络配置说明；抓取到的 GitHub 页面尚不能证明成熟硬件结果，适合作为技术 watchlist 候选。

### iit-DLSLab/mpx
- 链接: https://github.com/iit-DLSLab/mpx
- 类别: MPC / trajectory optimization / JAX / MJX
- 机器人类型: 人形 / 四足 / 通用腿足
- 仿真器: MJX / MuJoCo
- 部署: 仿真 / 研究基础设施
- 摘要: MPX 用 JAX 实现腿足机器人 MPC 与轨迹优化，包含 GPU 并行扫描、可微求解器、可接入批量学习 pipeline 的接口，以及 Talos、H1、Aliengo 和 Go2 的 MJX 示例。
- 备注: 更适合作为求解器基础设施，而不是某个具体机器人的完整发布；README 展示了四足 trot、人形跳跃和四足 barrel roll 示例。

### lbnmahs/quadrrl
- 链接: https://github.com/lbnmahs/quadrrl
- 类别: RL / benchmark / simulator / toolkit
- 机器人类型: 四足 / 轮腿四足
- 仿真器: Isaac Lab / Isaac Sim
- 部署: 仿真
- 摘要: Quadrrl 是一个面向腿足和轮腿四足运动的训练与 benchmarking 库，提供平地和复杂地形 RL 任务，覆盖 ANYmal C/D、Spot、Unitree Go2/B2、Go2W/B2W、Deeprobotics 和 Zsibot 等模型。
- 备注: README 列出 RSL-RL、RL Games、SKRL 和 HARL 支持；今天未验证硬件部署声明，因此应视为仿真 / benchmark 基础设施。

### BrandoUlissi/isaaclab-go2-locomotion
- Link: https://github.com/BrandoUlissi/isaaclab-go2-locomotion
- Category: RL / control / training baseline
- Robot Type: quadruped
- Simulator: Isaac Lab / Isaac Sim
- Deploy: sim
- Summary: NVIDIA Isaac Lab 中的 Unitree Go2 强化学习行走基线，包含 PPO 训练、确定性回放脚本、TensorBoard 绘图和 push-recovery 扩展文档。
- Notes: 已验证的最新 release `v0.2.0-pushrecovery` 发布于 2026-06-03，加入混合脉冲/持续扰动课程；release 报告在仿真中对 120 N 峰值脉冲负载达到 87.5% 恢复率。

### CMUYUY/legged-gym-in-isaac-lab
- Link: https://github.com/CMUYUY/legged-gym-in-isaac-lab
- Category: RL / simulator migration / toolkit
- Robot Type: quadruped
- Simulator: Isaac Lab
- Deploy: sim
- Summary: 将经典 `legged_gym` 的 ANYmal-C 崎岖地形强化学习设置从 Isaac Gym 风格 API 迁移到 NVIDIA Isaac Lab，包括 DirectRLEnv、USD 资产、观测/动作/奖励和 RSL-RL 训练衔接。
- Notes: 不是 2026-07 的新更新，但对把旧 Isaac Gym 腿足行走代码迁移到 Isaac Lab 的团队有参考价值。

### IsaacLab-Tutorial
- Link: https://github.com/Lab-of-AI-and-Robotics/IsaacLab-Tutorial/
- Category: RL / simulator / tutorial / toolkit
- Robot Type: quadruped / humanoid
- Simulator: Isaac Lab
- Deploy: sim / sim-to-real tutorial material
- Summary: 十章 Isaac Lab 教程，用于开发腿足机器人强化学习环境；从 Unitree Go2 四足 baseline 起步，并扩展到 Unitree H1 人形 locomotion。
- Notes: 作者为 Sungkyunkwan University 的 Lab of AI and Robotics 成员 Jihoon Moon；章节覆盖项目脚手架、资产、运动学、自定义 action、reward shaping、curriculum、ActuatorNet sim-to-real bridging 和 humanoid frontiers。

### Axellwppr/motion_tracking
- Link: https://github.com/Axellwppr/motion_tracking
- Category: RL / retargeting / dataset / deployment
- Robot Type: humanoid
- Simulator: MuJoCo / mjlab
- Deploy: both
- Summary: HEFT 官方实现，包含人形机器人全身 motion tracking 的训练、评估、导出和部署相关资产；分支覆盖 HEFT 训练、G1 compliance 工作，以及 sim2real runtime/checkpoints。
- Notes: README 提到 PMG、WPC、公开训练数据或样例、ONNX/PT 导出和 sim2real 分支资产；完整 HEFT 数据集和部分 WPC payload labels 似乎仍计划后续发布。

### johnzhang3/mujoco_mpc_deploy
- Link: https://github.com/johnzhang3/mujoco_mpc_deploy
- Category: MPC / control / deployment
- Robot Type: quadruped / humanoid-adjacent
- Simulator: MuJoCo / MuJoCo MPC
- Deploy: hardware
- Summary: 面向 Unitree 机器人部署 MuJoCo MPC 的硬件接口仓库，对应 ICRA 2026 论文 “Whole-Body Model-Predictive Control of Legged Robots with MuJoCo”，并与官方 MuJoCo MPC / Menagerie 栈配合使用。
- Notes: README 明确说仓库仍在 work in progress，并指向 Go1/Go2 分支的 MuJoCo MPC；作为从模型式 whole-body MPC 到 Unitree 硬件的实践桥梁值得跟踪。

### mjlab-homierl
- 链接: https://github.com/Nagi-ovo/mjlab-homierl
- 类别: RL / locomotion / deployment / toolkit
- 机器人类型: humanoid
- 仿真器: MuJoCo / mjlab
- 部署: both
- 摘要: 一个外部 mjlab task package，用于复现 HOMIE 在 Unitree G1 和 H1 上的下肢 locomotion RL 部分；包含自定义任务/资产、HIM-PPO 训练、ONNX export metadata、预训练 checkpoint、仿真播放，以及 G1 上基于 DDS 的真机部署脚本。
- 备注: 仓库详细说明了与 OpenHomie 的差异、domain randomization 选择、deployment-grade PD gains、G1/H1 变体、手部/负载附件和 HOMIE+ torso-pitch 扩展；先作为实用实现信号跟踪，不直接视作官方 HOMIE 发布，除非后续确认。

### OmniContact_sim2sim
- 链接: https://github.com/Ingrid789/OmniContact_sim2sim
- 类别: control / loco-manipulation / policy deployment / simulator
- 机器人类型: humanoid
- 仿真器: MuJoCo
- 部署: sim / sim2real-style execution path
- 摘要: OmniContact 官方实现；OmniContact 是用于人形移动操作的 contact-flow 框架，支持 carry、push、slide、relocate、kick 以及多技能链式组合；仓库提供 CFgen/NPZ motion tracking 的脚本执行路径，以及面向 Unitree G1 风格 MuJoCo 场景的手柄热切换执行路径。
- 备注: 论文：https://arxiv.org/abs/2606.26201。README 关联 Noitom Robotics、HKUST、Wuhan University、HKU，并链接了 Hugging Face 上的 OmniContact 数据集。

### convex-mpc-biped
- 链接: https://github.com/ispaik06/convex-mpc-biped
- 类别: MPC / control / simulator
- 机器人类型: humanoid / biped
- 仿真器: MuJoCo
- 部署: sim
- 摘要: C++17 / MuJoCo 实现的 convex MPC biped/humanoid locomotion 原型，基于 single-rigid-body model，包含 contact-wrench optimization、Raibert-style swing-foot planning，以及 OSQP/Eigen 基础设施。
- 备注: 近期小仓库；在出现硬件验证或更广机器人支持前，先按教育/原型级 convex-MPC 实现跟踪。

### fault-locomotion-isaaclab
- 链接: https://github.com/iit-DLSLab/fault-locomotion-isaaclab
- 类别: RL / locomotion / simulator / deployment
- 机器人类型: quadruped
- 仿真器: Isaac Lab / MuJoCo
- 部署: both
- 摘要: 面向 motor failures 的 quadrupedal locomotion Isaac Lab DirectEnv，支持 Aliengo 和 Go2 的 flat/rough blind、rough-vision 环境，提供 MuJoCo sim-to-sim 和 ROS2 sim-to-real 部署路径。
- 备注: README 关联 concurrent state estimation、rapid motor adaptation 和 Mixture-of-Experts RL for Fault-Tolerant Legged Locomotion；是跟踪执行器退化/失效下四足鲁棒 locomotion 的实用来源。

### DribbleMaster
- 链接：https://github.com/Zhuoheng0910/DribbleMaster
- 类别：强化学习 / 运动控制 / 仿真到仿真
- 机器人类型：人形机器人
- 仿真器：Isaac Gym / MuJoCo
- 部署：仿真
- 摘要：新公开的 ICRA 2026 论文“Dribble Master”训练与评估代码，包含 Isaac Gym 人形带球任务、PPO 训练、策略回放和 MuJoCo 仿真到仿真验证。
- 备注：仓库创建于 2026-07-14，采用 MIT 许可证；它对应较早发布的 arXiv:2505.12679，并非本周的新论文。

### UFO
- 链接：https://github.com/Roboparty/UFO
- 类别：强化学习 / 动作学习 / 部署工具链
- 机器人类型：人形机器人
- 仿真器：MJLab / MuJoCo
- 部署：仿真与实机
- 摘要：一个人形机器人无监督强化学习框架，支持 FB 与 TeCH 训练、机器人感知的动作数据导入、跟踪/目标/奖励推理和 ONNX 导出；Unitree G1 是目前测试最充分的路径，实机部署与遥操作位于独立的 deploy 分支。
- 备注：仓库创建于 2026-07-13，检查时有 43 个 GitHub star。文档明确说明新机器人适配仍属实验功能，需要预先完成重定向的机器人动作数据，且不支持自动动作重定向或跨形态直接复用检查点。

### safe-rl-qp-mc-rtc-superbuild
- 链接: https://github.com/safe-rl-qp/safe-rl-qp-mc-rtc-superbuild
- 类别: 控制 / 强化学习 / 工具链
- 机器人类型: 人形机器人 / 通用
- 仿真器: MuJoCo / mc_rtc
- 部署: 仿真与真机
- 摘要: 该 CMake superbuild 可安装 Acc-CBF-QP 框架及其依赖，并提供可直接在 MuJoCo 中运行的 Unitree H1 行走策略示例，同时给出真机执行与自定义 RL-QP 控制器的扩展路径。
- 备注: 仓库创建于 2026-06-28，2026-07-17 有更新，文档面向 Ubuntu 24.04。它链接论文归档实现及实验日志 https://github.com/safe-rl-qp/mc-safe-rl-qp，并提供控制器模板和社区示例，是复现该 IROS 2026 开源系统的推荐入口。

### semantic-WBC
- 链接: https://github.com/Lab-RoCoCo-Sapienza/semantic-WBC
- 类别: 控制 / 强化学习 / 工具链
- 机器人类型: 人形机器人
- 仿真器: MuJoCo
- 部署: 仿真与真机
- 摘要: 面向 Unitree G1 音频驱动全身技能的官方独立部署包，包含 Python 代码、G1 配置、ONNX 策略执行、机器人端与 PC 端之间的 TCP 指令管线、本地音频指纹、仿真脚本及真机安全说明。
- 备注: 仓库在 2026-07-15 集中整理发布，构建于 RoboJuDo/BeyondMimic 组件之上。基础资产可从上游拉取，但 README 表明演示专用 ONNX 与音频扩展仍需等待 GitHub Release 或单独 URL。仓库没有声明整体 SPDX 许可证，复用前应逐项核查上游与内置第三方组件的许可。

### asimov-1
- 链接：https://github.com/asimovinc/asimov-1
- 类别：硬件 / 仿真器 / 控制平台
- 机器人类型：人形
- 仿真器：MuJoCo
- 部署：仿真与硬件
- 摘要：Asimov 1 的开源构建与仿真文件；该机器人高 1.2 m、重 35 kg、具有 25 个主动自由度，仓库包含机械 CAD、电气 CAD、MuJoCo 模型、线束、原理图、PCB 文件和机载软件。
- 备注：硬件采用 CERN-OHL-S-2.0 许可证；仓库仍将运动策略和 Asimov API 标为“即将推出”，因此目前更适合作为重要开放平台信号，而不是完整可用的运动控制栈。

### G1_RL_FootstepTracking
- 链接：https://github.com/CYH-SWU/G1_RL_FootstepTracking
- 类别：强化学习 / 运动控制 / 仿真器
- 机器人类型：人形
- 仿真器：MuJoCo
- 部署：仿真
- 摘要：面向 Unitree G1 的 PPO 全向足步跟踪环境，利用本体状态和指定足步位置/偏航角，输出 12 个腿部关节位置增量，覆盖前进、后退、侧移、转向、曲线行走和站立。
- 备注：包含最高 5 cm 台阶的课程学习、对称增强、测试、CI 及训练/评估脚本；这是一个新建的小型纯仿真仓库，暂未记录硬件部署。

### fastwmr
- 链接：https://github.com/kevinpark135/fastwmr
- 类别：强化学习 / 控制
- 机器人类型：人形机器人
- 仿真器：Isaac Lab
- 部署：仿真
- 摘要：一个早期独立实现，将 FastSAC 风格的离策略人形学习与 WMR 风格的循环世界状态估计和重建结合，已包含环境定义、actor/critic/decoder、回放缓冲区、训练脚本和针对性单元测试。
- 备注：仓库创建于 2026-07-16，并持续更新至 2026-07-20。核验时为 0 stars 且未声明许可证；它是值得关注的开发中实现，尚不能视为已验证复现或硬件部署。

### g1_real_ws
- 链接：https://github.com/JeanMayoko18/g1_real_ws
- 类别：控制 / 感知 / 工具链
- 机器人类型：人形机器人
- 仿真器：无
- 部署：硬件
- 摘要：一个面向 Unitree G1 的 ROS 2 工作区，通过三维激光雷达到二维扫描的处理、平面里程计适配与校准，以及针对学习型运动接口的速度缩放和指令调理，把 Nav2 适配到 G1。
- 备注：仓库创建并最后推送于 2026-07-16，已包含 G1 描述、地图、launch 文件和 ROS 包。项目非常新且为 0 stars；README 对架构有较完整说明，但今天未验证独立真实机器人复现。

### go2_rl_robotlab
- 链接：https://github.com/wertyuilife2/go2_rl_robotlab
- 类别：强化学习 / 运动控制 / 基准评估
- 机器人类型：四足机器人 — Unitree Go2
- 仿真器：Isaac Lab / MuJoCo
- 部署：仿真、sim-to-sim 与有文档说明的真实机器人评估
- 摘要：一个采用 Apache-2.0 许可证的 Go2 MoE-CTS Isaac Lab/RobotLab 实现，包含 MuJoCo sim-to-sim 部署、异步 RoboGauge 策略评估和真实楼梯行走演示。
- 备注：仓库于 2026-07-21 有推送，核验时为 44 stars。其报告 RoboGauge 得分 0.6984，高于早期 Isaac Gym 实现的 0.6713，并链接 RSS 2026 论文；本次运行未独立复现实验结果或真实机器人演示。

### HOPE
- 链接：https://github.com/hitchopen/HOPE
- 类别：强化学习 / 全身控制 / 规划 / 挑战平台
- 机器人类型：人形机器人
- 仿真器：Isaac Lab / MuJoCo
- 部署：仿真与 Agibot A3 参考部署路径
- 摘要：一个采用 Apache-2.0 许可证的人形乒乓球开放平台，集成正反手统一全身策略训练、ROS 2 球路规划、带球物理的 MuJoCo 评估、ONNX 导出和 Agibot A3 部署运行器。
- 备注：仓库于 2026-07-22 更新，核验时为 14 stars。A3 路径文档较完整，但生成资产、检查点和导出模型不随仓库提供；附带挥拍动作被明确标记为占位数据，严肃部署前必须替换。Unitree G1 仅出现在设计文档中，没有已交付代码路径。

### legged_mpc_amp
- 链接：https://github.com/Lxliam/legged_mpc_amp
- 类别：控制 / 数据集工具 / 强化学习
- 机器人类型：四足机器人
- 仿真器：Gazebo；可导出 Isaac Lab 格式的 AMP 数据
- 部署：仿真
- 摘要：一个基于 ROS Noetic、NMPC 和全身控制的工作区，可自动完成键盘驱动步态 rollout、AMP 运动数据录制、足端轨迹可视化及 Isaac Lab `.npz` 数据转换。
- 备注：仓库支持 Go1、Go2、A1、Aliengo 和 Lite3，于 2026-07-22 有推送，核验时为 41 stars；修改部分声明 BSD-3-Clause，并基于 `QiayuanLiao/legged_control`。目前没有版本化 release，也未核验硬件部署。

### phase_guided_terrain_traversal
- 链接：https://github.com/NtagkasAlex/phase_guided_terrain_traversal
- 类别：强化学习 / 控制 / 感知 / 地形生成
- 机器人类型：四足机器人 — Unitree Go2 / ANYmal
- 仿真器：MuJoCo MJX
- 部署：仿真与 Unitree Go2 实机
- 摘要：PGTT 官方实现，覆盖程序化地形生成、JAX/MJX 训练、多轮评估、策略检查点、LiDAR 高程映射感知栈和基于 Unitree SDK 的硬件部署。
- 备注：共享的机器人无关模块支持 Go2 与 ANYmal 配置；实机文档路径使用 Unitree L1 LiDAR、Point-LIO、高程映射和 `unitree_sdk2py`。核验时为 66 stars，GitHub 元数据中未显示明确许可证。

### YAHMP
- 链接：https://github.com/fabio-amadio/yahmp
- 类别：强化学习 / 动作跟踪 / 评估 / 工具包
- 机器人类型：人形机器人 — Unitree G1
- 仿真器：MuJoCo / MJLab
- 部署：仿真与有文档的实机部署
- 摘要：一个采用 Apache-2.0 许可证的模块化框架，用于训练、评估、导出和部署 Unitree G1 通用动作跟踪策略，支持重定向 AMASS/OMOMO 数据及配套 ONNX 策略运行路径。
- 备注：仓库包含基础版、未来参考编码版和教师—学生版，以及数据转换、评估、ONNX 导出和部署工具；核验时为 13 stars。论文报告零样本真实 G1 部署，但本次未复现训练或实机结果。

### Humanoid-Terrain-Bench
- 链接：https://github.com/shiki-ta/Humanoid-Terrain-Bench
- 类别：强化学习 / 基准评测 / 地形生成 / 数据集工具
- 机器人类型：人形机器人 — Unitree G1 / H1-2、Fourier GR1-T2 / GRX-N1
- 仿真器：Isaac Gym / Legged Gym
- 部署：仿真
- 摘要：面向人形机器人运动的地形基准与训练包，提供 9 类挑战地形、可组合地形布局、策略训练与定量评估，以及可将在线 rollout 保存为数据集的采集模块。
- 备注：该仓库用于 ICCV 2025 Multi-Terrain Humanoid Locomotion Challenge，并关联论文“One Policy but Many Worlds”（arXiv:2505.18780）。核验时为 80 stars；GitHub 未显示标准 SPDX 许可证，且文档注明竞赛专用模型导出和评估路径不能直接使用。

### robot_lab
- 链接：https://github.com/fan-ziqi/robot_lab
- 类别：强化学习 / 运动控制 / 训练框架
- 机器人类型：四足 / 轮足 / 人形机器人
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真；真机部署通过 rl_sar
- 摘要：一个面向 Isaac Lab 的多机器人强化学习扩展库，为大量四足、轮足和人形机器人提供速度控制及实验性技能训练环境。
- 备注：采用 Apache-2.0，支持 Docker 和分布式训练；Gazebo 与真实机器人运行由独立的 `rl_sar` 仓库负责。

### unitree_sim_isaaclab
- 链接：https://github.com/unitreerobotics/unitree_sim_isaaclab
- 类别：仿真器 / 遥操作 / 数据集工具
- 机器人类型：人形机器人 — Unitree G1 / H1-2，支持夹爪或灵巧手
- 仿真器：Isaac Lab / Isaac Sim 4.5、5.0 与 5.1
- 部署：仿真，并提供与真机兼容的 DDS 接口
- 摘要：宇树官方 Isaac Lab 人形机器人仿真包，支持面向遥操作的数据采集、回放、增强及模型验证，覆盖抓取、堆叠和移动全身操作任务。
- 备注：使用与宇树真机相同的 DDS topic，并可与 `xr_teleoperate` 集成；附带策略权重被明确限定为仅用于仿真测试。

### LeggedLab
- 链接：https://github.com/Hellod035/LeggedLab
- 类别：强化学习 / 运动控制 / 训练框架
- 机器人类型：腿足机器人 — 已在 Unitree G1 / H1 上验证
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真及通过 LeggedLabDeploy 的真机部署
- 摘要：一个精简的 Direct Isaac Lab 腿足机器人强化学习流程，强调环境逻辑透明、重构成本低，并与 Isaac Lab 核心仓库隔离。
- 备注：支持 RSL-RL 多 GPU 和多节点训练；README 报告已在 G1、H1 真机验证，并链接独立部署仓库。

### TienKung-Lab
- 链接：https://github.com/Open-X-Humanoid/TienKung-Lab
- 类别：强化学习 / 运动控制 / 动作模仿
- 机器人类型：人形机器人 — 天工
- 仿真器：Isaac Lab / Isaac Sim / MuJoCo
- 部署：仿真、sim-to-sim 与真机
- 摘要：面向全尺寸天工人形机器人的运动学习框架，结合 AMP 风格模仿奖励、周期步态奖励、运动重定向、射线传感器及走路和跑步策略。
- 备注：基于 Isaac Sim 4.5 与 Isaac Lab 2.1，包含导出策略和 MuJoCo 验证，并链接用于真实机器人执行的独立 `Deploy_Tienkung` 仓库。

### Isaac Lab
- 链接：https://github.com/isaac-sim/IsaacLab
- 类别：机器人学习框架 / 强化学习 / 模仿学习
- 机器人类型：通用 — 机械臂 / 四足 / 人形机器人
- 仿真器：NVIDIA Isaac Sim
- 部署：仿真及框架级 sim-to-real 工作流
- 摘要：NVIDIA 官方 GPU 加速开源机器人学习框架，统一强化学习、模仿学习、运动规划、传感器仿真和可扩展机器人实验，提供数十个环境及多种学习后端。
- 备注：主框架采用 BSD-3-Clause；它是基础设施框架，而不是面向特定机器人的统一硬件部署包。

### IsaacLab-Arena
- 链接：https://github.com/isaac-sim/IsaacLab-Arena
- 类别：基准评测 / 策略评估 / 环境组合
- 机器人类型：通用 / 多机器人形态
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真
- 摘要：一个可组合的 Isaac Lab 扩展，通过可复用组件组合场景、机器人形态与任务，用于大规模策略评估、模仿学习数据生成及顺序式长时程任务。
- 备注：采用 Apache-2.0；v0.2.x 被明确标记为早期版本，API 不稳定、功能尚不完整，官方不建议用于生产。

### rl_training
- 链接：https://github.com/DeepRoboticsLab/rl_training
- 类别：强化学习 / 运动控制 / 训练框架
- 机器人类型：四足 / 轮足机器人 — DeepRobotics Lite3 / M20
- 仿真器：Isaac Lab 2.3.2 / Isaac Sim 5.1 / RSL-RL
- 部署：仿真；支持 ONNX 导出，部署使用外部仓库
- 摘要：云深处面向 Lite3 和 M20 崎岖地形运动的 Isaac Lab 强化学习训练库，包含回放、分布式多 GPU/多节点训练和检查点直接导出 ONNX 的工具。
- 备注：采用 BSD-3-Clause；MuJoCo 和真实机器人部署由 DeepRoboticsLab 组织下的对应独立仓库负责。

### isaacLab.manipulation
- 链接：https://github.com/NathanWu7/isaacLab.manipulation
- 类别：强化学习 / 机器人操作 / 研究模板
- 机器人类型：机械臂 / 灵巧手 — Kinova / Franka / UR10 / Allegro Hand
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真
- 摘要：一个可独立安装的 Isaac Lab 机器人操作研究模板，提供可配置的机械臂 reaching、灵巧手方块重定向任务和 RSL-RL 训练流程。
- 备注：采用 MIT；源自较早的 Orbit 扩展结构，文档中包含若干需要手工处理的依赖与兼容性步骤。

### Isaac-RL-Two-wheel-Legged-Bot
- 链接：https://github.com/jaykorea/Isaac-RL-Two-wheel-Legged-Bot
- 类别：强化学习 / 轮足运动 / sim-to-real
- 机器人类型：双轮腿机器人 — Flamingo
- 仿真器：Isaac Lab / Isaac Sim / MuJoCo
- 部署：仿真、sim-to-sim 与真机
- 摘要：面向 Flamingo 双轮腿机器人的速度跟踪强化学习栈，包含 PPO、离策略 runner、观测堆叠、约束感知训练、ONNX 导出和零样本迁移演示。
- 备注：采用 MIT；MuJoCo ONNX 流程位于独立分支，README 表明该流程仍在迁移更新中。

### WheeledLab
- 链接：https://github.com/UWRobotLearning/WheeledLab
- 类别：强化学习 / 移动机器人 / sim-to-real 框架
- 机器人类型：轮式移动机器人 — HOUND / MuSHR
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真及通过 RealLab 的真机部署
- 摘要：面向开源轮式移动机器人的 Isaac Lab 环境、资产和强化学习流程，覆盖漂移、起伏地形穿越及视觉策略训练。
- 备注：采用 BSD-3-Clause；硬件集成由配套的 `UWRobotLearning/RealLab` 仓库提供，当前支持 HOUND 和 MuSHR，F1TENTH 被列为计划项。

### kinova_isaaclab_sim2real
- 链接：https://github.com/louislelay/kinova_isaaclab_sim2real
- 类别：强化学习 / 机器人操作 / sim-to-real
- 机器人类型：机械臂 — Kinova Gen3
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真与 ROS 2 真机
- 摘要：面向 Kinova Gen3 reaching 的端到端工具包，覆盖 Isaac Lab 强化学习训练、策略回放、预训练模型，以及无需在运行时安装 Isaac Lab 的 ROS 2 仿真硬件或真机部署。
- 备注：采用 MIT；支持 RSL-RL 和 RL-Games，并提供基于 `ros2_kortex` 的部署流程。

### Go2Arm_Lab
- 链接：https://github.com/zzzJie-Robot/Go2Arm_Lab
- 类别：强化学习 / 腿足操作 / 训练框架
- 机器人类型：四足移动操作机器人 — Unitree Go2 搭载 WidowX 250s 机械臂
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真；外部 sim-to-sim 与真机路径
- 摘要：面向 Go2Arm 移动操作平台的 RSL-RL 训练框架，包含 Isaac Lab 环境、策略训练与回放，并链接外部 Gazebo 和后继部署项目。
- 备注：仓库已进入维护模式，并建议新用户使用 `LeggedManip_Lab` 获取更新的 MuJoCo 与真机管线；README 显示 Apache-2.0，但核验时未找到根目录许可证文件。

### basic-locomotion-isaaclab
- 链接：https://github.com/iit-DLSLab/basic-locomotion-isaaclab
- 类别：强化学习 / 仿真器 / 运动控制 / 部署
- 机器人类型：四足机器人 — Aliengo / Go2 / B2 / HyQReal2
- 仿真器：Isaac Lab / Isaac Sim / MuJoCo
- 部署：仿真、sim-to-sim 与真机
- 摘要：一个 Isaac Lab 四足运动框架，包含 RSL-RL 训练、状态估计、适应、对称性和 AMP 支持，以及 MuJoCo sim-to-sim 与 ROS 2 sim-to-real 工具。
- 备注：采用 BSD-3-Clause；已测试 Isaac Lab 2.3.2、RSL-RL 3.3.0 和 MuJoCo 3.7.0。实机链路依赖 `muse` 与 `unitree-ros2-dls`，DAgger 和 depth-to-heightmap 功能被标记为已完成但未测试。

### amp-rsl-rl
- 链接：https://github.com/gbionics/amp-rsl-rl
- 类别：强化学习 / 模仿学习 / 工具包
- 机器人类型：人形机器人
- 仿真器：与仿真器解耦
- 部署：训练库
- 摘要：RSL-RL PPO 的扩展，加入对抗运动先验、动作捕捉数据加载、基于判别器的模仿奖励、对称增强和 AMP runner，用于人形机器人技能学习。
- 备注：采用 BSD-3-Clause 并通过 PyPI 分发；软件包被标记为 Beta，不包含机器人环境或仿真器，需要集成到兼容的 RSL-RL 任务栈并使用规定格式的 `.npy` 动作数据。

### isaac-go2-ros2
- 链接：https://github.com/Zhefan-Xu/isaac-go2-ros2
- 类别：仿真器 / ROS 2 / 导航
- 机器人类型：四足机器人 — Unitree Go2
- 仿真器：Isaac Sim / Isaac Lab
- 部署：带 ROS 2 接口的仿真
- 摘要：一个 Unitree Go2 仿真与 ROS 2 接口项目，在可配置的仓库和障碍环境中提供速度控制、相机、语义图像、LiDAR、里程计和位姿数据。
- 备注：默认分支目标环境为 Isaac Sim 4.5、Isaac Lab 2.1、ROS 2 Humble 和 Ubuntu 22.04，并提供独立的 4.2 与 Docker 分支；支持多 Go2 仿真，但未发现许可证或真机部署流程。

### MimicKit_IsaacLab
- 链接：https://github.com/NathanWu7/MimicKit_IsaacLab
- 类别：强化学习 / 模仿学习 / 动作跟踪 / 仿真器
- 机器人类型：人形机器人 — SMPL 人体 / 29 自由度 Unitree G1
- 仿真器：Isaac Lab / Isaac Sim
- 部署：仿真
- 摘要：MimicKit 的 Isaac Lab 适配版，为 SMPL 人体和 29 自由度 Unitree G1 提供 DeepMimic、AMP 与 ASE 动作模仿环境。
- 备注：采用 BSD-3-Clause；软件包版本 1.0.0 被标记为 Beta，并依赖外部动作数据。README 表明大量代码由 AI 辅助开发，且不提供 sim-to-sim 或真机部署。

</details>
