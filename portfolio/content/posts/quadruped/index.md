+++
title = "Quadruped Robot with Tensegrity Joints actuated via Pneumatic Artificial Muscles"
date = "2024-06-01T18:28:01-07:00"
lastmod = "2025-11-09"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
authorTwitter = "" #do not include @
cover = "cover.jpeg"
tags = ["Tensegrity", "Pneumatic Soft Actuators", "Mujoco", "RL with Gymnasium, 3D Printing"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
highlighted = true
+++
<!--more-->
The design of a quadruped robot with tensegrity joints and McKibbens artificial muscles is a complex challenge, as it involves the intricate task of designing a multi-axis compliant joint integrated with compliant actuation.
Analytical resolutions, simulations, and real-world measurement were necessary to solve this complex design problem. 
The demonstrator itself was first tested in Mujoco simulation before actually building it.

It was possible to eliminate the need for antagonistic pairs of muscles thanks to the introduction of a restoring force in every joint, hence reducing by a factor of two the number of actuators when compared with the antagonistic approach, eventually making the robot lighter. The pneumatic actuators are controlled by onboard valves and a microcontroller. The tensegrity joints are an assembly of 3d printed thermoplastic polyurethane and 3d printed PETG.

Thanks to the joints' restoring force, the quadruped has the ability to stand by itself without active actuator control. This follows the idea of a compliant quadruped robot with minimal sensory feedback.
So far, the robot has been shown to be capable of walking forward in simulation and on a flat surface with the demonstrator (while being supported by a rail).

{{< video src="walking.mp4" type="video/mp4" >}}

<object data="quadsegrity.pdf" type="application/pdf" width="100%" height="1000px">
    <p>Unable to display PDF file. <a href="quadsegrity.pdf">Download</a> instead.</p>
</object>