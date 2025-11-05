+++
title = "5 DOFs Robotic Arm"
date = "2018-06-01"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
+++
		
# Description

> ## ⚠️ Warning
> **WARNING:** This post describes a project known to be of very low quality. You might experience nausea while reading it.
>
> .. This is an old project from high-school. Back then I had no idea about how to properly engineer anything, more specifically:
> - how to properly design a robot (e.g: torque balancing)
> - concurrent motor control (everything runs in a single thread..)
> - inverse kinematic, it is totally missing here -_-


This project is about designing and manufacturing a simple 5 DOFs robotic arm.

It uses one servomotor for each degree of freedom, all controlled and powered by the Arduino Mega 2560.

There are 4 push buttons that can be used to manually control each degree of freedom separately.

# Final result
{{< image src="Vue 1.jpg" >}}
{{< image src="Vue 2.jpg" >}}
{{< image src="Vue 3.jpg" >}}

# Robot's ability demonstration
{{< image src="cover.gif" >}}

# Manual control
{{< image src="manual.gif" >}}
Controlled by pressing on those 4 buttons	

{{< image src="Vue 4.jpg" >}}

# A few 3d renders
{{< image src="FilaireFrontColored.png" >}}
{{< image src="FilaireSideColored.png" >}}
{{< image src="Perspective_1.JPG" >}}
{{< image src="Perspective_2.JPG" >}}
