+++
title = "Bootstrapped Feature Mapper"
date = "2026-10-18T18:28:01-07:00"
lastmod = "2026-10-18"
author = ""
authorTwitter = "" #do not include @
cover = "cover.jpeg"
tags = ["Computer Vision", "Percpetion", "Agriculture"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
highlighted = true
toc = false
+++
<!--more-->
Crop perception is hard to scale because agriculture covers a very wide range of crops, and training a reliable model for each one is expensive in data and annotation.

This project tests whether that cost can be replaced by a minimal amount of user input. The farmer manually labels a few points on as few as 3 frames of their own footage, marking the classes they care about (tomato, weed, eggplant, fruit tree, etc.). These labels bootstrap the classification step by matching against features from a frozen, general-purpose vision model. No training is involved.

The rest of the pipeline is generic: camera poses, depth estimation and 3D lifting rely on off-the-shelf models and need no retraining for a new crop or field. The output is a 3D point cloud of the labelled class, which is validated against an independent Gaussian splat reconstruction of the same scene.

{{< image src="pipeline.drawio.png" type="png" >}}

## Features: DINOv2 out of the box

The default DINOv2 base model already separates tomato plants from their surroundings well. Below, the red cross marks the selected pixel, and the yellow patches are the ones whose features are most similar to it.

{{< image src="dino_PCA_similarity.png" type="png" >}}

## From 2D to 3D

COLMAP gives the camera pose for each frame (left), and Depth Anything 3 gives time-coherent depth (right). Each classified patch is projected into 3D using that frame's pose and depth.

{{< images "camera_path.png" "preview_0025.png" >}}

The result is a point cloud of the selected class only:

{{< video src="result.mov" type="video/mp4" >}}

## Results and next steps

Looking at the 3D output, the main problem is accuracy rather than precision: the extracted points are consistent with each other, but they are not in the right place. Recall is harder to judge by eye, so it is not clear how much of the crop is being missed.

Before iterating toward a better pipeline, the remaining work for this version is to measure these metrics properly.

