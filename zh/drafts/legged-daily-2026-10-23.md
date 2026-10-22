[English](../../drafts/legged-daily-2026-10-23.md) | **中文**
# Legged Daily - 2026-10-23

## 摘要
- HuMiT(清华叉院 / 港中文)只跟踪根高度、根速度和四个稀疏关键点位姿组成的紧凑参考,实现 G1 全身遥操作,头显输入到策略输出约 20 ms;训练代码已公开。
- RISE(Stella X. Yu 组)在推理时用任务代价引导摔倒后的人形机器人如何起身,基于学习到的恢复动作词表和视觉扩散规划器,并在 Unitree G1 上进行了真机演示。
- SP-HLM 以五个任务关键身体位姿作为 VLA、实时动作生成器和通用动作跟踪器之间的接口,用于人形移动操作。
- 新仓库:`btx0424/active-adaptation`,是 FACET、HDMI、GentleHumanoid、Gallant 背后的 RL 框架,支持 Isaac Sim、MuJoCo、mjlab 后端。
- HoloMotion README 新增 2026-10-22 条目:H-bot 竞赛开放(Track 2 拳击基线单卡约 21 分钟训练);v2.1 与 HoloMotion-2 技术报告仍计划于 10 月底发布。
- 未核实到新招聘;EPFL BioRob 人形神经力学 PhD/博后岗位官方页面已标注 CLOSED。

<details>
<summary><strong>新论文</strong></summary>

### HuMiT: Low-Latency Whole-Body Humanoid Teleoperation via Compact Reference Tracking
- Link: https://arxiv.org/abs/2610.29903
- Source: arXiv
- Date: 2026-10-21
- Authors: Liu Cao, Botian Xu, Ruoqu Chen, Jiajun Liu, Mingzhi Pei, Zihao Wang, Zhongyu Li, Mengdi Xu
- Topics: 人形 / 全身遥操作 / 动作跟踪 / 低延迟 / 仿真到真机
- Summary: 统一的跟踪策略只需每帧紧凑参考(根高度、根速度、四个稀疏关键点的 SE(3) 位姿),即可达到使用更丰富参考信息的方法的水平,实现低延迟人形全身遥操作。
- Notes: 报告头显输入到策略输出约 20 ms,光流测得的中位延迟 65 ms;Unitree G1 真机演示包括反应式接物和协调操作。项目页:https://xiaohu-art.github.io/Track/;代码:https://github.com/xiaohu-art/Track。相关工作:ExtremControl(arXiv 2602.11321)低延迟遥操作。

### Test-Time Motion Steering for Perceptive Humanoid Fall Recovery
- Link: https://arxiv.org/abs/2610.30061
- Source: arXiv
- Date: 2026-10-21
- Authors: Osher Azulay, Cheng-Lin Hsieh, Stella X. Yu
- Topics: 人形 / 摔倒恢复 / 扩散规划 / 感知控制 / 测试时引导
- Summary: RISE 学习一个把意图动作与电机动作关联起来的恢复动作词表,再用视觉扩散规划器预测未来身体状态,并用任务代价(朝向、起身速度或路径)引导预测,从而无需重新训练即可控制机器人的起身方式。
- Notes: 仿真展示了多样的恢复方式、地形适应和测试时引导;真机演示在 Unitree G1 上完成。项目页:https://osheraz.github.io/RISE/(代码标注“即将发布”)。

### SP-HLM: Sparse-Pose-Driven Motion Generation and Whole-Body Control for Humanoid Loco-Manipulation
- Link: https://arxiv.org/abs/2610.30044
- Source: arXiv
- Date: 2026-10-21
- Authors: Zhaohui Yang, Quanbao Lin, Chengqi Shi, Zhenglang Weng, Jicheng Lin, Boyu Chen, Tengjie Zhu, Guanzhu Ren, Jiahao Xu, Yang Feng, Xiaokang Yang, Yao Mu
- Topics: 人形 / 移动操作 / VLA / 动作生成 / 动作跟踪
- Summary: 以五个任务关键身体位姿加学习到的潜在动作先验作为高层策略与全身控制之间的接口:SP-VLA 根据观测和语言预测稀疏位姿,SP-MGM 实时重建全身动作,SP-GMT 负责跟踪。
- Notes: 摘要称在动作跟踪和移动操作上均有提升,但未给出具体数字。项目页:https://sp-hlm.github.io/(本次运行无法抓取,代码是否公开未核实)。

</details>

<details>
<summary><strong>新仓库</strong></summary>

### btx0424/active-adaptation
- Link: https://github.com/btx0424/active-adaptation
- Category: RL / 工具包
- Robot Type: 通用 / 四足 / 人形
- Simulator: Isaac Lab / Isaac Sim(5.1.0+)、MuJoCo、mjlab
- Deploy: sim
- Summary: 面向足式运动与移动操作的 RL 框架,提供自动形状处理、单文件 RL 实现、对称性增强、MuJoCo sim2sim 以及项目脚手架 CLI。
- Notes: README 列出 Unitree Go2、G1、A2、B2,并注明 FACET、HDMI、GentleHumanoid、Gallant 基于此框架;HuMiT 的 Track 仓库依赖它。约 163 星;未见许可证或发布标签。

### xiaohu-art/Track
- Link: https://github.com/xiaohu-art/Track
- Category: 动作跟踪 / RL
- Robot Type: 人形
- Simulator: Isaac Lab(Isaac Sim 5.1.0)
- Deploy: sim
- Summary: HuMiT 项目页链接的代码,用于训练和评估 PPO 参考动作跟踪策略,可选导出 ONNX;基于 active-adaptation。
- Notes: README 内容很少,未见许可证或已发布权重,也未看到真机部署代码。相关论文:HuMiT(arXiv 2610.29903)。

</details>

<details>
<summary><strong>实验室 / 教授信号</strong></summary>

### Zhongyu Li — The Chinese University of Hong Kong
- Institution: 香港中文大学
- Homepage: https://zyliatzju.github.io/
- X: https://x.com/ZhongyuLi4
- Key Topics: 人形 / 全身遥操作 / 动作跟踪 / RL / 控制
- Notes: 对 labs.md 已有条目的更新:与 Mengdi Xu(清华叉院)、Botian Xu(港中文)合作发表 HuMiT(arXiv 2610.29903),训练代码已开源,基于 Botian Xu 的 active-adaptation 框架。Botian Xu 在组内的身份未核实,因此不建议添加学生条目。

</details>

<details>
<summary><strong>招聘信号</strong></summary>

### 无新核实岗位
- Source: 官方来源核查
- Status: watching
- Notes: EPFL BioRob 关于人形机器人与人类运动神经力学的博后 + PhD 岗位在官方页面已标注 CLOSED,不建议加入 jobs.md。此前提出的 LAAS-CNRS 安全强化学习 PhD 移除建议(截止 2026-07-31,已过期)仍待确认。

</details>
