[English](../datasets.md) | **中文**
# 数据集

> 腿足机器人长期 curated 数据集列表：可直接用于机器人的动作数据、人体动捕、视频、优化生成的参考动作、实机采集数据，以及物理标定数据。

---

<details>
<summary><strong>机器人可用的动作数据</strong></summary>

### BONES-SEED
- 链接： https://huggingface.co/datasets/bones-studio/seed
- 类别： 人体动捕 / 机器人动作
- 对象： 人体 / 人形（Unitree G1）
- 内容： 522 名表演者的 142,220 条标注动作，约 288 h、120 fps；含特技组的空翻（如 flip_090、flip_180、flip_360、flip_from_wall）
- 格式： SOMA 比例版与统一版 BVH；Unitree G1 MuJoCo 兼容 CSV
- 获取方式： 需同意许可后下载
- 许可： bones-seed-license；学术用途及年收入 100 万美元以下的公司免费
- 摘要： 大规模人体动作库，其 G1 retarget 版本（由 NVIDIA 提供）是 SONIC 和 SuperMimic 的训练数据。
- 备注： SuperMimic 过滤后保留 129,514 条（264.56 h）用于平地跟踪。

### unilab-motions
- 链接： https://huggingface.co/datasets/unilabsim/unilab-motions
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： G1 跟踪片段，包括 flip_360_001__A304（后空翻）、flip_from_wall_104__A304（蹬墙翻）和 tictacflip，分 29 和 23 自由度版本
- 格式： NPZ（fps、joint_pos、joint_vel、body_pos_w、body_quat_w、body_lin_vel_w、body_ang_vel_w）
- 获取方式： 公开
- 许可： Hugging Face 上标为 Apache-2.0；片段疑似来自 BONES-SEED，其条款可能仍然适用
- 摘要： 可直接跟踪的 G1 空翻参考，供 UniLab 的翻转和蹬墙翻跟踪任务使用。

### any4hdmi-g1-amass-hard
- 链接： https://huggingface.co/datasets/elijahgalahad/any4hdmi-g1-amass-hard
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： 23 条已转到 G1 的 CMU 片段，包括侧空翻 90_08、前手翻 90_14/15、“monkey backflip” 90_19、侧手翻和鱼跃滚翻
- 格式： NPZ，50 Hz，36 维 qpos
- 获取方式： 公开
- 许可： 未声明；源自 AMASS
- 摘要： 目前找到的唯一保留了 CMU 空翻的公开 G1 retarget 数据集；常见的 AMASS→G1 数据集都把空翻过滤掉了。

### Unitree LAFAN1 Retargeting Dataset
- 链接： https://huggingface.co/datasets/lvhaidong/LAFAN1_Retargeting_Dataset
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： 40 条 retarget 后的 LAFAN1 片段（走、跑、跳、摔倒起身）；没有空翻
- 格式： CSV，30 fps
- 获取方式： 公开
- 许可： retarget 部分 BSD-3；底层 LAFAN1 为 CC BY-NC-ND
- 摘要： GMR retarget 评测协议和许多 G1 跟踪基线实际使用的片段集。

### AMASS Retargeted for G1
- 链接： https://huggingface.co/datasets/ember-lab-berkeley/AMASS_Retargeted_for_G1
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： 约 1.77 万条转到 G1 的 AMASS 片段；CMU 的杂技受试者大多被过滤掉
- 格式： NPZ
- 获取方式： 公开
- 许可： 标为 CC-BY-4.0；AMASS 条款仍然适用
- 摘要： 用于全身跟踪预训练的大型通用 G1 动作集。

### KungFuAthleteBot
- 链接： https://github.com/NPCLEI/KungFuAthleteBot
- 类别： 视频重建动作 / 机器人动作
- 对象： 人体 / 人形（Unitree G1）
- 内容： 来自国家级武术训练视频的 848 条片段，含 12 条后空翻和腾空跳跃
- 格式： GVHMR 的 SMPL-H 和 30 fps 的 G1 qpos（数据在 https://huggingface.co/datasets/LuluCao/KungfuAthleteBot ）
- 获取方式： 公开；不含原始视频
- 许可： 研究用途；论文接收后承诺改为 MIT
- 摘要： 视频到 G1 的流程（先 GVHMR 再 GMR），腾空段用抛物线修正根部轨迹。

### Humanoid-X
- 链接： https://huggingface.co/datasets/USC-PSI-Lab/Humanoid-X
- 类别： 视频重建动作 / 机器人动作
- 对象： 人体 / 人形（Unitree H1）
- 内容： 约 16.4 万条网络视频片段，提升为 SMPL 并转到 H1；含 Kinetics 的蹦床、后空翻和翻筋斗类
- 格式： SMPL 和机器人姿态文件；源视频只有 YouTube ID
- 获取方式： 公开
- 许可： 未声明
- 摘要： 规模很大但噪声多的视频重建动作集，适合作为杂技重建的基线和压力测试。

### ZEST G1 Motion Data
- 链接： https://doi.org/10.5281/zenodo.21135719
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： G1 的侧手翻、跳箱、爬箱、芭蕾和乒乓球参考轨迹，以及实机跟踪日志
- 格式： HDF5、CSV、pkl
- 获取方式： 公开
- 许可： CC-BY-4.0
- 摘要： ZEST（Science Robotics）的数据发布；ZEST 能把动捕、视频和动画中的运动技能零样本迁移到实机。

### OmniRetarget Dataset
- 链接： https://huggingface.co/datasets/omniretarget/OmniRetarget_Dataset
- 类别： 机器人动作
- 对象： 人形（Unitree G1）
- 内容： 约 0.5 h 的交互、地形和类跑酷 retarget 动作；没有空翻
- 格式： NPZ
- 获取方式： 公开
- 许可： MIT
- 摘要： 保留交互关系的 retarget 结果，面向移动操作和地形技能。

</details>

<details>
<summary><strong>人体动捕</strong></summary>

### CMU Graphics Lab Motion Capture Database
- 链接： http://mocap.cs.cmu.edu
- 类别： 人体动捕
- 对象： 人体
- 内容： 受试者 85、87、88、89、90 含约 40 条杂技动作：后空翻、侧空翻、手翻、带转体的后空翻（90_12/13）、侧手翻和滚翻
- 格式： C3D 和 ASF/AMC，60 或 120 Hz
- 获取方式： 公开
- 许可： 可用于任何用途；不得直接转售
- 摘要： 许可最宽松的真人空翻来源；所有空翻都从地面起跳。
- 备注： 几条最干净的后空翻（87_03–05、88_01/02/04、89_03）不在 AMASS 里，需要使用原始文件。

### AMASS
- 链接： https://amass.is.tue.mpg.de
- 类别： 人体动捕
- 对象： 人体
- 内容： 多个动捕数据集统一拟合到 SMPL-H / SMPL-X；杂技内容只有部分 CMU 空翻和侧手翻
- 格式： SMPL-H / SMPL-X NPZ
- 获取方式： 需注册
- 许可： 非商业研究；不得再分发
- 摘要： 大多数人形 retarget 数据集背后的标准大规模人体动作来源。

### FS-Jump3D
- 链接： https://github.com/ryota-skating/FS-Jump3D
- 类别： 人体动捕 / 视频
- 对象： 人体
- 内容： 4 名选手的 253 次花样滑冰跳跃，12 路同步视角，60 fps
- 格式： 无标记点 C3D、JSON、视频
- 获取方式： 公开（Google Drive）
- 许可： CC BY-NC-SA 4.0
- 摘要： 绕身体长轴快速旋转（转体）的参考，带跳跃阶段标注。

### EgoHTR
- 链接： https://huggingface.co/datasets/leggedrobotics/egohtr
- 类别： 人体动捕 / 视频
- 对象： 人体
- 内容： 55 段序列（1.37 h），含 4 段空翻和跑酷，附扫描场景和 Aria 第一视角视频
- 格式： 动捕服 IMU 得到的 SMPL-X 真值、视频
- 获取方式： 需人工审批
- 许可： CC-BY-4.0
- 摘要： 少数带真实空翻 3D 真值的公开数据集之一。

</details>

<details>
<summary><strong>视频与视频重建动作</strong></summary>

### Trampoline-AQA
- 链接： https://github.com/mlxger/Trampoline
- 类别： 视频
- 对象： 人体（蹦床）
- 内容： 2018–2024 年 206 个个人比赛套路（奥运会、世锦赛、亚运会），约 3.06 h，1080p 60 fps
- 格式： 视频；评分、腾空时间、水平位移、动作数量
- 获取方式： Google Drive 下载
- 许可： 代码 CC-BY-4.0；视频为电视转播素材
- 摘要： 规模最大的公开真实蹦床视频集；没有动作切分和姿态标注。

### AQA-7
- 链接： http://rtis.oit.unlv.edu/datasets.html
- 类别： 视频
- 对象： 人体（蹦床、跳水、跳马、大跳台）
- 内容： 83 个蹦床套路，另有跳台跳水、3 m 跳板双人跳水、跳马和大跳台滑雪 / 单板项目
- 格式： 带裁判评分的视频
- 获取方式： 直接下载
- 许可： 研究用途
- 摘要： 第二个公开的真实蹦床视频来源，侧面跟拍运动员。

### FineDiving
- 链接： https://github.com/xujinglin/FineDiving
- 类别： 视频
- 对象： 人体（跳水，含 3 m 跳板）
- 内容： 3,000 次跳水，52 种动作，帧级步骤切分（起跳、腾空、入水）
- 格式： 视频；动作编号、翻转圈数、转体圈数、姿态、评分
- 获取方式： 签署发布协议
- 许可： 研究用途；代码 MIT
- 摘要： 可用标签自动核对重建出的转角圈数和腾空时段。

### MTL-AQA
- 链接： https://github.com/ParitoshParmar/MTL-AQA
- 类别： 视频
- 对象： 人体（10 m 跳台、3 m 跳板）
- 内容： 来自 16 场比赛的 1,412 次跳水
- 格式： YouTube 列表，附评分、难度、姿态、翻转和转体标注
- 获取方式： 公开（基于 YouTube）
- 许可： 研究用途
- 摘要： 每次跳水都标了翻转和转体属性。

### Diving48
- 链接： http://www.svcl.ucsd.edu/projects/resound/dataset.html
- 类别： 视频
- 对象： 人体（跳水）
- 内容： 约 1.8 万段剪辑好的比赛跳水，48 类，由起跳、翻转、转体和姿态定义
- 格式： RGB 视频
- 获取方式： 直接下载
- 许可： 研究用途
- 摘要： 大规模翻转 / 转体视频集，只有类别标签。

### Motion-X++
- 链接： https://huggingface.co/datasets/YuhongZhang/Motion-Xplusplus
- 类别： 视频重建动作
- 对象： 人体
- 内容： 大规模视频重建的 SMPL-X 动作库；约 100 段杂技（如 HAA500 的蹦床和后空翻、功夫后空翻）
- 格式： SMPL-X，30 fps
- 获取方式： 需填申请表
- 许可： 非商业，并受源视频许可约束
- 摘要： 可补充视频重建的空翻作为基线；身体倒立时质量明显下降。

</details>

<details>
<summary><strong>优化生成的杂技动作</strong></summary>

### Miller Somersault Optimal Control Solutions
- 链接： https://data.mendeley.com/datasets/rz8t786st8
- 类别： 优化生成
- 对象： 人体（15 自由度生物力学模型）
- 内容： 双周直体后空翻加三周转体的最优控制解，每种建模方式 100 个解（只有空中段）
- 格式： biorbd 模型和解的 pickle
- 获取方式： 公开
- 许可： CC BY 4.0；代码在 https://github.com/Ipuch/OnDynamicsForSomersaults （MIT）
- 摘要： 在接近蹦床的高度上物理自洽的转体空翻腾空段。

### energetic_somersault
- 链接： https://github.com/Ipuch/energetic_somersault
- 类别： 优化生成
- 对象： 人体（15 自由度生物力学模型）
- 内容： Miller 空翻在 3、5、10、15、20、25 m 腾空高度下、用多种离散方法求得的解（只有空中段）
- 格式： 解的 pickle（状态、控制）
- 获取方式： 公开
- 许可： MIT
- 摘要： 按腾空高度参数化的空中段参考；3 m 和 5 m 与蹦床腾空时间相当。

### backflip_holonomic_tucking_constraint
- 链接： https://github.com/EveCharbie/backflip_holonomic_tucking_constraint
- 类别： 优化生成
- 对象： 人体（平面 7–8 自由度模型）
- 内容： 原地后空翻团身，含蹬地、腾空、团身和落地；三种接触变体，各 20 个多起点解
- 格式： pickle、biorbd 模型、视频
- 获取方式： 公开
- 许可： 通过 Zenodo 为 CC-BY-4.0（https://doi.org/10.5281/zenodo.14546204 ）
- 摘要： 少见的包含地面接触阶段的优化生成空翻。

### G1 Backflip Trajectory Optimization
- 链接： https://github.com/ShahhhVihaan/backflip
- 类别： 优化生成
- 对象： 人形（Unitree G1，23 自由度）
- 内容： 运动动力学轨迹优化得到的后空翻（蹬地、腾空、落地），用全身控制加 MPC 跟踪
- 格式： 轨迹 pickle；CasADi 和 Pinocchio 代码
- 获取方式： 公开
- 许可： 未声明（开发中）
- 摘要： 不依赖动捕、由模型生成的 G1 后空翻。

</details>

<details>
<summary><strong>机器人实机采集数据</strong></summary>

### GrandTour
- 链接： https://arxiv.org/abs/2602.18164
- 类别： 实机采集
- 对象： 四足（ANYmal-D）
- 内容： 大规模室内外多模态腿足机器人采集数据，带高精度真值
- 格式： 见配套仓库 https://github.com/leggedrobotics/grand_tour_dataset （Hugging Face 和 ROS1 示例）
- 获取方式： 公开
- 摘要： 用于感知、状态估计和导航的真实腿足数据。

</details>

<details>
<summary><strong>物理参数与标定</strong></summary>

### FIG Apparatus Norms: Trampoline (TRA1)
- 链接： https://www.gymnastics.sport/publicdir/rules/files/en_Apparatus%20Norms%20IV%20.pdf
- 类别： 物理参数
- 对象： 蹦床
- 内容： 60 kg、直径 40 cm 的球从 4.00 m 落到床中心：下陷须在 940–1010 mm，反弹须在 3310–3560 mm；另有弹簧阶跃测试规程
- 格式： PDF 标准
- 获取方式： 公开
- 摘要： 仿真比赛蹦床的直接标定目标。
- 备注： 按线性能量守恒估算，等效中心刚度约 5.8–6.6 kN/m，恢复系数约 0.91–0.94（推算值，标准中未直接给出）。

### Competition Trampoline Stiffness (Qian et al. 2020)
- 链接： https://pmc.ncbi.nlm.nih.gov/articles/PMC7386159/
- 类别： 物理参数
- 对象： 蹦床
- 内容： 5.05 × 2.91 × 1.15 m 比赛蹦床；20–260 kg 静载下床中心刚度线性，为 5.69 kN/m；弹簧 0.70 / 1.10 kN/m；有限元床面与多体仿真耦合
- 格式： 期刊论文
- 获取方式： 公开
- 许可： CC BY-NC-ND
- 摘要： 比赛蹦床的实测刚度。

### Trampoline Bed Spring-Network Model (Jules_toile_A2022)
- 链接： https://github.com/EveCharbie/Jules_toile_A2022
- 类别： 物理参数
- 对象： 蹦床
- 内容： 15 × 9 质点网格，含框架弹簧、床面弹簧和斜向弹簧，用动捕和测力台静态试次拟合；床面质量 5 kg；阻尼尚未定稿
- 格式： Python / CasADi 代码和拟合结果 pickle
- 获取方式： 公开
- 许可： 未声明
- 摘要： 目前最接近的、经实验拟合的开源蹦床床面空间模型。

### MuJoCo Flex Trampoline Example
- 链接： https://github.com/google-deepmind/mujoco/blob/main/model/flex/trampoline.xml
- 类别： 物理参数
- 对象： 蹦床（仿真）
- 内容： 16 × 16 二维弹性 flexcomp，1.5 m 见方，四角固定
- 格式： MJCF
- 获取方式： 公开
- 许可： Apache-2.0
- 摘要： MuJoCo 官方的弹性膜蹦床起点模型。

</details>
