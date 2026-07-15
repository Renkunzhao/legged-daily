**English** | [中文](../zh/drafts/legged-daily-2026-07-15.md)
# Legged Daily - 2026-07-15

## Summary
- GaitSpan grows a pretrained humanoid walking policy into a single command-conditioned walking, jogging, and running policy through rhythm generation, stride shaping, and residual adaptation.
- A new vision-based humanoid soccer paper learns opponent-aware dribbling from temporal depth observations, but its current evidence is simulation-only and performance drops against an active attacker.
- RoboParty released UFO, an unsupervised humanoid-control framework with MJLab training, motion-data import, ONNX export, and a separate Unitree G1 deployment branch.
- LAAS-CNRS opened a humanoid-robotics PhD on hybrid RL and online MPC for contact-mode decisions and whole-body dynamic locomotion; applications close on July 31, 2026.

<details>
<summary><strong>New Papers</strong></summary>

### GaitSpan: Growing Humanoid Locomotion from Walking to Running
- Link: https://arxiv.org/abs/2607.12114
- Source: arXiv
- Date: 2026-07-13
- Authors: Kwan-Yee Lin, Zilin Wang, Janelle J. Liu, Stella X. Yu
- Topics: humanoid locomotion / reinforcement learning / gait transition / sim-to-real
- Summary: GaitSpan expands a pretrained walking policy into continuous-speed walking, jogging, and running-like locomotion by reusing frozen walking structure, combining learned internal rhythms, shaping dynamic strides, and adding residual corrections; the authors report cross-morphology transfer and zero-shot deployment on unseen simulated and real terrains.
- Notes: Project page: https://gaitspan2026.github.io/. Its code button pointed to https://github.com/LeCAR-Lab/GaitSpan/ during review, but that repository was not publicly accessible at the check time.

### Vision-Based Dribbling for Humanoid Soccer via Privileged Representation Learning
- Link: https://arxiv.org/abs/2607.12702
- Source: arXiv
- Date: 2026-07-14
- Authors: Flavio Maiorana, Valerio Spagnoli, Eugenio Bugli, Flavio Volpi, Daniele Affinita, Vincenzo Suriani, Daniele Nardi, Luca Iocchi
- Topics: humanoid / loco-manipulation / reinforcement learning / visual control / soccer
- Summary: The method first learns a privileged-state dribbling policy and then trains a temporal depth encoder to reproduce its task latent, enabling a simulated Booster T1 to dribble from onboard-style depth observations without explicit scene-state estimation.
- Notes: The project reports 100% success without obstacles, 96% with one static obstacle, and 46% against an active ball attacker; all reported experiments are currently in simulation. Project page: https://lab-rococo-sapienza.github.io/learning-to-dribble/.

</details>

<details>
<summary><strong>New Repos</strong></summary>

### UFO
- Link: https://github.com/Roboparty/UFO
- Category: RL / motion learning / deployment toolkit
- Robot Type: humanoid
- Simulator: MJLab / MuJoCo
- Deploy: both
- Summary: An unsupervised reinforcement-learning framework for humanoid control with FB and TeCH training, robot-aware motion-data import, tracking/goal/reward inference, and ONNX export; Unitree G1 is the best-tested path and real-robot deployment and teleoperation live on a separate deploy branch.
- Notes: The repository was created on 2026-07-13 and had 43 GitHub stars when checked. New robot bring-up is explicitly experimental, requires already-retargeted robot motion data, and does not provide automatic motion retargeting or cross-morphology checkpoint reuse.

### DribbleMaster
- Link: https://github.com/Zhuoheng0910/DribbleMaster
- Category: RL / locomotion / sim-to-sim
- Robot Type: humanoid
- Simulator: Isaac Gym / MuJoCo
- Deploy: sim
- Summary: Newly published training and evaluation code for the ICRA 2026 paper “Dribble Master,” providing an Isaac Gym humanoid dribbling task, PPO training, policy playback, and MuJoCo sim-to-sim validation.
- Notes: The repository was created on 2026-07-14 and is MIT-licensed. It corresponds to the earlier arXiv paper 2505.12679 rather than a new paper from this week.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### RoboParty Lab
- Homepage: https://github.com/Roboparty
- GitHub: https://github.com/Roboparty
- Lab / Department: RoboParty Lab
- Key Topics: humanoid / motion retargeting / imitation learning / unsupervised RL / deployment / teleoperation
- Notes: The lab released UFO and also published the Party OS roadmap at https://github.com/Roboparty/Party_OS, connecting motion-data generation, human-to-humanoid retargeting, MimicLite imitation learning, UFO unsupervised learning, and future interaction and VLA layers. This is a useful new source to watch for open humanoid-control infrastructure.

### RoCoCo Lab
- Institution: Sapienza University of Rome
- Homepage: https://lab-rococo-sapienza.github.io/learning-to-dribble/
- GitHub: https://github.com/Lab-RoCoCo-Sapienza
- Lab / Department: RoCoCo Lab, Department of Computer, Control, and Management Engineering
- Key Topics: humanoid / robot soccer / reinforcement learning / visual control / loco-manipulation
- Notes: The lab's new temporal-depth dribbling project links perception directly to a humanoid control policy and identifies active moving adversaries and Booster T1 sim-to-real transfer as the main next steps.

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto Team — PhD in Humanoid Robotics
- Type: PhD
- Location: Toulouse, France
- Source: official website — https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59
- Topics: humanoid / legged locomotion / reinforcement learning / MPC / whole-body control / safe control
- Status: active
- Notes: A 36-month PhD starting October 1, 2026, supervised by Olivier Stasse at LAAS-CNRS and co-supervised by Mehdi Benallegue at CNRS-AIST JRL. The project assigns discrete contact, footstep, gait, and behavior-transition decisions to RL while an online-parametrized MPC enforces physical constraints and generates continuous whole-body motion, with planned validation on PAL Robotics Kangaroo and/or Unitree humanoids.

</details>
