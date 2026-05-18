# Papers

> Long-term curated paper list for legged robotics.

This draft is the initial long-term paper file for the repository split.
Unlike `legged-daily/YYYY-MM-DD.md`, this file is meant for **persistent retrieval**, not daily triage.
It now includes the current paper-related content that already exists in the source `README.md`.

---

## How to Use This File

Use this file for papers that are worth preserving beyond a single daily update.
Good candidates include:
- representative papers in a subtopic
- papers that introduce strong methods, datasets, benchmarks, or systems
- papers repeatedly connected to new repos, labs, or coauthor networks
- papers that help orient future reading

Do **not** store daily-only importance labels here.

---

## Basics

### Rigid Body Dynamics Algorithms
- Link: resources/books/Rigid%20Body%20Dynamics%20Algorithms.pdf
- Source: book
- Topics: dynamics / rigid body dynamics / fundamentals
- Summary: Foundational material on rigid body dynamics algorithms.

### 仿人机器人
- Link: resources/books/仿人机器人.pdf
- Source: book
- Topics: humanoid / fundamentals
- Summary: Book resource on humanoid robots.

### Robot Dynamics Lecture Notes - ETH
- Link: https://ethz.ch/content/dam/ethz/special-interest/mavt/robotics-n-intelligent-systems/rsl-dam/documents/RobotDynamics2017/RD_HS2017script.pdf
- Source: lecture notes
- Topics: robot dynamics / fundamentals
- Summary: ETH lecture notes on robot dynamics.

---

## Learning-based Simulation

### A review of learning-based dynamics models for robotic manipulation
- Link: https://www.science.org/doi/epdf/10.1126/scirobotics.adt1497
- Source: Science Robotics
- Topics: learning-based simulation / dynamics models / manipulation
- Summary: Review of learning-based dynamics models for robotic manipulation.

### Robotic World Model: A Neural Network Simulator for Robust Policy Optimization in Robotics
- Link: https://sites.google.com/view/roboticworldmodel
- Source: project page
- Topics: world model / simulation / policy optimization
- Summary: Neural network simulator for robust policy optimization in robotics.
- Notes: Code link in current README: https://github.com/leggedrobotics/robotic_world_model.git

### Uncertainty-Aware Robotic World Model Makes Offline Model-Based Reinforcement Learning Work on Real Robots
- Link: https://sites.google.com/view/uncertainty-aware-rwm
- Source: project page
- Topics: world model / offline RL / model-based reinforcement learning
- Summary: Uncertainty-aware robotic world model for offline model-based RL on real robots.
- Notes: Current README also links a GitHub code reference.

### Neural Robot Dynamics
- Link: https://neural-robot-dynamics.github.io/
- Source: project page
- Topics: robot dynamics / learned dynamics
- Summary: Project focused on neural robot dynamics.

---

## Dexterous Manipulation

### SimToolReal: An Object-Centric Policy for Zero-Shot Dexterous Tool Manipulation
- Link: https://simtoolreal.github.io/
- Source: project page
- Topics: dexterous manipulation / sim-to-real / policy learning
- Summary: Object-centric policy for zero-shot dexterous tool manipulation.
- Notes: PDF: https://arxiv.org/pdf/2602.16863 and code: https://github.com/tylerlum/simtoolreal

### TactAlign: Human-to-Robot Policy Transfer via Tactile Alignment
- Link: https://yswi.github.io/tactalign/
- Source: project page
- Topics: dexterous manipulation / tactile alignment / policy transfer
- Summary: Human-to-robot policy transfer through tactile alignment.
- Notes: PDF: https://arxiv.org/pdf/2602.13579

---

## Trampoline / Deformable Terrain

### Learning quadrupedal locomotion on deformable terrain
- Link: https://www.science.org/doi/pdf/10.1126/scirobotics.ade2256
- Source: Science Robotics
- Topics: quadruped / deformable terrain / locomotion / adaptation
- Summary: Learning quadrupedal locomotion on deformable terrain.
- Notes: Also described in the source README under data-driven optimization with method and result notes.

### RMA: Rapid Motor Adaptation for Legged Robots
- Link: https://arxiv.org/pdf/2107.04034
- Source: arXiv
- Topics: locomotion / adaptation / legged robots
- Summary: Rapid motor adaptation for legged robots.

---

## Data-driven Optimization

### Learning quadrupedal locomotion on deformable terrain
- Link: https://www.science.org/doi/pdf/10.1126/scirobotics.ade2256
- Source: Science Robotics
- Topics: quadruped / deformable terrain / RL / adaptation
- Summary: Trains a quadruped RL policy in simulation with a parameterized deformable-terrain contact model and broad terrain randomization.
- Notes: Current README includes detailed method and result notes about recurrent inference of terrain properties and successful hardware transfer.

### Data-Enabled Predictive Control: In the Shallows of the DeePC
- Link: https://arxiv.org/pdf/1811.05890
- Source: arXiv
- Topics: data-driven control / predictive control / DeePC
- Summary: Data-enabled predictive control in the shallows of DeePC.

### Toward a Data-Driven Template Model for Quadrupedal Locomotion
- Link: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9799758
- Source: IEEE
- Topics: quadruped / template models / data-driven control
- Summary: Toward a data-driven template model for quadrupedal locomotion.

### Deep DeePC: Data-enabled predictive control with low or no online optimization using deep learning
- Link: https://aiche.onlinelibrary.wiley.com/doi/pdf/10.1002/aic.18644
- Source: journal article
- Topics: DeePC / deep learning / predictive control
- Summary: Deep DeePC with low or no online optimization using deep learning.

### prescyent
- Link: https://github.com/hucebot/prescyent
- Source: GitHub
- Topics: data-driven control / trajectory prediction
- Summary: Data-driven trajectory prediction library in Python.

---

## Surveys and Collections

### many-quadrupeds
- Link: https://github.com/beduffy/many-quadrupeds
- Source: GitHub
- Topics: survey / collection / quadrupeds
- Summary: Awesome-style collection of many quadruped-related resources.

---

## Suggested Future Topic Organization

As the file grows, it can be reorganized under stable headings such as:
- Humanoids
- Quadrupeds
- RL
- MPC / Model-based Control
- Motion Tracking / Mimic
- Perception / Navigation
- Sim-to-real / Foundation Models

The current draft keeps closer alignment with the existing README content so migration is easier to verify.

---

## Maintenance Rules
- Keep entries concise enough for GitHub Markdown browsing.
- Prefer curation over exhaustiveness.
- When a paper is first discovered in a daily log, only move it here if it is worth long-term retrieval.
- Use notes to preserve the context that helps future search and review.
