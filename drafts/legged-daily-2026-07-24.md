**English** | [中文](../zh/drafts/legged-daily-2026-07-24.md)
# Legged Daily - 2026-07-24

## Summary
- One high-confidence new paper was selected: CAT conditions terrain traversability directly on robot embodiment and demonstrates real-world navigation with Boston Dynamics Spot and TerraSentia.
- No new implementation repository met the bar today. CAT currently exposes a project website repository, but no public training or deployment code was found.
- The University of São Paulo Mobile Robotics Group is a new source worth tracking; the already tracked LAAS-CNRS/JRL humanoid PhD remains active, with a 2026-07-31 deadline.

<details>
<summary><strong>New Papers</strong></summary>

### Towards Capability-Aware Traversability Navigation for Unstructured Environments
- Link: https://arxiv.org/abs/2607.20679
- Project: https://capability-aware-traversability.github.io/
- Source: arXiv / IROS 2026
- Date: 2026-07-22
- Authors: Gianluca Capezzuto, Felipe Tommaselli, Matheus P. Angarola, Ricardo V. Godoy, Marcelo Becker
- Topics: traversability / embodiment conditioning / quadruped navigation / semantic perception / unstructured environments
- Summary: Capability-Aware Traversability (CAT) predicts dense terrain costs while conditioning the perception representation on a queried robot profile. It combines RGB-D DINOv3 features, CLIPSeg semantic terrain maps, robot-specific traversability vectors, a SPADE decoder, and per-robot prototypes, rather than applying embodiment constraints only as a late trajectory filter.
- Notes: The authors report an 11.0% AUROC improvement on physically executed trajectories and a 15.8% AUPRC improvement on human traces over the strongest baseline. On a Jetson Orin Nano, CAT runs at 4.8 Hz; Boston Dynamics Spot completed 10/10 forest trials, while TerraSentia avoided a staircase in 7/10 trials. The project-page repository contains website assets, but no public implementation was visible at verification time.

</details>

<details>
<summary><strong>New Repos</strong></summary>

No new high-confidence implementation repository was selected today. The CAT project website is public at https://github.com/capability-aware-traversability/capability-aware-traversability.github.io, but GitHub metadata and the published site identify it as a project-page repository rather than released training or deployment code.

</details>

<details>
<summary><strong>Lab / Professor Signals</strong></summary>

### Marcelo Becker / Mobile Robotics Group
- Institution: University of São Paulo (USP), São Carlos, Brazil
- Homepage: https://capability-aware-traversability.github.io/
- arXiv: https://arxiv.org/abs/2607.20679
- Lab / Department: Mobile Robotics Group, University of São Paulo
- Key Topics: mobile robotics / traversability / semantic perception / quadruped navigation / field deployment
- Notes: CAT is a concrete new signal from the group around multi-embodiment outdoor navigation. The work combines physically grounded trajectory labels with foundation-model visual features and validates the same capability-aware representation on both Boston Dynamics Spot and a wheeled skid-steer robot, making this group useful to track for field robotics and embodiment-aware perception.
- Students and Representative Works:
  - [Gianluca Capezzuto](https://arxiv.org/search/cs?searchtype=author&query=Capezzuto,+G) — [Towards Capability-Aware Traversability Navigation for Unstructured Environments](https://arxiv.org/abs/2607.20679)

</details>

<details>
<summary><strong>Job Signals</strong></summary>

### LAAS-CNRS Gepetto / CNRS-AIST JRL — PhD in Humanoid Robotics
- Type: PhD
- Location: Toulouse, France, with part of the work at JRL in Tsukuba, Japan
- Source: https://emploi.cnrs.fr/Offres/Doctorant/UPR8001-OLISTA-018/Default.aspx?lang=EN
- Deadline: 2026-07-31 23:59 local posting time
- Topics: humanoid locomotion / reinforcement learning / online MPC / whole-body control / safe control
- Status: active; previously tracked, deadline reminder
- Notes: The project assigns discrete high-level contact, footstep, gait, and behavior decisions to RL while online MPC enforces continuous whole-body feasibility and safety. Supervision is by Olivier Stasse at LAAS-CNRS Gepetto and Mehdi Benallegue at CNRS-AIST JRL; intended hardware includes PAL Robotics Kangaroo and/or Unitree H1/R1-class humanoids. The official page lists an expected start date of 2026-10-01.

### EPFL BioRob humanoid locomotion positions
- Current Status: closed / not selected as an active signal
- Reason: The official openings page labels the Fall 2026 humanoid neuromechanics Postdoc/PhD entry “CLOSED” and also states that the positions are now closed, despite older application text remaining on the same page.
- Source Checked: https://www.epfl.ch/labs/biorob/openings/

</details>
