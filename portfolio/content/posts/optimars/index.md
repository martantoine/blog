+++
title = "OptiMARS"
date = "2025-09-26"
lastmod = "2025-11-09"
author = ""
authorTwitter = "" #do not include @
cover = "cover.png"
tags = ["Monte Carlo", "Mujoco", "GUI", "C++", "Inverse Kinematics", "Non Linear Optimization", "Java", "Python", "UDP", "RTI DDS", "Linux", "V&V"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
highlighted = true
+++

## In short
- Dev. a Digital Twin to optimize tool dimensions & motions
- Dev. algorithms to improve the collaborative capabilities of the KUKA arms

<!--more-->
---
## Abstract
The MARS surgical system enhances minimally invasive procedures through magnetic fields and robotic automation. The system's surgical effectiveness is directly tied to the robot kinematics behavior. For this reason, this research refines the target controller to improve positional consistency, a solution already tested and awaiting deployment. Additionally, OptiMARS, a Monte Carlo-based simulator, was developed to optimize kinematic parameters such as cart placement and tool dimensions. This simulator incorporates patient-specific variations (e.g. BMI, incision location) and replicates the real system’s motion controller behavior, enabling relevant kinematic optimization. Initial optimization efforts have yielded a set of optimized cart placement positions that can be used during a new alignment procedure. The work delivers immediate improvements while establishing a scalable framework for future enhancements, ensuring the MARS system can evolve alongside clinical advancements.

{{< image src="editor.png" >}}

## Key Achievements
- Creation of a high-fidelity digital twin model of the operating room
- Simulation of the physical environment, including collision detection and Jacobian evaluation
- GUI-based editing and visualization of the digital twin
- Implementation of inverse kinematics for the robotic arms
- Execution of non-linear optimization algorithms to optimize cart placement and tool dimensions

