+++
title = "OptiMARS"
date = "2025-09-26"
author = ""
authorTwitter = "" #do not include @
cover = "cover.png"
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
+++
<!--more-->
# Abstract
The MARS surgical system enhances minimally invasive procedures through magnetic fields and robotic automation. The system's performance is directly constrained by the robot kinematics behavior. Consequently, improving workspace utilization would significantly increase the surgical effectiveness of MARS.
This research addresses these challenges by refining the target controller to improve positional consistency, a solution already tested and awaiting deployment. Additionally, OptiMARS, a Monte Carlo-based simulator, was developed to optimize kinematic parameters such as cart placement and tool dimensions. This simulator incorporates patient-specific variations (e.g. BMI, incision location) and replicates the real system’s motion controller behavior, enabling relevant kinematic optimization. Initial optimization efforts have yielded a set of optimized cart placement positions that can be used during a new alignment procedure. The work delivers immediate improvements while establishing a scalable framework for future enhancements, ensuring the MARS system can evolve alongside clinical advancements.

{{< image src="editor.png" >}}

# Key Achievements
- Creation of a high-fidelity digital twin model of the operating room
- Simulation of the physical environment, including collision detection and Jacobian evaluation
- GUI-based editing and visualization of the digital twin
- Implementation of inverse kinematics for the robotic arms
- Execution of non-linear optimization algorithms to optimize cart placement and tool dimensions
