**English** | [中文](../zh/drafts/legged-daily-2026-05-23.md)
# Legged Daily - 2026-05-23

## Summary
- Today's strongest signals cluster around humanoid navigation and whole-body loco-manipulation: MIF, SUGAR, and WiXus all report real-system or deployment-oriented results.
- MIF is marked as RSS 2026 and targets robust Unitree G1 navigation in dynamic offices with semantic 3DGS memory, local memory updates, and interaction-pose safety.
- SUGAR converts unstructured human videos into deployable humanoid loco-manipulation skills, aiming to reduce task-specific reward design, reference-motion conditioning, and heavy teleoperation dependence.
- WiXus is an ICRA 2026 wheeled-legged robot that uses environmental wire actuation so its legs can switch from locomotion to manipulation/tool-use roles.
- Repository signals are mostly newly discovered or actively updated infrastructure: BotBrain for ROS2 web-based legged robot operation, EgoHumanoid for egocentric-demo humanoid loco-manipulation, and SIMPLE for humanoid loco-manipulation simulation/evaluation.
- Job signal verified from the official EPFL BioRob openings page: Fall 2026 PhD/Postdoc openings on human locomotion neuromechanics with humanoid robots.

## New Papers
- [Learning to Evolve: Multi-modal Interactive Fields for Robust Humanoid Navigation in Dynamic Environments](https://arxiv.org/abs/2605.21935)
  Source: arXiv / RSS 2026 / project page
  Importance: high
  Summary: MIF combines confidence-aware semantic 3D Gaussian Splatting, discrepancy-triggered spatial memory updates, and task-driven geometry reconstruction for manipulation-oriented Unitree G1 navigation; the project page reports relocation success rising from 12% to 94% and 91.4% semantic-memory reduction in a real dynamic office.

- [SUGAR: A Scalable Human-Video-Driven Generalizable Humanoid Loco-Manipulation Learning Framework](https://arxiv.org/abs/2605.20373)
  Source: arXiv / project page
  Importance: high
  Summary: SUGAR extracts interaction priors from unstructured human videos, refines them into physically feasible skills, and distills them into a hierarchical policy for humanoid loco-manipulation; the paper reports real-hardware zero-shot transfer, closed-loop execution, and autonomous failure recovery.

- [WiXus: A Wheeled-Legged Robot with Wire-Driven Environmental Utilizing to Integrate Mobility and Manipulation](https://arxiv.org/abs/2605.20932)
  Source: arXiv / ICRA 2026 / project page
  Importance: medium
  Summary: WiXus combines wheeled-legged locomotion with wire-driven environmental anchoring, enabling planar motion, cliff climbing, and suspension-based leg repurposing for object manipulation and tool use; this is a notable hardware-design signal for mobility-manipulation integration.

## New Repos
- [BotBrain](https://github.com/botbotrobotics/BotBrain)
  Topic: ROS2 / web UI / teleoperation / navigation / legged robots
  Importance: medium
  Summary: A modular open-source robot brain for quadrupeds, bipeds, humanoids, and wheeled ROS2 robots, with a web UI for teleoperation, autonomous navigation, mapping, monitoring, and 3D-printable hardware; the README explicitly targets Jetson / RealSense deployments and Unitree Go2/G1-style platforms.

- [EgoHumanoid](https://github.com/OpenDriveLab/EgoHumanoid)
  Topic: humanoid / loco-manipulation / egocentric demos / VLA
  Importance: medium
  Summary: RSS 2026 framework for training humanoid whole-body loco-manipulation from egocentric human demonstrations plus limited robot data, using view alignment and action alignment before deploying VLA policies on Unitree G1 hardware.

- [SIMPLE](https://github.com/physical-superintelligence-lab/SIMPLE)
  Topic: simulator / benchmark / humanoid loco-manipulation / IsaacSim / MuJoCo
  Importance: medium
  Summary: A simulation-based policy learning and evaluation environment with Unitree G1 support, 1000+ Objaverse assets, 50+ Habitat HSSD scenes, and 50+ humanoid whole-body loco-manipulation tasks; useful as a watchlist item for full-stack humanoid manipulation evaluation.

## Lab / Professor Signals
- Name / Lab: Peifeng Jiang et al. / Peking University Shenzhen Graduate School + Oxford Robotics Institute + ETH Zurich
  Source: MIF arXiv / project page
  Update: MIF connects humanoid navigation, semantic 3DGS memory, dynamic-scene updates, and Unitree G1 real-world trials, making this author network a high-priority source for perception-aware humanoid navigation.

- Name / Lab: CFCS, School of Computer Science, Peking University + Beihang University
  Source: SUGAR arXiv / project page
  Update: SUGAR shows active work on human-video-driven humanoid loco-manipulation; track the project page and authors for code/data releases or follow-up systems.

- Name / Lab: JSK Robotics Laboratory, The University of Tokyo
  Source: WiXus project page / arXiv
  Update: WiXus is an ICRA 2026 hardware-system signal from the JSK network, extending wheeled-legged robots with environmental wire actuation for mobility, manipulation, and tool use.

## Job Signals
- Institution / Company / Lab / Team: EPFL Biorobotics Laboratory / Auke Ijspeert
  Type: PhD / Postdoc
  Source: official BioRob open positions page
  Deadline: Fall 2026 opening; EPFL doctoral program deadlines are typically April 15 and December 15
  Summary: The official page lists one Postdoc and one PhD opening on investigating and leveraging human locomotion neuromechanics using humanoid robots, combining numerical neuromechanical simulations, bio-inspired humanoid locomotion controllers, and reinforcement learning.
